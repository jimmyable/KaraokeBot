
[ReFrameWork Documentation](https://github.com/UiPath/ReFrameWork/blob/master/Documentation/REFramework%20documentation.pdf)

# KaraokeBot

Song Requests can be entered [here](https://forms.gle/KGRwkUqnQywJEXmi9)

Orchestrator Queues and Assets can be set up [here](http://platform.uipath.com/)

## This Process has two main Pieces

### DispatcherBot
- Scrape data from Google Forms for Song, and Singer Name from [here](https://docs.google.com/forms/d/1a07MoJb2u9udNp5TFb_uP-d0ocRSelcYF0muXCBiKSM/edit#responses)
- Upload it to a an Orchestrator Queue called `Song_Queue`


### Main

#### Init

- Open `iexplore.exe` and Navigate to YouTube
- Open `WINWORD.exe` and open a blank Document and TypeAndSpeak the welcome message

#### Get Transaction
- Get each transaction item(Song/Singer Name)

#### Process
- TypeAndSpeak *Round_number*, *Song_Name*, *Singer*
- Navigate to Youtube and load the corresponding Karaoke song
- Fullscreen the video, skip all ads and wait for video finish(appearance of the `Replay` button)

- TypeAndSpeak "Rate Performance", with a input dialog
- Scores are send to Orchestrator Queue `Score_List`

#### End Process

- End Process by retriveing `Score_List` and identifying the Winner using highest score
- Navigate to Google Images, search for an acceptable song cover photo
- Navigate to Google Drive, create an empty presentation, fill with content and use **Explore** to auto-format it

- Display Winner, kill both apps
