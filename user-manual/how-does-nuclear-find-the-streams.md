---
description: Where is the music from?
---

# How does Nuclear find the streams?

Are you curious about how Nuclear, an open-source project, can offer a vast array of music? Unlike platforms such as Spotify or Tidal, Nuclear doesn't host any music on its servers. Instead, all the music is provided by third-party sources such as YouTube.

### How does Nuclear know what tracks to stream?

When you add a song to your queue, Nuclear only requires two pieces of information: the artist and title of the track. With this information, Nuclear searches using the chosen streaming provider, such as YouTube, and obtains a list of potential streams. The program then selects the stream that is most likely to be the one you want to play, based on various heuristics.

As a result of this process, you may occasionally hear a different track or something entirely unexpected. This matching process is partly based on guesswork, and although the developers have made many tweaks to it over time, there is still room for error.

Despite the potential for inaccuracies, Nuclear offers an impressive selection of music and allows you to easily access a wide variety of songs. Additionally, if you notice any discrepancies between the track you requested and the one that was played, you can submit a report via Nuclear's GitHub repository. The developers are continuously working to improve the accuracy of Nuclear's track selection and appreciate any feedback from users.

{% hint style="info" %}
To change the stream selected by Nuclear, simply right-click the track and choose a new source from the dropdown menu.

\
![](<../.gitbook/assets/image (9).png>)![](<../.gitbook/assets/image (1).png>)
{% endhint %}
