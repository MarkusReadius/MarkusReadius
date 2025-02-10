# Technical Context

## Technologies Used
- GitHub-flavored Markdown (GFM)
- Shields.io API
- GitHub README Stats API
- GitHub Actions (optional for blog updates)
- Komarev Profile Views Counter

## Development Setup
1. Repository Requirements
   - Must be named exactly "MarkusReadius"
   - Must be public
   - Must contain README.md in root directory

2. External Services
   - shields.io for badges
   - github-readme-stats.vercel.app for stats cards
   - komarev.com for view counter

3. GitHub Actions Setup (Optional)
   ```yaml
   name: Blog Posts
   on:
     schedule:
       - cron: '0 */24 * * *'
   jobs:
     update:
       runs-on: ubuntu-latest
       steps:
         - uses: gautamkrishnar/blog-post-workflow@master
           with:
             feed_list: "your-rss-feed-url"
   ```

## Technical Constraints
1. Image Limitations
   - All images must be publicly accessible
   - SVG files must be from trusted sources
   - Badges must use approved shield.io endpoints

2. Markdown Restrictions
   - Limited HTML support
   - No JavaScript execution
   - No CSS styling (except GitHub-supported attributes)

3. API Rate Limits
   - GitHub Stats API has rate limiting
   - Shield.io has usage limits
   - Consider caching for high-traffic profiles

## Dependencies
- None required locally
- All external services are web-based
- No package management needed
