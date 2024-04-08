![PBD_Logo](img/pdb_logo_small.png)

# Podcast Bulk Downloader
![example workflow](https://github.com/cnovel/PodcastBulkDownloader/actions/workflows/python-app.yml/badge.svg) [![codecov](https://codecov.io/gh/cnovel/PodcastBulkDownloader/branch/master/graph/badge.svg)](https://codecov.io/gh/cnovel/PodcastBulkDownloader) ![version](https://img.shields.io/badge/Python-3.7%20%7C%203.8%20%7C%203.9%20%7C%203.10%20%7C%203.11-blue)

**Podcast Bulk Downloader** is a simple soft that allows you to download all the episodes of a podcast feed in a folder. This fork writes Podcast descriptions to the Finder comments so it is only useful on macos

## How to use Podcast Bulk Downloader
### CLI version
Usage: `PodcastBulkDownloaderCLI.exe -f FOLDER --url RSS_URL [--overwrite] [-l LAST_N]`

Arguments:
* `-h`, `--help`: shows this help message and exit
* `--url URL`: URL to inspect for MP3s, local path file is also supported
* `-f FOLDER`, `--folder FOLDER`: Destination folder for MP3 files
* `--overwrite`: Will overwrite existing files
* `-l LAST_N`, `--last LAST_N`: Will only download the last N episodes. If N=0, download all the episodes
* `--prefix [NO_PREFIX, DATE, DATE_TIME]`: Optional, choose is you want to prefix with date or date_time
* `-v`, `--version`: Print version

Example:
```
python3 src/bulk_downloader.py -f kolisrael/ --url https://www.omnycontent.com/d/playlist/23f697a0-7e6a-4e96-a223-a82c00962b12/4222a8e4-ca1d-4fe3-88f5-a919008d5a53/34de46c9-e299-44d2-9386-a919008d5a58/podcast.rss```

### GUI Version
![PBD_GUI](img/PBD_GUI_v0.8.png)

It's fairly easy to use: fill the RSS field, click Fetch to inspect the feed.
Then fill the Folder field and click download to download the episodes.
Logs will be displayed in the bottom part and will warn you if the software ran into issues.
Check the overwrite checkbox if you want to redownload all the episodes.
Overwriting is solely based on filename, it doesn't do any checks at the moment.
If you want to download only the last N episodes, check the corresponding box and fill the number of episodes wanted.

## How to build _PBD_
### Build and run tests
We are supporting Python 3.7 and above. Project may work for earlier version tough it is not guaranteed.

To install dependencies, execute this command in the root folder:
```
pip install .
```

To run tests, execute this command in the root folder:
```
pytest -v
```