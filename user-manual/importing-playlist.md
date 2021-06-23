# Importing playlist

## By Json File
You can import a json playlist file as the following structure:

```json
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

- `source` and `id` fields help Nuclear pull correctly track from `stream provider`.
- `streams` field only need when you don't define `source` field in the top level. This happens when the playlist is not from a single source.

## Spotify / Youtube
You can use this tool (https://github.com/HaiDang666/extract-sptf-playlist) to extract the json playlist file from spotify and youtube, after downloading, the simplest way is editing the url in `example.js`.


## By Url 
comming soon
