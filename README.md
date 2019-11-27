Open Video Data
---

This repository stores configuration data for MIT Open's video ingestion.


#### YouTube

In order to add a new YouTube channel, create a file with the extention `.yaml` in the `youtube/` directory. The format of the file should follow this structure:

```yaml
---
channel_id: CHANNEL_ID
offered_by: OCW  # optional, defaults to none. If set, it shows up as a new facet value
playlists:  # List of youtube playlists to import (at least 1) *
  - id: PLAYLIST_ID1
    create_user_list: false  # optional field, defaults to yes
  - id: PLAYLIST_ID2
```

Notes:
- The comments (the part after `#`) in the example above are purely documentative, you may remove them or leave them in your actual configuration file.
- The channel_id is usually in the url of the channel (e.g. https://www.youtube.com/channel/UCTBMWu8yshnAmpzR3MoJFtw). For older channels (e.g. https://www.youtube.com/user/MIT) that's not immediately visible. See https://stackoverflow.com/a/16326307
