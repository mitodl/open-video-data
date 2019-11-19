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
    create_user_list: false  # optional field, defaults to yes
  - id: PLAYLIST_ID2
```

**NOTE:** the comments (the part after `#`) in the example above are purely documentative, you may remove them or leave them in your actual configuration file.
