# PikPak Kodi Setup: How to Stream Your Cloud Library on Kodi — WebDAV Method, MediaFusion Integration, Step-by-Step Guide + Full Plan Comparison

So you've got a PikPak drive sitting in the cloud, loaded with movies and shows your local storage can't hold, and you're staring at Kodi wondering why these two things aren't talking to each other yet. Good news: they absolutely can. The combination is genuinely great once it's running — Kodi handles the interface and playback, PikPak handles the 10TB of cloud storage and the blazing-fast server-side downloads that got all those files there in the first place.

There are two main ways to connect PikPak and Kodi. The first is through **WebDAV**, where you mount your PikPak drive directly as a network media source inside Kodi. The second is through **MediaFusion**, an open-source streaming addon that supports PikPak as a debrid-style provider for on-demand content. Both methods work, and they serve slightly different use cases. This guide covers both — plus everything you need to know about PikPak's plans before you commit.

---

## What Makes PikPak Worth Setting Up with Kodi

Before getting into the steps, it helps to understand what PikPak actually does, because it's not just another cloud drive.

The core idea is simple: you paste a torrent link, magnet URL, or direct download link into PikPak, and PikPak's own servers grab the file for you — at enterprise-level bandwidth. More than 80% of files land in your private cloud library within seconds, regardless of your local internet speed. Once the file is there, it stays in your 10TB drive until you decide to delete it.

Pair that with Kodi, and you've essentially built a personal media server that's always online, requires zero local storage, and can stream in 4K without buffering. It's a setup a lot of people pay significantly more to replicate across a seedbox, a NAS, and a streaming server subscription. PikPak collapses it into one service.

