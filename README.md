# Web Server Data Analysis

This repository showcases an in-depth analysis of **BoilerExam**, a study platform built to help Purdue University students excel in their exams.

BoilerExam supports _19 courses_, offers a database of _3,149 questions_, has logged _6,165,679 answers_, and facilitated _272,172 hours_ of study.

The analysis aims to uncover suspicious activities, such as unusual requests and user behaviors, that may signal security threats or misuse of the system.

## Repository Structure

- **`results/`**: Contains Jupyter notebooks with detailed findings and analyses.

## Analysis Highlights

This project dives into key areas to ensure the platform’s security and integrity:

### 1. Suspicious Requests from an IP Address
Repeated requests from IP `52.169.249.118` attempted to access sensitive WordPress-related files. Since BoilerExam doesn’t run on WordPress, this strongly indicates bot-driven activity targeting vulnerabilities.

- **Notebook**: [Malicious IP Analysis](results/malicious_ip.ipynb)

### 2. Unusual User Agent: axios/1.6.7
Requests using the rare user agent `axios/1.6.7` were observed at precise 5-second intervals targeting the stats page. This behavior suggests the presence of an automated bot or script.

- **Notebook**: [Weird User Agent Analysis](results/weird_user_agent.ipynb)

### 3. Additional Insights
Exploratory analysis of other data points that, while secondary, offer valuable insights into potential issues and platform usage patterns.

- **Notebook**: [Miscellaneous Data Analysis](results/misc.ipynb)

## Getting Started

To explore the findings:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/boilerexam-data-analysis.git
   cd boilerexam-data-analysis
   ```

2. **Set Up Your Environment**:  
   Install Jupyter or open the notebooks directly in [Google Colab](https://colab.research.google.com/).

3. **Access the Notebooks**:  
   Navigate to the `results/` directory to view detailed analyses.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE.md) file for details.

## Contact

Have questions or suggestions? Open an issue in this repository. Contributions are welcome!
