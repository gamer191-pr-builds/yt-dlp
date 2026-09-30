# This repo hosts my builds of yt-dlp PRs that aren't merged yet. 

Install builds using `yt-dlp --update-to gamer191-pr-builds/yt-dlp@PR0000` replacing 0000 with the PR number

Open an issue to request a build or ping/DM me on Discord @gamer.191

## Build process:

1. `pr=0000` (replace with PR number)
1. `gh pr checkout $pr -R yt-dlp/yt-dlp -b PR$pr`
1. `git rebase upstream/master`
1. `git diff PR$pr upstream/master`
1. Manually inspect diff for obvious malware
1. `git push --force origin PR$pr:PR$pr`
1. `gh workflow run release.yml -R gamer191-pr-builds/yt-dlp --ref PR$pr -f source=yt-dlp/yt-dlp -f target=gamer191-pr-builds/yt-dlp@PR$pr -f prerelease=true -f linux_armv7l=false`
