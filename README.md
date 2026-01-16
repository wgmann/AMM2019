This [repo](https://github.com/wgjm1986/AMM2019) contains Jupyter notebooks that explain how we constructed aggregate investment and Tobin's Q as used in the first two figures of Andrei, Mann, and Moyen (JFE 2019), and how to repeat this process as of 2026 using data available through the FRED API. We hope these files are helpful to those interested in working in this area. If you use these resources, please cite our paper as appropriate.

There are three different scripts in this repo:

- [AMM2019 - Archived data.ipynb](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20Archived%20data.ipynb) - This notebook replicates Figures 1 and 2 of the published paper using data that we archived at the time of publication. ([PDF version of the notebook output](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20Archived%20data.pdf))
	- The algorithm in our paper and in this notebook was designed to follow Hall (2001) as closely as possible, for consistency with prior literature. The sample ends in 2015.
	- There are two minor typos noted in the code, which can be corrected with negligible impact on the results. ([PDF of the output with these typos corrected](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20Archived%20data%20-%20errata%20corrected.pdf))
- [AMM2019 - FRED API data.ipynb](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20FRED%20API%20data.ipynb) - This notebook implements the same algorithm as the above, but downloading all data from FRED via API, which allows the results to be updated through the most recent available data. Due to revisions of historical data since the publication of our paper, the data downloaded by this code will not match the data that we archived. ([PDF](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20FRED%20API%20data.pdf))
- [AMM2019 - FRED API data - simplified.ipynb](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20FRED%20API%20data%20-%20simplified.ipynb) - This notebook removes many steps from Hall's algorithm to arrive at a process for constructing Tobin's Q and investment that is much simpler to follow, but yields qualitatively similar conclusions, and is closer in spirit to the way investment-Q regressions are often run in Compustat. See further comments in the file. ([PDF](https://wgjm1986.github.io/AMM2019/Code/AMM2019%20-%20FRED%20API%20data%20-%20simplified.pdf))

To get this repo running locally:

	git clone https://github.com/wgjm1986/AMM2019
	cd AMM2019
	cp .env.example .env

...then add your FRED API key to .env, then

	conda env create -f environment.yml
	conda activate AMM2019
	jupyter notebook

...and then open and run any of the files.
