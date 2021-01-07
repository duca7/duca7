![Metrics](https://metrics.lecoq.io/duca7?template=classic&languages=1&config.timezone=Asia%2FBangkok)
name: Metrics
on:
  # Schedule updates
  schedule: [{cron: "0 * * * *"}]
  push: {branches: "master"}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # You'll need to setup a personal token in your secrets.
          token: ${{ secrets.METRICS_TOKEN }}
          # GITHUB_TOKEN is a special auto-generated token used for commits
          committer_token: ${{ secrets.GITHUB_TOKEN }}

          # Options
          user: duca7
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Bangkok
          plugin_languages: yes








