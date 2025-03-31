name: Latest blog post workflow
on:
  schedule: # Runs every hour
    - cron: '0 * * * *'
  workflow_dispatch: # Allows manual triggering

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: gautamkrishnar/blog-post-workflow@v1
        with:
          max_post_count: "5" # 显示最近 5 篇
          feed_list: "你的博客 RSS feed 链接" # 替换成你的 RSS 链接
