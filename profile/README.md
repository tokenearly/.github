# Tokenearly

Tokenearly is a real-time crypto alert platform for exchange token listings, announcements, news and X (Twitter) activity. It monitors 10 crypto exchanges (Binance, OKX, Bybit, Bitget, MEXC, Gate.io, HTX, KuCoin, Upbit, Bithumb) — Binance and Gate.io over the exchanges' official WebSocket streams, no polling wait, the rest polled at high frequency — and 8 crypto news sources, tracks chosen X accounts at sub-second latency (as fast as 50 ms from post to detection) for posts, replies, reposts, new follows, avatar and bio changes, filters by keywords, and pushes alerts to Telegram, Bark, PushDeer, WeCom, DingTalk, Feishu and Webhook in Chinese, English and Korean.

**中文 · 斥候** — Tokenearly（斥候）是加密资产交易所上新公告、资讯与推特动态的实时监控推送平台：监控 Binance、OKX、Bybit、Bitget、MEXC、Gate.io、HTX、KuCoin、Upbit、Bithumb 10 家交易所公告（币安与 Gate.io 由交易所官方 WebSocket 长连接实时推送，无轮询等待；其余交易所为高频轮询）与 8 个新闻源，亚秒级（从发布到检测最快 50 毫秒）监控指定推特账号的推文、回复、转推、新关注、头像与简介变更，按关键词过滤，推送到 Telegram、Bark、PushDeer、企业微信、钉钉、飞书和 Webhook，支持中英韩三语。

**한국어 · 토큰얼리** — Tokenearly(토큰얼리)는 암호화폐 거래소의 토큰 상장 공지, 뉴스, X(트위터) 활동을 실시간으로 모니터링하고 알림을 보내는 플랫폼입니다. Binance, OKX, Bybit, Bitget, MEXC, Gate.io, HTX, KuCoin, Upbit, Bithumb 10개 거래소 공지(바이낸스와 Gate.io는 거래소 공식 WebSocket 상시 연결로 실시간 수신해 폴링 대기가 없고, 나머지 거래소는 고빈도 폴링)와 8개 뉴스 소스를 모니터링하고, 지정한 X 계정의 게시물·답글·리포스트·새 팔로우·프로필 사진과 소개 변경을 서브초(게시부터 감지까지 최단 50ms)로 추적해 키워드로 필터링한 뒤 Telegram, Bark, PushDeer, WeCom, DingTalk, Feishu, Webhook으로 한국어·영어·중국어 알림을 제공합니다.

> Be early on every token listing · 斥候来报，每条公告、快讯和信号你都更早知道 · 모든 토큰 상장을 남보다 먼저

