# LINE TECHPULSE 2018

以下按Session順序紀錄摘要與心得

===========================

## Marco Chen
## Line的技術策略:兩大主題

串連 connect

透過Discover, Natural UX
大量利用AI在分析與辨識

付費生態圈 mutual benefit ecosystem

Open API:
Message API
LIFF
LIFF chain（應用區塊鏈）
去中心化
獎勵用戶做出貢獻
流通不同服務的數位貨幣
透過LINK chain來解決處理效率問題
Clova
目前尚無法處理中文
Chatbot engine
目前尚無法處理自然語言的對話

LINE platform
How is it cost?
官方帳號2.0計畫
Build everything from scratch?
Re-use oriented software programming
Micro service -> PAAS -> New initiative POC -> Open API
Oversea Open API
OXII-VN
TODAY APP-ID

Yvonne Wang
LINE platform API Update
打造更好的chatbot服務
More service on line
Messaging API
三大優化
Message
FLEX Message
彈性的訊息格式
Video ImageMap
透過影音強化用戶體驗
Chat
Quick reply
提供用戶回覆建議減少用戶與chatbot溝通卡住
Interface
LIFF
整合表單，外部網頁與訊息減少用戶錯誤的操作
Personalization
LINE Login
Account link
分析用戶資料自動將用戶分群
Compared hash data and
Send message to your targeting customer.
Switcher API
在不同endpoint之間切換
CALL API
直接透過電話與官方聯絡
Icon Switch API

Friendly develop
Bot Designer
Flex Simulator
LIFF Console

What’s Next
New Official Account
Ask will start from $0 with Messaging API.
Chatbot engine
NLU tool integrated in LINE bot natively.
＝＝＝＝＝＝＝＝＝＝
Bill Chan
LINE Pay X 一卡通

行動支付生態圈
Credit card+LINE points
iPass電子支付+iPass電子票證
LINE Pay與iPass兩邊獨立模組
可利用LINE Pay x iPass單人或多人分攤付款
生活費用也可用LINE Pay x iPass
乘車碼:手機也可搭高捷（台北公車coming soon…） LINE Wallet
iPass帳戶連結銀行帳戶
可設定自動儲值或虛擬帳號ATM儲值
可即時提領，即時入帳
用戶的金錢紀錄投過銀行的信託專戶來儲存與轉移
用LINE points付款，小吃夜市也ＯＫ
LINE Pay open API
商店交易可投過Credit card, LINE points或iPass來付款

市政府資訊局長 李維斌
市政府smart portal

重新分類市政服務
透過LINE整合服務申請流程資訊化

Kevin Luo
LINE Things
LINE IOT平台技術分享

Why Line Things
Every one is using LINE
Hassle & Chaos for users now
Cause bad user experience
With LINE Things
For users…
All in one, Hassle free, interact with chat or web view
For developers…
No more apps
Just use web tech
Easy to integrate
Support both offline and online devices
Use case:
Open home devices
Door opened alarm

LINE Beacon
You can send messages when customer entering your store

Service Architecture
LIFF BLE

Features:
Devices link
LIFF SDK with BLE (JS)
Automated BLE communication

Sample code on github: line-things-starter

Jin-Hee Lee (KR)
LINK chain and LINK
LINE區塊鏈平台與代幣經濟

LINE needs blockchain and cryptocurrencies

LINK Token economy
LINK - LINE’s cryptocurrency
Platform coin of LINK Chain
Service coin of LINK Chain
3 Principles of the LIKNK ecosystem
1. Design for dApps and users
2. Contribution is the new mining
3. Connected economy with a single coin
Issues:
Total 1 billion 
No privacy safe, no ICO
User bottlenecks:
Wallet
Private key
No useful dApp
dApp Developers headache:
Learning curve of tech
LINE offers service-oriented LINK platform
LINK chain:
Improved UX
Easy integration to blockchain
Flexible and scalable
BitBox 註冊送3link

陳宏宇 國家災害防救科技中心

Kuan-Wei Lin
LINE TODAY高效率的敏捷測試開發技巧

DevOps <> Design <> Testing <> Discover <> DevOps …
Shorter Release Cycle
Testing is a Repetition work
Really Agile?
2 important part of develop flow:
New functionality
System regression
3 part of checking
Code
Architecture
Change scope
3 code quality aspect
Code coverage
Code review
Continuous improvement
1 PR should less than 200 line
Testing on native iOS or Android

Nishikawa
KAAS in line private cloud
Verda

Sean Huang
LINE Chatbot
活動報名報到設計及分享

Registration Chatbot
Registration:
Entry Point>Web, Click to get QR code, scan to mobile device
registrater to add official account with rich menu (LIFF)
Check-in:
Beacon -> with BLE
QRCode -> with simple way
Events:
Realtime Information
With flex message to send session information Interactive Booth
Jungle Pang Battle
With ranking feed
Smart City
With IOT
Questionnaire

日本開發者大會分享
Deniel Kao

Too many features, too less time
LINE TODAY service, becomes content portal
Proposed approach:
1. Release fast
2. Find pain points
3. Iterate

Irene Chen

LINE BUZZ
Users can share fun image or video
HBASE as database
1. Indexed only based on rockets
2. No transaction
Retrieve content by Get post by id
To prevent full table scan, use secondary index table with rowkey = user_postID ex. “UserA_1”
We build secondary indices by Kafka
By control consumer’s offset commit
Call commit only when all message are processed successfully
 Duplicate message might be avoid

TingTing Hu

Taipei Metro X LINE Beacon
LINE TODAY - enrich your 50 minutes commute time
Coupon - give you what’s near you
Puzzle Game - make the city your playground
Bus Info - make your transfer seamless
CWA(Channel Web Application)?
How to manage 200+ beacons
Hierarchy management
Event handling
Zookeeper Key = UserID + Event Type
Event processing speedup with indecently db entry

Yeats Yang
LINE新星計畫介紹與新星團隊分享
LINE PROTOSTAR

We offer…
Business connect:
Unlimited OA friends
Message API
LINE Login API
LINE Pay API
Technical consultation
ex. Taxi go, help them to expand business like chatbot
LINE caring program:
Dedicated account officer
Mentorship
CCIA(中華開發加速器) bootcamp
CCIA offer training camp
Business and technical consultation
Partnership referral
Protostar networks
Investment opportunities:
LINE investment
Strategy or financial investment
Partnership for LINE new service
Other reward option

LINE partner app
潔客幫
跑跑腿

Evan Lin
LINE開發者社群推廣

LINE developer website
LINE engineering blog
LINE API Expert
LINE Open Source Software
LINE - starter
LINE Login - starter
LINE Things - starter
LINE SimpleBeacon
LINE BOOT awards (global)

Kay Chang
LINE技術合作夥伴與應用分享

We offer…
Latest tech update
Business opportunities
Monetization model

繳費平台應用:生活繳費王

Try:
Chatbot + cnn-watermakrs-removal
Send a watermarked picture and return original version
