# Debrid Media Organizer
## _A Real-Debrid Quasi-Clone Media Library Curator_

![Static Badge](https://img.shields.io/badge/Version-2.0.4-brightgreen) ![Static Badge](https://img.shields.io/badge/Python-3.10%2B-brightgreen)

Debrid Media Organizer is a Python script designed to help real-debrid cloud service users efficiently organize and maintain a highly structured, portable media collection on a remote or local drive. By iterating through user's cloud torrent library, Debrid Media Organizer identifies whether each folder contains a movie or a TV show. It then leverages the python-torrent-title (PTN) library (version 2.5) to parse the torrent name and extract relevant media information. Based on this information, the script organizes a folder hierarchy on a user-specified drive location and populates it with .strm files containing links to the media resources.

## Table of Contents
1. [Features](#features)
2. [Usage](#usage)
3. [Configuration](#configuration)
4. [Scheduled Task](#scheduled-task)
5. [Plugins](#plugins)
5. [Contributing](#contributing)
6. [License](#license)


## Features
Debrid Media Organizer offers several features to enhance your media organization and access experience:

- **Media Detection:** Automatically identifies whether a folder contains a movie or a TV show.
- **Metadata Extraction:** Utilizes the PTN library to extract metadata from folder names.
- **Structured Hierarchy:** Creates a well-structured folder hierarchy based on media information.
- **.strm Files:** Generates .strm files with renewed links every 7 days to ensure continuous access.
- **Compatibility:** Works seamlessly with Kodi, ~~Plex~~, Emby, and similar media players.
- **Low-Powered Device Access:** Allows users to access their cloud media collection on low-powered devices.
- **Portability:** The portable quasi-clone can be easily mounted on different devices.

## Usage
Before you can use Debrid Media Organizer, you'll need to install Python (version >3.10) and ensure you have the necessary dependencies. Follow these steps to get started:
1. Clone this repository to your local machine:
    ```sh
    git clone https://github.com/Renoria/Drive2CloudSync
    ```
2. Navigate to the project directory:
    ```sh
    cd Drive2CloudSync
    ```
3. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```
3. Make a copy of `settings.example.py` file:
    ```sh
    cp settings.example.py settings.py
    ```
4. Edit and add appropriate API keys in `settings.py` file
5. Edit source and destination paths in `settings.py` file
6. Run the script by using the following command:
    ```sh
    python cataloguer.py -h
    ```
7. Monitor `status.log` file for info, errors & exceptions

## Configuration
Debrid Media Organizer allows for some customization through its configuration file. To configure the script to your preferences, follow these steps:

Open the `settings.py` file in the project directory.

Modify the following settings as needed:

`DEST_ROOT`: The destination drive location where the nicely-named & sophisticatedly structured hierarchy will be created.

`FOLDER_CHECK_FREQUENCY`: Amount of time in seconds after which the cloud library should be checked for changes.

`RESET_COUNTER`: The amound of hours after which the whole cloud library should be re-iterated for dead-links

`CORRECTIONS_FILE_LOCATION`: The corrections.csv file location which will used to track user asserted corrections.

## Scheduled Task
For convenience, consider setting up a scheduled task (e.g., using cron on Unix-like systems) to run Debrid Media Organizer at your preferred event. This ensures your media collection remains updated without manual intervention.

Example for running Debrid Media Organizer at every reboot:
`@reboot /usr/bin/python /path/to/drive2cloudsync/cataloguer.py --keep-running`

Alternatively, it can be run just once every few hours:
`* 0/4 * * * /usr/bin/python /path/to/drive2cloudsync/cataloguer.py`

## Plugins

~~Debrid Media Organizer is currently dependent on the following projects.~~
De-coupled from rclone_RD to make this tool standalone.
Nonetheless, itsToggle's rclone_RD is a very a resourceful tool which will greatly help you in keeping your real-debrid torrent media library alive, so you should probably install it.
Instructions on how to use them are linked below.

| Plugin | README |
| ------ | ------ |
| Rclone_RD | [rclone_RD/README.md][rclone_readme] |

## Contributing
If you'd like to contribute to this project, please follow these guidelines:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them with clear, concise commit messages.
4. Push your changes to your fork.
5. Create a pull request with a detailed description of your changes.

Your pull request will be reviewed, and your contributions are greatly appreciated!

## License
This project is licensed under the [MIT License]. Feel free to use, modify, and distribute it according to the terms of the license.

   [rclone_RD]: <https://github.com/itsToggle/rclone_RD>
   [rclone_readme]: <https://github.com/itsToggle/rclone_RD/blob/master/README.md>
   [MIT License]: <https://mit-license.org/>
