Source: https://www.noesisengine.com/docs/App.MediaElement._MediaPlayer.html

# MediaPlayer Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Abstract class for the implementation of audio/video in a [MediaElement](/App.MediaElement/_MediaElement.md).

Each platform must provide an implementation for this class and pass it to [MediaElement](/App.MediaElement/_MediaElement.md) by calling *MediaElement::SetCreateMediaPlayerCallback*.

# Inheritance Hierarchy

• *MediaPlayer*

# Properties

| Name | Description |
| --- | --- |
| ○ *Balance* | Gets or sets the balance between the left and right speaker volumes, represented in a range between -1 and 1. The default is 0 |
| ○ *BufferingProgress* | Gets the percentage of buffering completed for streaming content, represented in a value between 0 and 1 |
| ○ *CanPause* | Gets a value indicating whether the media can be paused |
| ○ *DownloadProgress* | Gets the percentage of download progress for content located at a remote server, represented by a value between 0 and 1. The default is 1 |
| ○ *Duration* | Gets the duration in seconds of the media |
| ○ *Height* | Gets the pixel height of the video |
| ○ *IsMuted* | Gets or sets a value that indicates whether the media is muted. The default is false |
| ○ *Position* | Gets or sets the current position in seconds of the media |
| ○ *ScrubbingEnabled* | Gets or sets a value that indicates whether the media player will update frames for seek operations while paused. The default is false |
| ○ *SpeedRatio* | Gets or sets the ratio of speed that media is played at, represented by a value between 0 and the largest float. The default is 1 |
| ○ *Volume* | Gets or sets the media's volume, represented on a linear scale between 0 and 1. The default is 0.5 |
| ○ *Width* | Gets the pixel width of the video |

● Dependency Property   ○ Reflection Property

# Attached Properties

MediaPlayer has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *GetTextureSource()* | Gets the texture source for rendering the video |
|  *HasAudio()* | Gets a value that indicating whether the media has audio output |
|  *HasVideo()* | Gets a value that indicates whether the media has video output |
|  *Pause()* | Pauses media playback |
|  *Play()* | Starts or resumes media playback |
|  *Stop()* | Stops media playback and moves position to the begining |

# Events

| Name | Description |
| --- | --- |
| ◆ *BufferingEnded* | Occurs when buffering has finished |
| ◆ *BufferingStarted* | Occurs when buffering has started |
| ◆ *MediaEnded* | Occurs when the media has finished playback |
| ◆ *MediaFailed* | Occurs when an error is encountered |
| ◆ *MediaOpened* | Occurs when the media is opened |

▸ Routed Event    Non-routed Event   ◆ Delegate Event