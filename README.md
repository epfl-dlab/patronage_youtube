# Characterizing Patronage on YouTube

- [Project plan](https://docs.google.com/document/d/1bepoDivLu2HQbNpobFW2bgolxljEC571mYp5zGtnV3M/edit)
- [Weekly updates](https://docs.google.com/document/d/1wgBpiViQH2K2i5I0ULRKUHqklsiHvx57bRuVCs_8uSU/edit#)

## Files and brief explanation of those

All data is located in `/dlabdata1/youtube_large/`

**YouNiverse dataset:**

- `df_channels_en.tsv.gz`: channel metadata.
- `df_timeseries_en.csv.gz`: channel-level time-series.
- `df_videos_raw.jsonl.gz`: raw video metadata.
- `youtube_comments.tsv.gz`: user-comment matrices.
- `youtube_comments.ndjson.zst`: raw comments — this is a HUGE file.

**Graphteon dataset:**
- `creators.csv` list with all creator names.
- `final_processed_file.json.gz` all graphteon time-series.
- `pages.zip` raw html of the pages in graphteon.