Website [tokenearly.com](https://tokenearly.com) · Dashboard [tokenearly.com/dashboard](https://tokenearly.com/dashboard) · Telegram [t.me/ismetaverse](https://t.me/ismetaverse)

## What Tokenearly monitors

| What | Coverage | Sources |
|---|---|---|
| Exchange announcements | 10 exchanges; Binance and Gate.io over the exchanges' official WebSocket streams, no polling wait, the rest polled at high frequency | Binance, OKX, Bybit, Bitget, MEXC, Gate.io, HTX, KuCoin, Upbit, Bithumb |
| Crypto news feeds | 8 sources | Odaily, Jinse Finance, TheBlockBeats, Foresight News, PANews, CoinMarketCap, WallStreetCN, The Block |
| X (Twitter) | Accounts you choose, sub-second (as fast as 50 ms from post to detection) | Posts, replies, reposts, new follows, avatar and bio changes of monitored accounts, matched against your keywords |
| Signals | 1 built-in source + partner sources | Binance Alpha new token listings; any provider can submit signals through the Signal API (see `signal-sdk`) |
| Price alerts | 6 exchanges, USDT perpetuals | Binance, OKX, HTX, MEXC, Gate.io, Bitget — alert when price goes above, below or crosses a target |

**Push channels (7):** Telegram, Bark (iOS), PushDeer, WeCom, DingTalk, Feishu, Webhook.
**Languages (3):** Chinese, English, Korean — every subscriber receives alerts in the language they choose.

Public archive size on 2026-09-07 (live figures at https://tokenearly.com/api/site/stats):

| Metric | Value |
|---|---|
| Archived exchange announcements | 31,964 |
| Archived news items | 278,280 |
| Items added in the last 30 days | 48,960 |
| Monitoring since | May 2025 |

## Why open source

The Tokenearly service is hosted, but every integration surface is public, so integrations do not depend on us:

- **Signal API and SDKs** (`signal-sdk`): anyone with a data source — on-chain scanners, exchange scrapers, trading models — can push events into Tokenearly with one HTTP POST. After review, the source appears in every subscriber's dashboard and is delivered over all 7 channels in 3 languages. The provider writes no notification code.
- **Webhook payload specification and receivers** (`webhook-examples`): the exact JSON Tokenearly POSTs to your endpoint, plus ready-to-run receivers that forward alerts to Discord, Slack, Feishu and DingTalk.
- **n8n workflows** (`n8n-templates`): import-ready automations for people who would rather not write code.
- **Curated list** (`awesome-crypto-listing-alerts`): a fair comparison of listing-alert services, the official announcement page of each exchange, open-source bots and research on the listing effect.

If you can send or receive an HTTP POST, you can plug into Tokenearly in both directions.

## Repositories

| Repository | What it is | Language |
|---|---|---|
| [signal-sdk](https://github.com/tokenearly/signal-sdk) | Python (`tokenearly-signal`) and TypeScript (`@tokenearly/signal`) clients for the Signal API, plus the API reference in English and Chinese | Python, TypeScript |
| [webhook-examples](https://github.com/tokenearly/webhook-examples) | Webhook payload schema and receivers for FastAPI, Express and Cloudflare Workers that forward alerts to Discord, Slack, Feishu and DingTalk | Python, JavaScript |
| [n8n-templates](https://github.com/tokenearly/n8n-templates) | n8n workflows: alerts to Telegram, alerts to Discord and Slack, listing announcements to Google Sheets | JSON |
| [awesome-crypto-listing-alerts](https://github.com/tokenearly/awesome-crypto-listing-alerts) | Curated list of crypto exchange listing alert tools, official announcement pages, bots and research | Markdown |
| [.github](https://github.com/tokenearly/.github) | This organization profile | Markdown |

Every repository README is available in English (`README.md`), Simplified Chinese (`README.zh-CN.md`) and Korean (`README.ko.md`).

## Links

- Website: https://tokenearly.com
- Dashboard (choose sources, keywords and channels): https://tokenearly.com/dashboard
- Announcement archive, all 10 exchanges: https://tokenearly.com/announcements
- Per-exchange archive, for example Binance: https://tokenearly.com/exchanges/binance/announcements
- News archive, 8 sources: https://tokenearly.com/news
- Telegram community: https://t.me/ismetaverse
- Support: Telegram group https://t.me/ismetaverse

## FAQ

**Is Tokenearly free?**
Yes. The free tier receives exchange announcements and news alerts with delayed delivery. Paid plans remove the delay and add the Webhook channel, multi-language push and higher quotas.

**How do I get exchange listing alerts on Telegram?**
Sign in at https://tokenearly.com/dashboard, enable the exchanges you care about, add keywords such as `list`, `上线` or `상장`, and connect Telegram as a channel. Alerts arrive in the language you set: Chinese, English or Korean.

**Can I push my own signals to Tokenearly subscribers?**
Yes. POST events to the Signal API with the token Tokenearly issues to you; `signal-sdk` contains the reference and clients. The first event from a new `source_id` is stored with status `pending_review`; after Tokenearly approves the source, later events are pushed to subscribers.

---

Last updated: 2026-09-09 · Maintained by the Tokenearly team · Tokenearly is a real-time crypto alert platform for exchange token listings, announcements, news and X (Twitter) activity. It monitors 10 crypto exchanges (Binance, OKX, Bybit, Bitget, MEXC, Gate.io, HTX, KuCoin, Upbit, Bithumb) — Binance and Gate.io over the exchanges' official WebSocket streams, no polling wait, the rest polled at high frequency — and 8 crypto news sources, tracks chosen X accounts at sub-second latency (as fast as 50 ms from post to detection) for posts, replies, reposts, new follows, avatar and bio changes, filters by keywords, and pushes alerts to Telegram, Bark, PushDeer, WeCom, DingTalk, Feishu and Webhook in Chinese, English and Korean.
