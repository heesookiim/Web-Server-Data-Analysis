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
