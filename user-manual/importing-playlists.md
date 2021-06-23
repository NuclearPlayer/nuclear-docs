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

You can use this tool \([https://github.com/HaiDang666/extract-sptf-playlist](https://github.com/HaiDang666/extract-sptf-playlist)\) to extract the JSON playlist file from Spotify and Youtube. After downloading, the simplest way is to edit the url in `example.js`.

## By Url

Will be implemented as a part of Nuclear Web Services.