👉 [Start with PikPak — register free, no credit card required](https://bit.ly/PIkpak)

---

## Method 1: PikPak Kodi Setup via WebDAV (Best for Personal Libraries)

This is the cleaner approach if your goal is to browse and stream your own PikPak file library directly from Kodi. WebDAV lets you mount your PikPak cloud drive as a network location — Kodi treats it like a regular folder, you navigate to a file, hit play, and it streams directly from the cloud.

**Step 1: Get PikPak Premium**

WebDAV access is a Premium-only feature on PikPak. The free tier gives you 6GB of storage and the core download functionality, but you won't see the WebDAV option until your account is upgraded to Premium.

If you're new to PikPak, signing up with invitation code **74098243** gives you a chance at bonus free Premium days before any payment is needed.

👉 [Upgrade to PikPak Premium](https://bit.ly/PIkpak)

**Step 2: Enable WebDAV in Your PikPak Settings**

Log into your PikPak account on the web, then follow these steps:

1. Navigate to **Settings → Access & Integrations → WebDAV**
2. Toggle WebDAV **on**
3. Click **Create WebDAV Credential**
4. PikPak will display your WebDAV **server address**, **username**, and **password**

Write these down — you'll need all three in Kodi. Keep the credentials secure and don't share them. You can revoke WebDAV access at any time without touching your main account password.

> **Important:** PikPak's WebDAV currently supports read operations — browsing, streaming, and downloading files. Write operations like uploading or reorganizing via WebDAV are in active development.

**Step 3: Add PikPak as a Video Source in Kodi**

Open Kodi, then:

1. From the Home screen, go to **Videos → Files**
2. Select **Add videos…**
3. Click **Browse → Add network location**
4. Set the Protocol to **WebDAV server (HTTP)**
5. Enter the **Server address** from PikPak's WebDAV settings (just the hostname portion, without `https://`)
6. Enter the **Username** and **Password** from your PikPak WebDAV credentials
7. Leave the port as default unless PikPak specifies otherwise
8. Click **OK**, give the source a name like "PikPak," and click **OK** again

Kodi now lists PikPak under Files as a permanently browsable source. Navigate through your PikPak folder structure the same way you would in the app — select any video and playback begins, streaming directly from the cloud.

**Step 4: Enable Library Scraping (Optional but Recommended)**

If you want Kodi to pull movie posters, episode data, ratings, and descriptions for your PikPak content — so it looks like a real media library instead of just a file browser — you can configure content type scraping on your PikPak source:

1. Right-click the PikPak source in Kodi's file browser
2. Select **Set content**
3. Choose **Movies** or **TV shows** based on the folder's contents
4. Pick a scraper (TMDb works well for movies, TheTVDB for shows)
5. Run the library scan

After the scan, your PikPak content appears inside Kodi's Movies and TV Shows sections, complete with cover art, summaries, and ratings — looking exactly like a local library.

---

## Method 2: PikPak Kodi Setup via MediaFusion (Best for Discovering New Content)

MediaFusion is an open-source streaming aggregator — a Kodi-native addon that aggregates streams from debrid providers including PikPak. Rather than browsing your existing library, this method fetches cached streams from PikPak's network on the fly when you search for specific movies or TV shows in Kodi.

This method is better suited for people who want to watch new content as they discover it, rather than maintaining a curated personal library.

**Step 1: Install the MediaFusion Addon in Kodi**

1. Open Kodi → **Settings** (gear icon)
2. Go to **System → Add-ons**
3. Toggle **Unknown sources** on — confirm with **Yes**
4. Go back to **Settings → File manager**
5. Select **Add source → \<None\>**
6. Enter the URL: `https://mhdzumair.github.io/MediaFusion`
7. Name the source **MediaFusion** and click **OK**
8. Return to **Add-ons → Install from zip file**
9. Select the **MediaFusion** source you just added
10. Install **repository.mediafusion.zip**
11. After installation, go to **Install from repository → MediaFusion Repository → Video add-ons**
12. Select **MediaFusion** and click **Install**

> If you see a "Could not connect to repository" message, this is a known caching issue. Fully close and force-stop Kodi, then reopen and navigate back to the repository — it installs cleanly after a fresh launch.

**Step 2: Configure MediaFusion with Your PikPak Account**

1. Open a browser and go to `mediafusion.elfhosted.com/configure`
2. Click **Add Streaming Provider**
3. Select **PikPak** from the provider list
4. Enter your PikPak account **username and password** (your regular login credentials)
5. Configure **Catalogs** — select Movies, TV Shows, Sports, or Live TV as preferred
6. Under **Preferences**, set your resolution, quality, and file size filters
7. Click **Generate Install URL**

**Step 3: Link MediaFusion to Kodi**

1. Back in Kodi, launch the MediaFusion addon
2. Click **Configure Secret**
3. Kodi shows you an authorization code
4. Return to the MediaFusion configuration site, enter the code, and click **Link Kodi**
5. "Setup completed successfully" confirms the connection

MediaFusion now appears in Kodi's Video Add-ons list. When you browse to a title and select a stream, MediaFusion fetches it through your PikPak account — fast, cached, and without any manual downloading.

---

## Which Method Should You Use?

| Use Case | Recommended Method |
| --- | --- |
| Streaming files already saved in your PikPak drive | WebDAV |
| Watching new movies and shows on demand | MediaFusion |
| Building a organized library with cover art and metadata | WebDAV + Kodi scraper |
| Fast access to cached torrent-sourced content | MediaFusion |
| Full control over your file and folder structure | WebDAV |
| Simplest possible setup experience | MediaFusion |

There's no reason you can't run both at the same time — WebDAV for your curated personal library, MediaFusion for on-demand discovery alongside it.

---

## PikPak Plans: Full Comparison (Every Plan, No Gaps)

Both Kodi integration methods require a PikPak Premium account for full functionality. Here's the complete current plan lineup:

| Plan | Storage | Speed | Billing | Approx. Price | Purchase Link |
| --- | --- | --- | --- | --- | --- |
| Free | 6 GB | Shared/Standard | — | $0 | [Try Free](https://bit.ly/PIkpak) |
| Regional Premium Monthly | 10 TB | Up to 5 MB/s | Monthly | ~$2.99–$4.99/mo | [Get Monthly](https://bit.ly/PIkpak) |
| Regional Premium Yearly | 10 TB | Up to 5 MB/s | Annual | ~$28.99–$49.99/yr | [Get Yearly Regional](https://bit.ly/PIkpak) |
| Global Premium Monthly | 10 TB | Up to 20 MB/s | Monthly | ~$7.99–$10/mo | [Get Global Monthly](https://bit.ly/PIkpak) |
| Global Premium Yearly | 10 TB | Up to 20 MB/s | Annual | ~$100.99/yr (~$8.42/mo) | [Get Global Yearly](https://bit.ly/PIkpak) |
| Extra Storage Add-on (Global only) | +10 TB | Same as plan | Annual | ~$60/yr per 10TB | [Add Storage](https://bit.ly/PIkpak) |

**Regional vs Global Premium:** PikPak detects your region automatically at checkout using your IP address and device signals. Users in approximately 23 developed countries — including the US, UK, Canada, Japan, and most of Western Europe — see Global Premium pricing. Everyone else gets Regional Premium, which is priced lower and designed for local use, though it caps download speed at 5 MB/s and doesn't maintain consistent speed when traveling internationally.

For Kodi streaming via WebDAV, **Global Premium is the more comfortable choice**. The 20 MB/s speed ceiling handles 4K content without issue, while the 5 MB/s Regional cap can struggle with high-bitrate encodes. For standard HD content, Regional Premium still works fine.

Going annual saves roughly 16% compared to monthly billing on both tiers. At around $100/year for 10TB of Global Premium, that's approximately $0.83 per TB per month — compare that to Google Drive's $9.99/month for just 2TB and the value picture is clear.

👉 [See all current PikPak plans and pricing](https://bit.ly/PIkpak)

---

## Common PikPak Kodi Problems and How to Fix Them

**WebDAV source fails to connect in Kodi**
The most common cause is a credentials mismatch. PikPak generates dedicated WebDAV credentials that are completely separate from your regular login — go back to your PikPak settings and copy them again exactly as displayed. Also confirm your Premium status is active, since WebDAV won't appear as an option on free accounts.

**"Could not connect to repository" when installing MediaFusion**
Force-close Kodi entirely (on Android: long-press back → App info → Force stop), relaunch, and try the repository install again. The error is caused by a stale connection cache and clears after a fresh session.

**Buffering during 4K playback via WebDAV**
Step down to 1080p or 720p first to confirm the connection itself is working. If lower resolutions play smoothly, the issue is bitrate — your PikPak plan's speed ceiling or your local internet upload can't sustain the 4K stream. Global Premium's 20 MB/s handles most 4K encodes comfortably; Regional Premium at 5 MB/s may hit limits with very high-bitrate files (50+ Mbps HDR encodes, for example).

**MediaFusion doesn't find streams through PikPak**
Check that PikPak shows as an active provider in your MediaFusion configuration panel. If PikPak is listed but streams return as unavailable, the specific file may not be cached in PikPak's network — try a different quality setting or source within MediaFusion.

**Files appear in WebDAV browse but won't play**
Most common formats (MKV, MP4, AVI) play without issue. Some edge cases with older audio codecs in `.wmv` files can cause problems in web-based WebDAV playback. Installing an additional Kodi codec add-on or switching the audio track in player settings usually resolves this.

---

## Beyond Kodi: What Else PikPak Does

The PikPak Kodi setup is compelling, but the service does quite a bit more that feeds directly into the Kodi experience.

**Telegram Bot:** Forward any file or link from a Telegram channel to your PikPak drive with one tap. For people pulling content from private Telegram groups, this is a fast pipeline: Telegram → PikPak → Kodi via WebDAV, all without touching a download client.

**Browser Extension:** Chrome and Edge extensions let you right-click any downloadable link on a webpage and send it directly to PikPak. By the time you've navigated away, the file is already in your cloud library.

**Cloud Decompression:** Upload a ZIP, RAR, or 7z archive and extract it entirely in the cloud without downloading anything locally first. The extracted files appear in your PikPak folder ready to browse via Kodi's WebDAV source.

**4K In-App Streaming:** PikPak's own apps on Android, iOS, Windows, macOS, and Android TV handle 4K playback with automatic resolution switching. If your Kodi setup is temporarily unavailable, the PikPak app is a direct fallback.

**Multi-Device Access:** Your PikPak library is accessible simultaneously across all devices. The Kodi box in the living room, the phone during a commute, the laptop at a desk — all drawing from the same 10TB pool.

---

## Should You Use the Free Tier Before Committing?

Yes, and it's a legitimate test rather than a token gesture. The free 6GB tier gives you full access to PikPak's cloud download functionality — the core feature that makes the whole system work. You can paste magnet links, download from URLs, use the Telegram bot, and see exactly how fast files land in your library before spending anything.

The only things behind the Premium wall are WebDAV access (which you need for the Kodi integration), the higher storage ceiling, and the priority download speed. For the Kodi use case specifically, Premium is necessary — but the free tier is genuinely useful for confirming the workflow makes sense before you upgrade.

👉 [Create your free PikPak account — invitation code 74098243 for bonus access](https://bit.ly/PIkpak)

---

## Final Take: PikPak + Kodi Is a Surprisingly Clean Setup

The PikPak Kodi setup solves a real problem neatly. You get 10TB of cloud storage that fills itself, accessible from Kodi via WebDAV as a permanent library source — or through MediaFusion as an on-demand streaming provider. Either way, no local storage required, no home server to maintain, no seedbox management.

The WebDAV path requires about ten minutes of configuration after you've enabled the feature in PikPak settings. MediaFusion takes a bit longer because of the configuration site step, but it's a one-time setup. After that, both just work.

If you're already using PikPak's cloud download features and haven't connected it to Kodi yet, it's worth the fifteen minutes. If you're new to PikPak entirely, start with the free tier to get a feel for the download workflow, then upgrade to Premium when you're ready to add Kodi to the mix.

👉 [Get started with PikPak today](https://bit.ly/PIkpak)
