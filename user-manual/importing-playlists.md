# Importing playlists

## By JSON File

You can import a JSON playlist file with the following structure:

```javascript
  {
    "name": "playlist name",
    "numberOfTrack": 105,
    "source": "youtube",
    "tracks": [
      {
        "index": 1,
        "id": "xxxxxx",
        "thumbnail": "image_url",
        "title": "track title",
        "album": "album name",
        "duration": "3:40",
        "artist": "artist name",
        "streams": [
          {
            "source": "youtube",
            "id": "xxxxxx"
          }
        ]
      },
    ]
  }
```

* `source` and `id` fields help Nuclear pull streams correctly from `stream provider`.
* `streams` field is only needed when you don't define the `source` field at the top level. This happens when the playlist is not from a single source.

## Spotify / Youtube

You can use this tool ([https://github.com/NuclearPlayer/extract-sptf-playlist](https://github.com/NuclearPlayer/extract-sptf-playlist)​) to extract the JSON playlist file from Spotify and Youtube.\
This tool uses puppeteer package to fetch data and requires nodejs in your system.) to extract the JSON playlist file from Spotify and Youtube.\
This tool uses puppeteer package to fetch data and requires nodejs in your system.[nodejs](https://nodejs.org/en/) in your system.

First, open your ternimal and make an empty directory then point to the new directory and install the package by this command:

```bash
npm install --save extract-sptf-playlist
```

Then create a file named `index.js` with the following content:

```javascript
const { getSpotifyPlaylist } = require('extract-sptf-playlist');
const url = 'YOUR PLAYLIST URL';

getSpotifyPlaylist(url, {
filePath: 'data.json',
displayProcess: true,
});
```

If it's Youtube playlist, replace `getSpotifyPlaylist` by `getYoutubePlaylist`;

Back to your terminal and execute the file by:

```bash
node index.js
```

The playlist will be exported in the file `data.json` in same directory.

## By Url

Will be implemented as a part of Nuclear Web Services.
