Open Video Data
---

This repository stores configuration data for MIT Open's video ingestion.


#### YouTube

In order to add a new YouTube channel, create a file with the extention `.yaml` in the `youtube/` directory. The format of the file should follow this structure:

```yaml
---
channel_id: CHANNEL_ID
offered_by: OCW  # optional, defaults to none
playlists:  # may include one or more playlists
  - id: PLAYLIST_ID1
    create_user_list: false  
  - id: PLAYLIST_ID2
    user_list_title: A custom name 

```

The following options are supported for playlists:
- `create_user_list` - Defaults to True. If true, a user list is created for the playlist
- `user_list_title` - Specifies the title of the userlist that is created. Defaults to the title of the playlist on youtube.

Optionally `id: all` can be used to indicate the desired default behavior for the playlists in the channel. Setting for individual playlists overwrite the behavior set by all.  `ignore: true`  can be used with `all` to specify that videos from a playlist should not be added to the course catalog.


```yaml
---
channel_id: CHANNEL_ID
offered_by: OCW 
playlists: 
  - id: all
    create_user_list: true
  - id: PLAYLIST_ID1
    create_user_list: false  
  - id: PLAYLIST_ID2
    ignore: true 

```

In the above example, videos from all playlists for the channel that are not specifically included in the config file are added to the course catalog and user lists are created for those playlists. The videos for `PLAYLIST_ID1` are added to the course catalog but no user list is created.  `PLAYLIST_ID2` is ignored completely.

### Uploads playlist
Every youtube channel has an "uploads" playlist. To get the uploads playlist id go to the "Videos" tab for the channel and click "Play All". The upload playlist id will be the `list=<playlist id>` parameter in the URL
