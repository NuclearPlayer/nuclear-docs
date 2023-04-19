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

### Directly in Nuclear

Nuclear is able to import Spotify and Youtube playlists. This is the preferred method, but it's based on scraping, so it can be wonky. We're working on improving it so it's more reliable, but it's a cat and mouse game.

#### To import from Spotify:

* Go to Playlists and click this button (at the top): <img src="../.gitbook/assets/image (5).png" alt="A button with a label saying &#x22;Import from URL (Spotify)&#x22;" data-size="line">
* Paste your playlist's URL into the input box and click "Import"
* Nuclear should start importing the playlist. If it works, you should see progress within a couple of seconds. If it stays at 0%, don't wait for it more than 10s.
* If it hangs, you can retry by following this process again. Sometimes restarting Nuclear also helps.
* If it doesn't work after 2-3 retries, it's probably not going to work for that playlist. You can try telling us about that on [Discord](https://discord.gg/JqPjKxE) or [Github](https://github.com/nukeop/nuclear/issues). If you link your playlist we might be able to fix that in a future release.

#### To import from Youtube:

* You're going to need a playlist link that looks like this: [https://www.youtube.com/playlist?list=PLWMjC05R8fbWlVwjhRx2E2jhdreZLr12c](https://www.youtube.com/playlist?list=PLWMjC05R8fbWlVwjhRx2E2jhdreZLr12c)
* To get this link, you have to go to the playlist view on Youtube, not to a video in the playlist.
*   If you're in a view where a video from the playlist is playing, and the rest of the playlist is in the sidebar, you can go directly to the playlist view by clicking its name:

    <figure><img src="../.gitbook/assets/image (6).png" alt="A Youtube screenshot showing where to click to go to the playlist view"><figcaption></figcaption></figure>

    &#x20;
*   Paste the playlist link directly into Nuclear's search box. If you do it correctly, you should see a list of all the tracks in the playlist:

    <figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>


* Now you can add them all to your play queue, and save the queue as a playlist by clicking the three dots above the queue.

### extract-sptf-playlist tool

You can use this tool ([https://github.com/NuclearPlayer/extract-sptf-playlist](https://github.com/NuclearPlayer/extract-sptf-playlist)​) to extract the JSON playlist file from Spotify and Youtube. Since this is already built into Nuclear, the script is less convenient and not preferred.\
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

