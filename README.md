# ohbstudio-pixel.github.io

Developer website for OHB Studio, served by GitHub Pages at
https://ohbstudio-pixel.github.io/

| Path | What it is |
|---|---|
| `/privacy/` | iOS privacy policy for Who Knows Kenya. Linked from the App Store listing. Keep Android wording out of it - App Review rejects a policy that mixes in the other platform. |
| `/privacy/android/` | Android privacy policy for Who Knows Kenya (ads, Play Games, Play Billing). Linked from the Play listing. |
| `/app-ads.txt` | Authorised ad sellers for every app that lists this site as its developer website. |

## Why everything lives in this one repo

`app-ads.txt` is only read from the **root** of the developer website listed on
the store page (`https://<domain>/app-ads.txt`). A GitHub account has exactly
one root site - this repo. Any other repo is served from a sub-path, where ad
networks never look.

## Updating app-ads.txt

One file serves every app on this domain, so it is split into sections by ad
SDK (`# LevelPlay`, `# Appodeal ...`). When an SDK's dashboard asks for an
update, add the missing lines under that SDK's section, commit, and push.
**Never replace the file wholesale** - that silently de-authorises the other
SDK's sellers and their fill drops.

The Appodeal section is Appodeal's published list from
https://appodeal.com/app-ads.txt, minus lines already present in the
LevelPlay section.

`.nojekyll` stops GitHub Pages from running Jekyll over the site.
