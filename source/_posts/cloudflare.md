---
title: Use CloudFlare to protect personal blogs
tags:
  - CloudFlare
  - blog
categories:
  - CloudFlare
description: Recently, many personal blogs have been attacked to varying degrees. Let us see how to use the powerful CloudFlare to protect our website!
keywords:
  - CloudFlare
  - blog
  - ddos
date: 2020-03-25 08:12:55
---

## Resolve domain name to CloudFlare
{% note info %}
### info
Because each domain name registrar is different, so I won’t do a demonstration here
{% endnote %}

## Configure firewall
After entering the dashboard, click on `Firewall` to enter `Firewall Rules`

![firewall rules](https://assets.bmyjacks.cn/img/20200325071518.png?x-oss-process=style/style)

### Block malicious bots
Create a new Firewall Rules.

First, we configure rules to block some bots that pose a threat to the website

![example](https://assets.bmyjacks.cn/img/20200325072055.png?x-oss-process=style/style)

Write in 2

```bash
(http.user_agent eq "404") or
(http.user_agent eq "nmap") or
(http.user_agent eq "80legs") or
(http.user_agent eq "Abonti") or
(http.user_agent eq "admantx") or
(http.user_agent eq "aipbot") or
(http.user_agent eq "AllSubmitter") or
(http.user_agent eq "Backlink") or
(http.user_agent eq "backlink") or
(http.user_agent eq "Badass") or
(http.user_agent eq "Bigfoot") or
(http.user_agent eq "blexbot") or
(http.user_agent eq "Buddy") or
(http.user_agent eq "CherryPicker") or
(http.user_agent eq "cloudsystemnetwork") or
(http.user_agent eq "cognitiveseo") or
(http.user_agent eq "Collector") or
(http.user_agent eq "cosmos") or
(http.user_agent eq "CrazyWebCrawler") or
(http.user_agent eq "Crescent") or
(http.user_agent eq "Devil") or
(http.user_agent eq "domain") or
(http.user_agent eq "spider") or
(http.user_agent eq "stat") or
(http.user_agent eq "Appender") or
(http.user_agent eq "Crawler") or
(http.user_agent eq "DittoSpyder") or
(http.user_agent eq "Konqueror") or
(http.user_agent eq "Easou") or
(http.user_agent eq "Yisou") or
(http.user_agent eq "Etao") or
(http.user_agent eq "mail") or
(http.user_agent eq "olf") or
(http.user_agent eq "spider") or
(http.user_agent eq "exabot.com") or
(http.user_agent eq "getintent") or
(http.user_agent eq "Grabber") or
(http.user_agent eq "GrabNet") or
(http.user_agent eq "HEADMasterSEO") or
(http.user_agent eq "heritrix") or
(http.user_agent eq "htmlparser") or
(http.user_agent eq "hubspot") or
(http.user_agent eq "Jyxobot") or
(http.user_agent eq "kraken") or
(http.user_agent eq "larbin") or
(http.user_agent eq "ltx71") or
(http.user_agent eq "leiki") or
(http.user_agent eq "LinkScan") or
(http.user_agent eq "Magnet") or
(http.user_agent eq "Mag-Net") or
(http.user_agent eq "Mechanize") or
(http.user_agent eq "MegaIndex") or
(http.user_agent eq "Metasearch") or
(http.user_agent eq "MJ12bot") or
(http.user_agent eq "moz.com") or
(http.user_agent eq "Navroad") or
(http.user_agent eq "Netcraft") or
(http.user_agent eq "niki-bot") or
(http.user_agent eq "NimbleCrawler") or
(http.user_agent eq "Nimbostratus") or
(http.user_agent eq "Ninja") or
(http.user_agent eq "Openfind") or
(http.user_agent eq "Page") or
(http.user_agent eq "Analyzer") or
(http.user_agent eq "Pixray") or
(http.user_agent eq "probethenet") or
(http.user_agent eq "proximic") or
(http.user_agent eq "psbot") or
(http.user_agent eq "RankActive") or
(http.user_agent eq "RankingBot") or
(http.user_agent eq "RankurBot") or
(http.user_agent eq "Reaper") or
(http.user_agent eq "SalesIntelligent") or
(http.user_agent eq "Semrush") or
(http.user_agent eq "SEOkicks") or
(http.user_agent eq "spbot") or
(http.user_agent eq "SEOstats") or
(http.user_agent eq "Snapbot") or
(http.user_agent eq "Stripper") or
(http.user_agent eq "Siteimprove") or
(http.user_agent eq "sitesell") or
(http.user_agent eq "Siphon") or
(http.user_agent eq "Sucker") or
(http.user_agent eq "TenFourFox") or
(http.user_agent eq "TurnitinBot") or
(http.user_agent eq "twingly") or
(http.user_agent eq "VidibleScraper") or
(http.user_agent eq "WebLeacher") or
(http.user_agent eq "WebmasterWorldForum") or
(http.user_agent eq "webmeup") or
(http.user_agent eq "Webster") or
(http.user_agent eq "Widow") or
(http.user_agent eq "Xaldon") or
(http.user_agent eq "Xenu") or
(http.user_agent eq "xtractor") or
(http.user_agent eq "Zermelo") or
(http.user_agent eq "aggregator") or
(http.user_agent eq "AhrefsBot") or
(http.user_agent eq "asterias") or
(http.user_agent eq "BDCbot") or
(http.user_agent eq "BLEXBot") or
(http.user_agent eq "BuiltBotTough") or
(http.user_agent eq "Bullseye") or
(http.user_agent eq "BunnySlippers") or
(http.user_agent eq "ca-crawler") or
(http.user_agent eq "CCBot") or
(http.user_agent eq "Cegbfeieh") or
(http.user_agent eq "CheeseBot") or
(http.user_agent eq "CopyRightCheck") or
(http.user_agent eq "discobot") or
(http.user_agent eq "DOC") or
(http.user_agent eq "DotBot") or
(http.user_agent eq "Download Ninja") or
(http.user_agent eq "EmailCollector") or
(http.user_agent eq "EmailSiphon") or
(http.user_agent eq "EmailWolf") or
(http.user_agent eq "EroCrawler") or
(http.user_agent eq "Exabot") or
(http.user_agent eq "ExtractorPro") or
(http.user_agent eq "Fasterfox") or
(http.user_agent eq "FeedBooster") or
(http.user_agent eq "Foobot") or
(http.user_agent eq "Genieo") or
(http.user_agent eq "grub-client") or
(http.user_agent eq "Harvest") or
(http.user_agent eq "hloader") or
(http.user_agent eq "httplib") or
(http.user_agent eq "humanlinks") or
(http.user_agent eq "ieautodiscovery") or
(http.user_agent eq "InfoNaviRobot") or
(http.user_agent eq "IstellaBot") or
(http.user_agent eq "Java1.") or
(http.user_agent eq "JennyBot") or
(http.user_agent eq "k2spider") or
(http.user_agent eq "Kenjin Spider") or
(http.user_agent eq "Keyword Density0.9") or
(http.user_agent eq "LexiBot") or
(http.user_agent eq "libWeb") or
(http.user_agent eq "libwww") or
(http.user_agent eq "LinkextractorPro") or
(http.user_agent eq "linko") or
(http.user_agent eq "LinkScan8.1a Unix") or
(http.user_agent eq "LinkWalker") or
(http.user_agent eq "LNSpiderguy") or
(http.user_agent eq "lwp-trivial") or
(http.user_agent eq "magpie") or
(http.user_agent eq "Mata Hari") or
(http.user_agent eq "MaxPointCrawler") or
(http.user_agent eq "Microsoft URL Control") or
(http.user_agent eq "MIIxpc") or
(http.user_agent eq "Mippin") or
(http.user_agent eq "Missigua Locator") or
(http.user_agent eq "Mister PiX") or
(http.user_agent eq "moget") or
(http.user_agent eq "MSIECrawler") or
(http.user_agent eq "NetAnts") or
(http.user_agent eq "NICErsPRO") or
(http.user_agent eq "Niki-Bot") or
(http.user_agent eq "NPBot") or
(http.user_agent eq "Nutch") or
(http.user_agent eq "Offline Explorer") or
(http.user_agent eq "panscient.com") or
(http.user_agent eq "ProPowerBot2.14") or
(http.user_agent eq "ProWebWalker") or
(http.user_agent eq "Python-urllib") or
(http.user_agent eq "QueryN Metasearch") or
(http.user_agent eq "RepoMonkey") or
(http.user_agent eq "RMA") or
(http.user_agent eq "SemrushBot") or
(http.user_agent eq "SeznamBot") or
(http.user_agent eq "SISTRIX") or
(http.user_agent eq "sitecheck.Internetseer.com") or
(http.user_agent eq "SiteSnagger") or
(http.user_agent eq "SnapPreviewBot") or
(http.user_agent eq "Sogou") or
(http.user_agent eq "SpankBot") or
(http.user_agent eq "spanner") or
(http.user_agent eq "Spinn3r") or
(http.user_agent eq "suzuran") or
(http.user_agent eq "Szukacz1.4") or
(http.user_agent eq "Teleport") or
(http.user_agent eq "Telesoft") or
(http.user_agent eq "The Intraformant") or
(http.user_agent eq "TheNomad") or
(http.user_agent eq "TightTwatBot") or
(http.user_agent eq "Titan") or
(http.user_agent eq "True_Robot") or
(http.user_agent eq "turingos") or
(http.user_agent eq "UbiCrawler") or
(http.user_agent eq "UnisterBot") or
(http.user_agent eq "URLy Warning") or
(http.user_agent eq "VCI") or
(http.user_agent eq "WBSearchBot") or
(http.user_agent eq "Web Downloader6.9") or
(http.user_agent eq "WebAuto") or
(http.user_agent eq "WebBandit") or
(http.user_agent eq "WebCopier") or
(http.user_agent eq "WebEnhancer") or
(http.user_agent eq "WebmasterWorldForumBot") or
(http.user_agent eq "WebReaper") or
(http.user_agent eq "WebSauger") or
(http.user_agent eq "Website Quester") or
(http.user_agent eq "Webster Pro") or
(http.user_agent eq "WebStripper") or
(http.user_agent eq "WebZip") or
(http.user_agent eq "Wotbox") or
(http.user_agent eq "wsr-agent") or
(http.user_agent eq "WWW-Collector-E") or
(http.user_agent eq "Zao") or
(http.user_agent eq "Zeus") or
(http.user_agent eq "ZyBORG") or
(http.user_agent eq "coccoc") or
(http.user_agent eq "Incutio") or
(http.user_agent eq "lmspider") or
(http.user_agent eq "memoryBot") or
(http.user_agent eq "serf") or
(http.user_agent eq "Unknown") or
(http.user_agent eq "uptime files") or
(http.user_agent eq "HTTrack") or
(http.user_agent eq "Apache-HttpClient") or
(http.user_agent eq "harvest") or
(http.user_agent eq "audit") or
(http.user_agent eq "dirbuster") or
(http.user_agent eq "pangolin") or
(http.user_agent eq "sqln") or
(http.user_agent eq "hydra") or
(http.user_agent eq "Parser") or
(http.user_agent eq "BBBike") or
(http.user_agent eq "sqlmap") or
(http.user_agent eq "w3af") or
(http.user_agent eq "owasp") or
(http.user_agent eq "Nikto") or
(http.user_agent eq "fimap") or
(http.user_agent eq "havij") or
(http.user_agent eq "zmeu") or
(http.user_agent eq "FeedDemon") or
(http.user_agent eq "Indy Library") or
(http.user_agent eq "Alexa Toolbar") or
(http.user_agent eq "AskTbFXTV") or
(http.user_agent eq "CrawlDaddy") or
(http.user_agent eq "CoolpadWebkit") or
(http.user_agent eq "Java") or
(http.user_agent eq "Feedly") or
(http.user_agent eq "UniversalFeedParser") or
(http.user_agent eq "ApacheBench") or
(http.user_agent eq "Swiftbot") or
(http.user_agent eq "ZmEu") or
(http.user_agent eq "oBot") or
(http.user_agent eq "jaunty") or
(http.user_agent eq "lightDeckReports Bot") or
(http.user_agent eq "YYSpider") or
(http.user_agent eq "DigExt") or
(http.user_agent eq "HttpClient") or
(http.user_agent eq "EasouSpider") or
(http.user_agent eq "Ezooms") or
(http.user_agent eq "BabyKrokodil") or
(http.user_agent eq "netsparker") or
(http.user_agent eq "httperf")
```

Then you can set the name of the firewall rule in 1, and select the action after triggering the firewall rule in 3.

```bash
Block #Block access
JS Challenge #Use JS verification, bots cannot pass verification, browser can pass verification (recommended for bot)
Challenge(Captcha) #Use the verification code to verify, the browser must enter the verification code to access
Allow #Allow access
Bypass
```

Click Save and make sure it is set to open. Now, most malicious bots cannot access your website!

![Turn on the firewall](https://assets.bmyjacks.cn/img/20200325072746.png?x-oss-process=style/style)


## Malicious IP
Create a new `Firewall Rule` and edit the options as shown

![Whreat score](https://assets.bmyjacks.cn/img/20200325080814.png?x-oss-process=style/style)

```bash
Threat Score #IP Threat Index
# TS>50 Very threatening
# 24<TS<50 Mid threatening
# TS>10 Low threatening
```

Click `And`, select `Known bots`, and turn off the switch.

And it is not a known good bot, save it, succeed!

{% note success %}
## Congratulations
Congratulations to you，Some common attacks on the Internet can no longer cause damage to your website
{% endnote %}
