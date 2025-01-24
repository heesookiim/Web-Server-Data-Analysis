# BoilerExam Data Analysis

This repository hosts the data analysis conducted on the BoilerExam platform. The purpose of this analysis is to identify and investigate suspicious requests and unusual user behaviors that could indicate potential security threats or system misuse.

## Project Structure

The repository is structured as follows:

- `results/`: Contains Jupyter notebooks with detailed analysis.

## Analysis Overview

### 1. Suspicious Requests from a Specific IP

We observed multiple requests from the IP address `52.169.249.118` attempting to access sensitive WordPress-related PHP files. This section explores these requests in depth to understand their nature and potential threat.

**Notebook**: [Malicious IP Analysis](results/malicious_ip.ipynb)

### 2. Unusual User Agent: axios/1.6.7

An uncommon user agent `axios/1.6.7` was found making requests at consistent 5-second intervals targeting the stats page, indicating an automated script or bot.

**Notebook**: [Weird User Agent Analysis](results/weird_user_agent.ipynb)

### 3. Miscellaneous Data Analysis

Additional data analysis covers various metrics that were not the primary focus but may provide insights into other potential areas of concern.

**Notebook**: [Miscellaneous Data Analysis](results/misc.ipynb)

## Getting Started

To run the Jupyter notebooks:

1. Clone this repository to your local machine.
2. Ensure you have Jupyter installed, or use [Google Colab](https://colab.research.google.com/) to open the notebooks.
3. Navigate to the `results/` directory and open the notebook you want to examine.

## Contributing

Contributions to this analysis are welcome. If you have suggestions or data that could enhance this project, please feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

## Contact

For any further questions or requests, please open an issue in this repository.

