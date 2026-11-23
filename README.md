# CHOR & more song voting

This repository contains the static song-voting site for the choir [CHOR & more](https://chorandmore.ch/), published at [danielhoop.github.io/chorandmore](https://danielhoop.github.io/chorandmore). It includes the site and its audio samples.

A separate analysis process extracted song names and timestamps from medley PDFs, researched additional information such as artists, and automatically created more than 400 voice-separated audio samples.

## How it works

* GitHub Pages hosts the site. The browser loads song details and audio samples from there.
* The site sends requests to a Google Apps Script to read and update votes. The script's URL is configured in `config.js`.
* The script accesses a Google spreadsheet, reading the shared password and maximum number of selected songs from the `Config` tab and storing votes in the `Stimmen` tab.
* Each browser generates an ID and stores it in local storage to identify its votes. Everyone uses the same password. The default limit is 10 songs per browser and can be changed in the spreadsheet's `Config` tab. Choir members are trusted not to bypass the limit by using multiple browsers or devices.
* Thumbs-up and thumbs-down ratings are stored locally for sorting; rocket votes are sent to the voting service.

Overall, this is a **simple, easy-to-use solution tailored** to a popular vote on the choir's favorite songs.
