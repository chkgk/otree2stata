# oTree2Stata

## Description
STATA does not play well with variable names that contain dots. When exporting data from oTree, variable names contain dots between model name and variable name (e.g. "player.payoff"). Thus, they cannot be used in STATA easily.

This command line utility takes oTree data export files for individual apps (in csv format; not the combined all apps file!) and converts its column headers to form suitable variable names. 

Model prefixes ("player", "group", etc.) are removed. If this would result in duplicate column header names (e.g. "player.payoff" and "participant.payoff"), the dot between model and variable name is replaced with an underscore ("_") instead.

The original data file is left untouched. A file with updated column names is created in the same directory with "_stata" appended to the original filename.

## Requirements
This script requires Python 3.5 or newer to be installed.

## Usage
- clone this repository or download otree2stata.py separately
- place otree2stata.py in the same directory as your app-specific data file exported by oTree in csv format. 
- run the script on each app-data file individually, providing the filename as an argument.

Example:
```bash
python otree2stata.py risk_data_2019_12_02.csv
```

The script will not produce any output, but will create a new file  ```risk_data_2019_12_02_stata.csv``` in the same directory.