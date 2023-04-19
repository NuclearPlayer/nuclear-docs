# Stream verification

You might have noticed this box under your play queue:\
\
![](<../.gitbook/assets/image (2).png>)\
\
This lets you **verify** a stream, confirming that it's the correct one for the song that you're listening to right now. This works a little like [Sponsorblock](https://sponsor.ajay.app/) - you verify that this stream is alright, and other people will then benefit from your verification.

Normally, Nuclear selects streams based on [search results and heuristics](how-does-nuclear-find-the-streams.md).\
\
With verification, the stream the most people have verified will be selected first if you're using this feature. This lets us increase the accuracy of streams over time.

### How it works

The box applies to the currently playing track and can be in one of five states:

#### Unknown

![](<../.gitbook/assets/image (3).png>)

This probably means it's still loading, or maybe the verification service errored out. Either way you can't verify it, and you don't know which streams are verified. Nuclear keeps working as normal.

#### Unverified

![](<../.gitbook/assets/image (11).png>)

There are no entries for this song. Maybe you're the first one listening to it. If what you're hearing sounds correct, click the **Verify** button to help others out. If it doesn't, right click the track, and try manually changing the stream to something else.

#### Verified by you

![](<../.gitbook/assets/image (4).png>)

This means you've already marked this stream as verified for this track earlier. In addition to helping others, this stream will now play for you automatically, overriding Nuclear's default mechanism, even if other people verify different streams for this song. You can correct Nuclear's normal stream selection permanently this way.\
You can retract your verification by using the **Unverify** button.

#### Weakly verified

![](<../.gitbook/assets/image (7).png>)

Only a couple people have verified this stream (less than 3). It might mean it's still correct, and you can strengthen the verification by clicking the **Verify** button.

#### Verified

The stream has been verified by more than 2 people, and it's prioritized when selecting what to play. You can still verify it yourself if you want.

### How does it know it's me?

You may be wondering how Nuclear knows that you have verified a stream and what data it sends to the servers to make this work.

* A unique user ID is generated in Nuclear. This is just a GUID string.
* If you click **Verify,** the server receives this id, plus the artist, title, selected streaming source, and the stream id to be verified and saves it.
* When you play songs, a request is sent to check if the stream has any verifications, and if your user id has already verified it. It returns the top stream id along with its score.
* Yes, this can be used to track what you're listening to. This backend service is [publicly available under AGPL 3.0](https://github.com/NuclearPlayer/nuclear-verification-service).&#x20;
* Even then, you have to take my word for it that this is what's really running on the server. If you don't like it, you can disable this feature altogether in the settings. In the future I will also introduce an option to use your own server for this, but it's going to be useless if only one person is participating.
* Pinky promise I'm not using this for tracking anyone. This information is useless to me, and isn't saved anywhere. I have no way of connecting the user ID to any particular people.
