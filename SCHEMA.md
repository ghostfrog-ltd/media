# SCHEMA.md
### YouTube Ops Database (PostgreSQL)

```sql
-- Track individual video performance vs. generation cost
CREATE TABLE IF NOT EXISTS video_factory (
    id SERIAL PRIMARY KEY,
    created_at TIMESTAMPTZ DEFAULT CURRENT_TIMESTAMP,
    niche_topic TEXT,
    veo_clip_path TEXT,
    lyria_track_path TEXT,
    yt_video_id VARCHAR(50),
    views_count INTEGER DEFAULT 0,
    retention_score DECIMAL(5, 2)
);

-- Monitor Gemini Advanced Quota usage
CREATE TABLE IF NOT EXISTS quota_log (
    date DATE PRIMARY KEY,
    veo_count INTEGER DEFAULT 0,
    nano_banana_count INTEGER DEFAULT 0
);