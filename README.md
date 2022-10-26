# video-info

## Description

This Bash script is used to get the video information from a video file.
Besides metadata of local files, it can also get information about media on Twitch, YouTube, TikTok, and Instagram, including data about the uploader.


## Features

Get the following information about videos from the following sources:

**Twitch VODs**
````
Streamer Name
Stream Title
Duration
Start Time
Viewer Count
Available Resolutions and approx. File Sizes
Chapters (in a table with: Start Time | End Time | Current Game)
````

**YouTube**

````
Channel Name
Channel Follower Count
Upload Date
Video Title
View Count
Like Count
Duration
Category
Tags
Chapters (in a table with: Start Time | End Time | Chapter Title)
````

**TikTok**

````
Uploader & Creator Name
Video Title
Description
Upload Date & Time
View Count
Like Count
Comment Count
Repost Count
Duration
Track
Artist
````

**Instagram Videos/Reels** _(unstable and may require authentication)_
````
Uploader
Channel
Like Count
Comment Count
Duration
Upload Date & Time
Title
Description
````

**Local Files**

````
Video Title
Duration
Resolution
FPS
Video Codec
Video Bitrate
Audio Codec
Audio Bitrate
Description & Comment tags (if available)
Chapters (in a table with: Start Time | End Time | Chapter Title) (if available)
````

## Dependencies

The following dependencies are required to use parsers:
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) (all platforms)
- [Streamlink](https://streamlink.github.io/) (Twitch)
- [ffprobe](https://ffmpeg.org/download.html) (local files)
- [jq](https://stedolan.github.io/jq/) (all platforms & local files)

macOS users also need to install the following via [Homebrew](https://brew.sh/):
- `gdate` via the [coreutils](https://formulae.brew.sh/formula/util-linux) package (all platforms, local)
- `column` via the [util-linux](https://formulae.brew.sh/formula/util-linux) package (local)

The path to `column` has to be manually entered into the `column_path` variable.

## Installation

Windows users need to use Cygwin or WSL to run Bash scripts. Most Linux distributions and macOS[^1] should already have Bash installed.

Simply download [video-info](https://github.com/anga83/video-info/blob/main/video-info) from the files above and save it in a convenient place. Like all Bash scripts, the file has to be marked as executable. To do this, open a terminal window and paste `chmod +x /path/to/video-info`. Once that is done, you can double-click it to run.

If you don't already have it installed you also need to install [yt-dlp](https://github.com/yt-dlp/yt-dlp).
Ubuntu users should note that Ubuntu 22.04 LTS has an old version of yt-dlp in its package repositories, which may cause the fetching metdata to fail. Check the link above to update to the latest version.

## Usage

Depending on your operating system, launching the script may differ, but in general there are three ways:
- macOS: remove the `.sh` file extension, now you can simply double-click to launch
- Ubuntu: right click and choose "Run as a Program" (there are tutorials to make double-click work as well)
- any OS: open a Terminal window, navigate to the script directory and enter `./tiktok-downloader.sh`

Once launched, choose the mode you want to use and the script will assist you through the necessary steps to get your files.

In all prompts you can enter 'q', 'quit' or 'exit' to exit the program.


## Notes

Obviously, all social media platforms are constantly changing and information may become unavailable. Under the hood, this script uses yt-dlp to get all available information. Keep it updated to avoid errors. To fetch data from Instagram it may become necessary to import your brwoser cookies to yt-dlp.

macOS now uses zsh as default shell and hasn't updated Bash for ages. The script doesn't do that crazy stuff, but issues may still arise. You may update Bash via [Homebrew](https://formulae.brew.sh/formula/bash).
