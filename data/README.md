# Dataset provenance

`tiktok_dataset.csv` is the unchanged synthetic educational CSV provided with the course lab. It is not real TikTok user data.

- Observed shape: 19,382 rows × 12 columns.
- The course dictionary states 19,383 rows; the cause of this difference is unknown.
- Same 298 rows lack `claim_status`, `video_transcription_text` and the five engagement counts.
- No duplicated records or repeated video IDs.
- Original data are retained; no cleaning or imputation has been applied to the CSV.
- SHA-256: `94512709a3fe757ab676584336ef8f8713aa2c3a498f892ac8390b5301b3777b`

## Fields

| Field | Meaning | Lab dtype |
|---|---|---|
| # | Supplied sequential record identifier | int64 |
| claim_status | Claim or opinion label | object |
| video_id | Video identifier | int64 |
| video_duration_sec | Duration in seconds | int64 |
| video_transcription_text | Spoken-content transcription | object |
| verified_status | Author verification category | object |
| author_ban_status | Active, banned or under review | object |
| video_view_count | Views | float64 |
| video_like_count | Likes | float64 |
| video_share_count | Shares | float64 |
| video_download_count | Downloads | float64 |
| video_comment_count | Comments | float64 |

Dtypes reflect the original lab environment; pandas versions may infer string types differently. Counts are discrete even when stored as floats. Source data and course materials retain their respective rights; this project does not assign them a new license.
