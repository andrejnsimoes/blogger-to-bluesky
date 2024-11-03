# Blogger to Bluesky Auto-Poster

This GitHub Action automatically posts new entries from your Blogger RSS feed to your Bluesky account. It runs every 4 hours and ensures no duplicate posts are made.

## Setup Instructions

1. **Fork or Clone this Repository**
   - Click the "Use this template" button or fork this repository
   - Give it a name like `blogger-to-bluesky`

2. **Create Required Secrets**
   Navigate to Settings > Secrets and Variables > Actions and add these secrets:
   - `BLUESKY_HANDLE`: Your Bluesky handle (e.g., `username.bsky.social`)
   - `BLUESKY_PASSWORD`: Your Bluesky app password (create one at https://bsky.app/settings/app-passwords)
   - `RSS_FEED_URL`: Your Blogger RSS feed URL (usually `https://yourblog.blogspot.com/feeds/posts/default`)
   - `MAX_POSTS`: Number of recent posts to check from the RSS feed (optional, defaults to 10)

3. **Enable GitHub Actions**
   - Go to the "Actions" tab
   - Click "I understand my workflows, go ahead and enable them"

## How It Works

- The action checks your Blogger RSS feed every 4 hours
- Processes only the most recent posts (controlled by MAX_POSTS)
- New posts are automatically shared on your Bluesky profile
- Each post includes:
  - The blog post title
  - A preview card with thumbnail and description
- A tracking file (`posted_entries.json`) prevents duplicate posts

## Manual Trigger

You can manually trigger the action:
1. Go to the "Actions" tab
2. Select "RSS to Bluesky Poster"
3. Click "Run workflow"

## File Structure

```
.
├── .github
│   └── workflows
│       └── bluesky-rss.yml
├── posted_entries.json
└── README.md
```

## Troubleshooting

Check the Actions tab for execution logs if posts aren't appearing:
1. Click on the "Actions" tab
2. Select the latest workflow run
3. Review the logs for any error messages

## Contributing

Feel free to open issues or submit pull requests if you have suggestions for improvements!
