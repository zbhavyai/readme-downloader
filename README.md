# README Downloader

A script to download README files from random GitHub repositories using GitHub API


## Features

+ Downloaded files are randomly chosen but unique
+ Downloaded files belong only to the Software Development repository
+ Downloaded files have size greater than 2 KB
+ Stores index of downloaded files as a CSV file


## Dependencies

+ pandas 1.2.4
+ requests 2.26.0
+ openpyxl 3.0.7


## Program Structure

The code is presented in two formats - 

1. A `.py` script named as [readme_downloader.py](readme_downloader.py)

   Normally, this format should be the one to be used in most scenarios. This script accesses the GitHub personal access token stored in the file [GitHub_PAT.txt](GitHub_PAT.txt). The downloaded readme files are stored in a new directory named as **`readme_files`**, and their index would be stored as **`readme_files/index.csv`**.

2. A [databricks](https://community.cloud.databricks.com) notebook named as [readme_downloader.ipynb](readme_downloader.ipynb).

   This format was created to fit a particular use case for a university project. Due to restrictions and complex juggling of two filesystems in the databricks, this version lacks some functionalities like logging and creation of index of downloaded readme files.


## How to run

1. Clone the repository on your machine

2. Create a GitHub personal access token from [here](https://github.com/settings/tokens), with atleast **repo** rights. Store this token in the file [GitHub_PAT](GitHub_PAT.txt). If you are using databricks version of the code, you must store this token in the file `dbfs:/FileStore/project/GitHub_PAT.txt`.

3. Run the [readme_downloader.py](readme_downloader.py) script

   ```bash
   $ python readme_downloader.py
   ```

   If you are using databricks version, simply run all the cells of the [notebook](readme_downloader.ipynb).

4. By default the script will download 10 **README.md** files. To change this behavior, edit the number of files to download on line number 43. Similarly, you can change this behavior in the notebook by updating line number 2 in the second code block.
