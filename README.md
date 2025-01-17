### BoilerExam Data Analysis Report

#### 1. **Suspicious Requests from Specific IP**
The IP address `52.169.249.118` has been observed making repeated requests to access `wp-content` and other WordPress-related PHP files.

For more details, check out `results/malicious_ip.ipynb`

#### 2. **Unusual user_agent: `axios./1.6.7`**
Not like most user_agents values - Mac, Windows, and etc -, `axis./1.6.7` showed somewhat bizzare behaviour
  - Consistent 5-second interval requests on stat page

For more detaisl, check out `results/weird_user_agent.ipynb`

#### 3. Miscellaneous data analysis
Some aspects of these analysis require a deeper review in person, but were not fully explored due to time constraints.
