# Importing playlists

Nuclear is able to import playlists from Spotify and Youtube, it can also import editorials from Deezer (playlists made by Deezer).

## Importing from Spotify

1. Go to `Playlists` (on the left)
2. Click `Add`, and then `Import from Spotify`:

<figure><img src="../.gitbook/assets/image (14).png" alt="" width="238"><figcaption><p>Where the <code>Import from Spotify</code> button is located</p></figcaption></figure>

3. Paste your playlist's URL into the input box and click "Import"

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="375"><figcaption><p>Import dialog</p></figcaption></figure>



{% hint style="info" %}
The format of the URL should look like this: [https://open.spotify.com/playlist/37i9dQZF1DWWQRwui0ExPn](https://open.spotify.com/playlist/37i9dQZF1DWWQRwui0ExPn)
{% endhint %}

4. Nuclear will start importing the playlist you selected. Give it some time to do it. If it's less than a 100 tracks, it should be pretty much instant, with 500-100 it takes a couple of seconds. Nuclear will show that the playlist came from Spotify.

<figure><img src="../.gitbook/assets/image (16).png" alt="" width="375"><figcaption><p>Imported Spotify playlist</p></figcaption></figure>

5. You can now play the playlist. To save the playlist locally, use the `Save locally` button.

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="324"><figcaption></figcaption></figure>

Afterwards, the playlist will be found in the `Playlists` section.

## From Deezer

Nuclear displays the editorial playlists from Deezer in the `Dashboard` section.

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="375"><figcaption><p>The editorial playlists from Deezer</p></figcaption></figure>

Click the playlist you want to listen to. If you save it locally, you can then edit it:

<figure><img src="../.gitbook/assets/image (19).png" alt="" width="375"><figcaption><p>Saving the Deezer playlist locally</p></figcaption></figure>

## From Youtube

1. You're going to need a playlist link that looks like this: [https://www.youtube.com/playlist?list=PLWMjC05R8fbWlVwjhRx2E2jhdreZLr12c](https://www.youtube.com/playlist?list=PLWMjC05R8fbWlVwjhRx2E2jhdreZLr12c)
2. To get this link, you have to go to the playlist view on Youtube, not to a video in the playlist.
3. If you're in a view where a video from the playlist is playing, and the rest of the playlist is in the sidebar, you can go directly to the playlist view by clicking its name:

<figure><img src="../.gitbook/assets/image (6).png" alt="A Youtube screenshot showing where to click to go to the playlist view" width="375"><figcaption><p>Location of the playlist link</p></figcaption></figure>

&#x20;

4. Paste the playlist link directly into Nuclear's search box. If you do it correctly, you should see a list of all the tracks in the playlist:

<figure><img src="../.gitbook/assets/image (12).png" alt="" width="375"><figcaption><p>How to import a Youtube playlist</p></figcaption></figure>



5. Now you can add them all to your play queue, and save the queue as a playlist by clicking the three dots above the queue.

Youtube import is still being developed, and it will likely follow the same process as Spotify and Deezer in the future.

## From JSON File

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

