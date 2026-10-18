---
title: Tap Champion Privacy Policy
permalink: /tapchampion/privacy/
---

# 連打名人 / Tap Champion — Privacy Policy

**発効日 / Effective:** 2026-06-12 ・ **バージョン / Version:** 1.0 ・ **連絡先 / Contact:** [support@haroworks.com](mailto:support@haroworks.com) ・ **applicationId / Bundle ID:** `com.haroworks.tapchampion`

[← Index](../../)

**Languages / 言語:** [日本語](#ja) ・ [English](#en) ・ [简体中文](#zh-hans) ・ [繁體中文](#zh-hant) ・ [한국어](#ko) ・ [Español](#es) ・ [Français](#fr) ・ [Deutsch](#de) ・ [Português](#pt)

本アプリは iOS / Android の両プラットフォームで配信されます。バックエンド構成は両プラットフォームで共通のため、本ポリシーは両者を対象とします。プラットフォーム固有の事項は本文中に注記します。 / The App is distributed on both iOS and Android. As the backend is identical on both, this Policy covers both platforms; platform-specific items are noted inline.

<a id="ja"></a>

## §A. 日本語 (ja, default)

### 連打名人 プライバシーポリシー

連打名人（Tap Champion、以下「本アプリ」）における個人情報および利用者データの取扱いについて定めます。本アプリの提供者 HaroWorks（以下「開発者」）は、以下のとおり個人情報および利用者データを取扱います。

#### 第 1 条 (適用範囲)

本ポリシーは、開発者が Apple App Store および Google Play で配信するモバイルアプリ「連打名人 / Tap Champion」のすべての利用者に適用されます。本アプリの利用を開始した時点で、利用者は本ポリシーに同意したものとみなします。

#### 第 2 条 (アカウントと匿名認証)

本アプリは、氏名・メールアドレス・電話番号等の登録を必要としません。初回起動時に Firebase Authentication の**匿名ログイン**により、利用者を識別するためのランダムな匿名 ID（匿名 UID）を自動発行します。

- 匿名 UID には、氏名・メールアドレス・電話番号その他の連絡先情報は一切紐づきません。
- 本アプリは、ソーシャルログインや会員登録の機能を持ちません。
- 匿名 UID は、ランキングへのスコア送信および実績の保存に用いられます。

#### 第 3 条 (収集・送信する情報)

本アプリは、オンラインランキング機能の提供のため、以下の情報を開発者のクラウドバックエンド（Google Cloud Firestore）に送信・保存します。

| 項目 | 内容 | 公開範囲 |
| --- | --- | --- |
| プレイヤー名（displayName） | 利用者が設定する 1〜12 文字の表示名。初期値は「Player + 数字」を自動生成 | 公開ランキングに表示 |
| 国（countryCode） | 利用者が選択する国（国旗表示用、ISO 3166-1 alpha-2）。初期値は端末の言語設定から推定 | 公開ランキングに表示 |
| スコア（score） | 各モードのベストスコア | 公開ランキングに表示 |
| モード / 期間 | A / AB / ABC / ABCD、Daily / Weekly / All Time の区分 | 公開ランキングに表示 |
| 更新日時（updatedAt） | スコア更新のサーバー時刻 | 公開ランキングに表示 |
| 実績解除状態 | 各実績の解除日時 | 非公開（本人のみ） |

**公開ランキングについて**: 上記のうちプレイヤー名・国・スコア・更新日時は、世界ランキングとして他のすべての利用者に公開表示されます。実名・個人を特定しうる情報をプレイヤー名に設定しないでください（設定画面でいつでも変更できます）。

本アプリはプレイ自体をオフラインで実行できます。通信が発生するのは、スコアのランキング送信、ランキングの閲覧、後述の分析・広告・課金処理の各場面に限られます。

#### 第 4 条 (端末内にのみ保存されるデータ)

本アプリは以下のデータを利用者の端末内ストレージにも保存します。これらはオフラインプレイおよび表示の高速化のために用いられ、ランキング送信時を除き端末外へ送信されません。

- 各モードの自己ベストスコア
- プレイヤープロフィール（プレイヤー名、国、UI 言語、広告削除の購入状態）
- 実績の解除状態
- ランキング送信待ちの保留データ（オフライン時に作成され、オンライン復帰時に送信後削除）

アプリをアンインストールすると、端末内データは削除されます。匿名 UID は端末ごとに発行されるため、アンインストール後はクラウド上のスコア・実績を復元できません。

#### 第 5 条 (利用状況の分析 — Firebase Analytics)

本アプリは、機能改善および利用状況の把握のため、Google の Firebase Analytics を利用します。以下のイベントが記録されます。

- `game_start`（ゲーム開始）/ `game_finish`（ゲーム終了・スコア）/ `mode_select`（モード選択）
- `ranking_view`（ランキング閲覧）/ `ad_view`（広告表示）/ `share_score`（スコア共有）

Firebase Analytics は、上記イベントに加えて、端末モデル・OS バージョン・おおまかな地域・アプリバージョン・言語設定・Google が発行するアプリインスタンス識別子（擬似 ID）等の標準的な情報を自動的に収集します。これらは統計的な分析に用いられ、利用者個人を特定する目的では利用しません。Google の取扱いは Google のプライバシーポリシー（<https://policies.google.com/privacy>）および「Google のサービスを使用するサイトやアプリから収集した情報の Google による使用」（<https://policies.google.com/technologies/partner-sites>）に従います。

#### 第 6 条 (クラッシュレポート — Firebase Crashlytics)

本アプリは、不具合の検出と修正のため、Firebase Crashlytics を利用します。アプリがクラッシュした際、スタックトレース・端末モデル・OS バージョン・アプリの状態等の診断情報が Google に送信されます。これらの情報に、氏名・メールアドレス等の個人情報は含まれません。

#### 第 7 条 (リモート設定 — Firebase Remote Config)

本アプリは、イベント運用・ランキング表示・広告表示の調整のため、Firebase Remote Config から設定値を取得します。取得時に Google が利用者の IP アドレスを参照しますが、本アプリは利用者識別情報を送信しません。

#### 第 8 条 (広告 — Google AdMob / UMP)

本アプリは、無料で提供されるため、Google AdMob による広告（リザルト画面のバナー広告、および任意視聴のリワード広告）を表示します。

- AdMob は、広告配信のために広告識別子（Android: 広告 ID、iOS: IDFA）を参照する場合があります。
- 欧州経済領域（EEA）・英国等では、Google UMP（User Messaging Platform）による**同意管理画面**を表示し、利用者の選択（パーソナライズド広告の可否等）に従います。
- 利用者が同意しない場合、または対象地域では、**非パーソナライズド広告**のみが配信されます。
- AdMob のプライバシーに関する取扱いは Google のポリシー（<https://policies.google.com/technologies/ads>）に従います。
- 後述の「広告削除」をアプリ内課金で購入すると、広告は表示されなくなります。

#### 第 9 条 (アプリ内課金 — Unity IAP)

本アプリは「広告削除」の買い切り課金（アプリ内課金）を提供します。

- 決済処理は Apple App Store（iOS）または Google Play（Android）が行い、開発者はクレジットカード番号等の決済情報を取得しません。
- 購入の検証・復元のために、各ストアが管理する購入レシート・トランザクション情報を参照します。これらの取扱いは Apple / Google のポリシーに従います。
- 購入状態（広告削除済みか否か）は端末内に保存されます。

#### 第 10 条 (SNS 共有)

リザルト画面の「共有」操作により、利用者の意思で、モード名・スコア・世界順位・ハッシュタグを含むテキストを、利用者が選択した SNS・アプリ（X / LINE / Facebook / Instagram 等）へ共有できます。共有は利用者の操作を起点として発生し、共有先での取扱いは各サービスのポリシーに従います。

#### 第 11 条 (第三者提供)

本アプリは、利用者の情報を、第 5〜10 条に記載した機能の提供に必要な範囲で各サービス提供者（Google / Apple / Unity）に処理を委託する場合を除き、第三者に開示・提供しません。法令に基づく開示要請があった場合を除きます。なお、公開ランキングに表示される情報（第 3 条）は、その性質上すべての利用者に公開されます。

#### 第 12 条 (子どもの利用)

本アプリは **13 歳未満の利用者を対象としていません**。アプリ内に表示される広告は AdMob によって配信されます。保護者の方は、13 歳未満の利用者によるインストール・利用および課金を管理してください。万一、13 歳未満の利用者の情報が送信された事実が判明した場合、開発者は速やかに削除します。

#### 第 13 条 (利用者の権利)

利用者は以下の権利を有します。

- **データ削除**: アプリをアンインストールすると端末内データは削除されます。クラウド上のスコア・プロフィール・実績の削除をご希望の場合は、第 16 条のお問い合わせ先までご連絡ください。匿名 UID をお知らせいただければ、当該データを削除します。
- **表示情報の変更**: プレイヤー名・国・言語は設定画面でいつでも変更できます。
- **広告のオプトアウト**: 端末の設定（iOS: 設定 > プライバシーとセキュリティ > トラッキング、Android: 設定 > Google > 広告）より、広告識別子のリセットやトラッキングの制限ができます。EEA / 英国等では、アプリ内の同意管理から再設定が可能です。
- **GDPR / CCPA**: 欧州経済領域・英国・カリフォルニア州等の利用者は、適用法令に基づくアクセス・削除・オプトアウト等の権利を行使できます。第 16 条よりご連絡ください。

#### 第 14 条 (データの保管とセキュリティ)

クラウド上のデータは Google Cloud（Firebase / Firestore）に保管され、Firestore Security Rules によりアクセス制御されます。ランキングの日次・週次スコアは一定期間経過後に自動削除されます（Daily は期間終了の約 2 日後、Weekly は期間終了の約 2 日後、All Time は保持）。

#### 第 15 条 (準拠法)

本ポリシーの解釈および適用は、日本国の法律に準拠します。

#### 第 16 条 (お問い合わせ・本ポリシーの変更)

本ポリシーに関するお問い合わせ、データ削除のご依頼は、以下までご連絡ください。

- メールアドレス: `support@haroworks.com`

本ポリシーは、関連法令の改正・サービス内容の変更等に伴い改定されることがあります。改定後のポリシーは、本 HTTPS 公開ページおよび各ストアのアプリ詳細ページに掲示された時点から効力を生じます。重要な変更がある場合は、アプリ内通知またはリリースノートで通知します。

---

**改定履歴**

- v1.0 (2026-06-12): 初版策定（v1.0.0 MVP リリースに合わせて発効）。

---

<a id="en"></a>

## §B. English (en-US)

### Tap Champion Privacy Policy

This Privacy Policy describes how Tap Champion (the "App") handles personal information and user data. The developer of the App, HaroWorks (the "Developer"), handles personal information and user data as follows.

#### Article 1 (Scope)

This Policy applies to all users of the mobile application "Tap Champion" distributed by the Developer through the Apple App Store and Google Play. By starting to use the App, you are deemed to have agreed to this Policy.

#### Article 2 (Accounts and Anonymous Authentication)

The App does not require registration of your name, email address, phone number, or similar information. On first launch, it automatically issues a random anonymous identifier (anonymous UID) via Firebase Authentication **anonymous sign-in** to identify you.

- No name, email address, phone number, or other contact information is associated with the anonymous UID.
- The App has no social login or membership registration.
- The anonymous UID is used to submit scores to the leaderboard and to store achievements.

#### Article 3 (Information We Collect and Transmit)

To provide the online leaderboard, the App transmits and stores the following information in the Developer's cloud backend (Google Cloud Firestore).

| Item | Content | Visibility |
| --- | --- | --- |
| Player name (displayName) | A 1–12 character display name you set; defaults to an auto-generated "Player + number" | Shown on the public leaderboard |
| Country (countryCode) | A country you select for the flag (ISO 3166-1 alpha-2); defaults to a guess from your device language | Shown on the public leaderboard |
| Score | Your best score per mode | Shown on the public leaderboard |
| Mode / Period | A / AB / ABC / ABCD, and Daily / Weekly / All Time | Shown on the public leaderboard |
| Updated time (updatedAt) | Server time of your score update | Shown on the public leaderboard |
| Achievement unlock state | The unlock time of each achievement | Private (you only) |

**About the public leaderboard**: Of the above, your player name, country, score, and updated time are displayed publicly to all other users as part of the world ranking. Do not use your real name or personally identifying information as your player name (you can change it at any time on the Settings screen).

The App can be played offline. Communication occurs only when submitting scores, viewing the leaderboard, and for the analytics, advertising, and purchasing functions described below.

#### Article 4 (Data Stored Only on Your Device)

The App also stores the following data in your device's local storage, used for offline play and faster display. It is not transmitted off your device except when submitting scores.

- Your best score per mode
- Player profile (player name, country, UI language, ad-removal purchase state)
- Achievement unlock state
- Pending score submissions (created while offline and deleted after being sent upon reconnection)

Uninstalling the App deletes the on-device data. Because the anonymous UID is issued per device, scores and achievements stored in the cloud cannot be restored after uninstalling.

#### Article 5 (Usage Analytics — Firebase Analytics)

The App uses Google Firebase Analytics to improve features and understand usage. The following events are recorded:

- `game_start` / `game_finish` (score) / `mode_select`
- `ranking_view` / `ad_view` / `share_score`

In addition to these events, Firebase Analytics automatically collects standard information such as device model, OS version, coarse region, app version, language, and a Google-issued app-instance identifier (pseudonymous ID). This is used for statistical analysis and not to identify you personally. Google's handling follows Google's Privacy Policy (<https://policies.google.com/privacy>) and "How Google uses information from sites or apps that use our services" (<https://policies.google.com/technologies/partner-sites>).

#### Article 6 (Crash Reporting — Firebase Crashlytics)

The App uses Firebase Crashlytics to detect and fix defects. When the App crashes, diagnostic information such as the stack trace, device model, OS version, and app state is sent to Google. This information does not include personal information such as your name or email address.

#### Article 7 (Remote Configuration — Firebase Remote Config)

The App fetches configuration values from Firebase Remote Config to adjust events, leaderboard display, and ad settings. Google may observe your IP address during the fetch, but the App transmits no identifying user information.

#### Article 8 (Advertising — Google AdMob / UMP)

Because the App is provided free of charge, it displays ads via Google AdMob (a banner ad on the result screen and an optional rewarded ad).

- AdMob may reference an advertising identifier (Android: Advertising ID, iOS: IDFA) to serve ads.
- In the European Economic Area (EEA), the UK, and similar regions, the App presents a **consent screen** via Google UMP (User Messaging Platform) and follows your choices (e.g., whether to allow personalized ads).
- If you do not consent, or in applicable regions, **only non-personalized ads** are served.
- AdMob's privacy practices follow Google's policy (<https://policies.google.com/technologies/ads>).
- Purchasing "Remove ads" (see below) stops ads from being displayed.

#### Article 9 (In-App Purchases — Unity IAP)

The App offers a one-time "Remove ads" in-app purchase.

- Payment is processed by the Apple App Store (iOS) or Google Play (Android); the Developer does not receive payment details such as credit card numbers.
- To verify and restore purchases, the App references purchase receipts and transaction information managed by each store. Their handling follows Apple's / Google's policies.
- The purchase state (whether ads are removed) is stored on your device.

#### Article 10 (Social Sharing)

Using "Share" on the result screen, you may, at your discretion, share text containing the mode name, score, world rank, and a hashtag to a social app you choose (X / LINE / Facebook / Instagram, etc.). Sharing is initiated by your action, and handling at the destination follows that service's policy.

#### Article 11 (Third-Party Sharing)

The App does not disclose or provide your information to third parties, except where it entrusts processing to the relevant service providers (Google / Apple / Unity) to the extent necessary to provide the functions described in Articles 5–10, or where required by law. Note that information shown on the public leaderboard (Article 3) is, by its nature, visible to all users.

#### Article 12 (Children's Use)

The App **is not directed at users under 13 years of age**. Ads in the App are served by AdMob. Parents and guardians are responsible for managing installation, use, and purchases by users under 13. If the Developer becomes aware that information from a user under 13 has been transmitted, the Developer will promptly delete it.

#### Article 13 (Your Rights)

You have the following rights:

- **Data deletion**: Uninstalling the App deletes on-device data. To delete your cloud-stored score, profile, and achievements, contact us (Article 16); if you provide your anonymous UID, we will delete that data.
- **Changing displayed information**: You can change your player name, country, and language at any time on the Settings screen.
- **Ad opt-out**: From your device settings (iOS: Settings > Privacy & Security > Tracking; Android: Settings > Google > Ads), you can reset the advertising identifier or limit tracking. In the EEA / UK, you can re-configure consent from the in-app consent management.
- **GDPR / CCPA**: Users in the EEA, UK, California, and similar jurisdictions may exercise rights such as access, deletion, and opt-out under applicable law. Please contact us via Article 16.

#### Article 14 (Data Retention and Security)

Cloud data is stored in Google Cloud (Firebase / Firestore) and access-controlled by Firestore Security Rules. Daily and weekly leaderboard scores are automatically deleted after a period (Daily: about 2 days after the period ends; Weekly: about 2 days after the period ends; All Time: retained).

#### Article 15 (Governing Law)

This Policy shall be interpreted and applied in accordance with the laws of Japan.

#### Article 16 (Contact / Changes to This Policy)

For questions about this Policy or to request data deletion, please contact:

- Email: `support@haroworks.com`

The Developer may revise this Policy when required by changes in applicable laws or in the App's features. Revised versions take effect once posted on this HTTPS page and on the store listings. Material changes will additionally be communicated via in-app notifications or release notes.

---

**Revision history**

- v1.0 (2026-06-12): Initial draft, in effect with the v1.0.0 MVP release.

---

<a id="zh-hans"></a>

## §C. 简体中文 (zh-Hans)

> 本译文仅供参考。如本译文与日文版（§A）或英文版（§B）之间存在任何差异，以日文版为准。

### 连打名人 / Tap Champion 隐私政策

本应用同时在 iOS 和 Android 两个平台发布。由于两个平台的后端配置相同，本政策同时适用于两者；平台特有的事项会在正文中注明。

本政策规定了连打名人（Tap Champion，以下简称"本应用"）对个人信息及用户数据的处理方式。本应用的提供者 HaroWorks（以下简称"开发者"）按以下方式处理个人信息及用户数据。

#### 第 1 条（适用范围）

本政策适用于开发者通过 Apple App Store 和 Google Play 发布的移动应用"连打名人 / Tap Champion"的所有用户。自开始使用本应用之时起，即视为用户已同意本政策。

#### 第 2 条（账户与匿名认证）

本应用无需登记姓名、电子邮件地址、电话号码等信息。首次启动时，本应用会通过 Firebase Authentication 的**匿名登录**自动生成一个用于识别用户的随机匿名 ID（匿名 UID）。

- 匿名 UID 不与姓名、电子邮件地址、电话号码或其他任何联系信息相关联。
- 本应用不提供社交账号登录或会员注册功能。
- 匿名 UID 用于向排行榜提交分数以及保存成就。

#### 第 3 条（收集和发送的信息）

为提供在线排行榜功能，本应用会将以下信息发送并保存至开发者的云端后端（Google Cloud Firestore）。

| 项目 | 内容 | 公开范围 |
| --- | --- | --- |
| 玩家名称（displayName） | 用户设置的 1～12 个字符的显示名称；初始值为自动生成的"Player + 数字" | 显示在公开排行榜上 |
| 国家/地区（countryCode） | 用户选择的国家/地区（用于显示国旗，ISO 3166-1 alpha-2）；初始值根据设备的语言设置推定 | 显示在公开排行榜上 |
| 分数（score） | 各模式的最佳分数 | 显示在公开排行榜上 |
| 模式 / 期间 | A / AB / ABC / ABCD，以及 Daily / Weekly / All Time 的区分 | 显示在公开排行榜上 |
| 更新时间（updatedAt） | 分数更新时的服务器时间 | 显示在公开排行榜上 |
| 成就解锁状态 | 各项成就的解锁时间 | 不公开（仅限本人） |

**关于公开排行榜**：上述信息中，玩家名称、国家/地区、分数和更新时间将作为世界排名向其他所有用户公开显示。请勿将真实姓名或可识别个人身份的信息设置为玩家名称（可随时在设置画面中更改）。

本应用可离线游玩。仅在提交分数至排行榜、浏览排行榜，以及下文所述的分析、广告和购买处理等情形下才会进行通信。

#### 第 4 条（仅保存在设备上的数据）

本应用还会将以下数据保存在用户设备的本地存储中。这些数据用于离线游玩和加快显示速度，除提交分数至排行榜时外，不会发送到设备之外。

- 各模式的个人最佳分数
- 玩家资料（玩家名称、国家/地区、界面语言、"去除广告"的购买状态）
- 成就解锁状态
- 等待提交至排行榜的保留数据（在离线时生成，恢复联网并发送后删除）

卸载本应用后，设备上的数据将被删除。由于匿名 UID 是按设备发放的，卸载后将无法恢复保存在云端的分数和成就。

#### 第 5 条（使用情况分析 — Firebase Analytics）

为改进功能和了解使用情况，本应用使用 Google 的 Firebase Analytics，并记录以下事件：

- `game_start`（游戏开始）/ `game_finish`（游戏结束・分数）/ `mode_select`（模式选择）
- `ranking_view`（浏览排行榜）/ `ad_view`（广告展示）/ `share_score`（分享分数）

除上述事件外，Firebase Analytics 还会自动收集设备型号、操作系统版本、大致地区、应用版本、语言设置以及 Google 发放的应用实例标识符（假名 ID）等标准信息。这些信息用于统计分析，不用于识别用户个人身份。Google 对这些信息的处理遵循 Google 隐私权政策（<https://policies.google.com/privacy>）以及"Google 如何使用来自使用我们服务的网站或应用的信息"（<https://policies.google.com/technologies/partner-sites>）。

#### 第 6 条（崩溃报告 — Firebase Crashlytics）

为检测和修复故障，本应用使用 Firebase Crashlytics。本应用崩溃时，堆栈跟踪、设备型号、操作系统版本、应用状态等诊断信息将发送给 Google。这些信息不包含姓名、电子邮件地址等个人信息。

#### 第 7 条（远程配置 — Firebase Remote Config）

为调整活动运营、排行榜显示和广告显示，本应用会从 Firebase Remote Config 获取配置值。获取时 Google 可能会获知用户的 IP 地址，但本应用不会发送任何可识别用户的信息。

#### 第 8 条（广告 — Google AdMob / UMP）

由于本应用免费提供，因此会通过 Google AdMob 显示广告（结果画面的横幅广告，以及可自愿观看的激励广告）。

- AdMob 可能会为投放广告而参考广告标识符（Android：广告 ID；iOS：IDFA）。
- 在欧洲经济区（EEA）、英国等地区，本应用会通过 Google UMP（User Messaging Platform）显示**同意管理画面**，并遵从用户的选择（例如是否允许个性化广告）。
- 如果用户不同意，或在适用地区，将**仅投放非个性化广告**。
- AdMob 的隐私处理遵循 Google 的政策（<https://policies.google.com/technologies/ads>）。
- 通过应用内购买购入下述"去除广告"后，将不再显示广告。

#### 第 9 条（应用内购买 — Unity IAP）

本应用提供"去除广告"的一次性买断购买（应用内购买）。

- 支付由 Apple App Store（iOS）或 Google Play（Android）处理，开发者不会获取信用卡号等支付信息。
- 为验证和恢复购买，本应用会参考各商店管理的购买收据和交易信息。这些信息的处理遵循 Apple / Google 的政策。
- 购买状态（是否已去除广告）保存在设备上。

#### 第 10 条（社交分享）

通过结果画面的"分享"操作，用户可自行决定将包含模式名称、分数、世界排名和话题标签的文本分享至自己选择的社交平台或应用（X / LINE / Facebook / Instagram 等）。分享由用户的操作发起，分享目标处的处理遵循各服务的政策。

#### 第 11 条（向第三方提供）

除在提供第 5～10 条所述功能的必要范围内委托各服务提供者（Google / Apple / Unity）进行处理，以及依据法律法规要求披露的情形外，本应用不会向第三方披露或提供用户信息。此外，公开排行榜上显示的信息（第 3 条）因其性质，对所有用户公开。

#### 第 12 条（儿童使用）

本应用**不以未满 13 周岁的用户为对象**。应用内显示的广告由 AdMob 投放。请家长或监护人对未满 13 周岁用户的安装、使用及购买行为进行管理。如发现有未满 13 周岁用户的信息被发送，开发者将及时删除。

#### 第 13 条（用户的权利）

用户享有以下权利：

- **删除数据**：卸载本应用后，设备上的数据将被删除。如希望删除保存在云端的分数、资料和成就，请通过第 16 条所列的联系方式与我们联系。提供您的匿名 UID 后，我们将删除相应数据。
- **更改显示信息**：玩家名称、国家/地区和语言可随时在设置画面中更改。
- **广告选择退出**：可在设备设置中（iOS：设置 > 隐私与安全性 > 跟踪；Android：设置 > Google > 广告）重置广告标识符或限制跟踪。在 EEA / 英国等地区，可通过应用内的同意管理重新设置。
- **GDPR / CCPA**：欧洲经济区、英国、美国加利福尼亚州等地区的用户，可依据适用法律行使访问、删除、选择退出等权利。请通过第 16 条与我们联系。

#### 第 14 条（数据的保存与安全）

云端数据保存在 Google Cloud（Firebase / Firestore）中，并通过 Firestore Security Rules 进行访问控制。排行榜的每日和每周分数将在一定期间后自动删除（Daily：期间结束约 2 天后；Weekly：期间结束约 2 天后；All Time：保留）。

#### 第 15 条（准据法）

本政策的解释和适用以日本国法律为准据法。

#### 第 16 条（联系方式・本政策的变更）

如对本政策有任何疑问或希望申请删除数据，请通过以下方式联系我们：

- 电子邮件：`support@haroworks.com`

本政策可能因相关法律法规的修订或服务内容的变更等而进行修订。修订后的政策自在本 HTTPS 公开页面及各商店的应用详情页面上发布之时起生效。如有重大变更，我们还将通过应用内通知或版本说明进行告知。

---

**修订历史**

- v1.0（2026-06-12）：初版制定（随 v1.0.0 MVP 发布生效）。

---

<a id="zh-hant"></a>

## §D. 繁體中文 (zh-Hant)

> 本譯文僅供參考。如本譯文與日文版（§A）或英文版（§B）之間有任何歧異，以日文版為準。

### 連打名人 / Tap Champion 隱私權政策

本應用程式同時於 iOS 及 Android 兩個平台發布。由於兩個平台的後端配置相同，本政策同時適用於兩者；平台特有的事項會於本文中註明。

本政策規定連打名人（Tap Champion，以下簡稱「本應用程式」）對個人資料及使用者資料的處理方式。本應用程式的提供者 HaroWorks（以下簡稱「開發者」）依下列方式處理個人資料及使用者資料。

#### 第 1 條（適用範圍）

本政策適用於開發者透過 Apple App Store 及 Google Play 發布之行動應用程式「連打名人 / Tap Champion」的所有使用者。自開始使用本應用程式之時起，即視為使用者已同意本政策。

#### 第 2 條（帳號與匿名驗證）

本應用程式無需登錄姓名、電子郵件地址、電話號碼等資訊。首次啟動時，本應用程式會透過 Firebase Authentication 的**匿名登入**，自動產生一組用於識別使用者的隨機匿名 ID（匿名 UID）。

- 匿名 UID 不與姓名、電子郵件地址、電話號碼或其他任何聯絡資訊相關聯。
- 本應用程式不提供社群帳號登入或會員註冊功能。
- 匿名 UID 用於向排行榜提交分數及儲存成就。

#### 第 3 條（蒐集及傳送的資訊）

為提供線上排行榜功能，本應用程式會將下列資訊傳送並儲存至開發者的雲端後端（Google Cloud Firestore）。

| 項目 | 內容 | 公開範圍 |
| --- | --- | --- |
| 玩家名稱（displayName） | 使用者設定的 1～12 個字元的顯示名稱；初始值為自動產生的「Player + 數字」 | 顯示於公開排行榜 |
| 國家/地區（countryCode） | 使用者選擇的國家/地區（用於顯示國旗，ISO 3166-1 alpha-2）；初始值依裝置的語言設定推定 | 顯示於公開排行榜 |
| 分數（score） | 各模式的最佳分數 | 顯示於公開排行榜 |
| 模式 / 期間 | A / AB / ABC / ABCD，以及 Daily / Weekly / All Time 的區分 | 顯示於公開排行榜 |
| 更新時間（updatedAt） | 分數更新時的伺服器時間 | 顯示於公開排行榜 |
| 成就解鎖狀態 | 各項成就的解鎖時間 | 不公開（僅限本人） |

**關於公開排行榜**：上述資訊中，玩家名稱、國家/地區、分數及更新時間將作為世界排名向其他所有使用者公開顯示。請勿將真實姓名或可識別個人身分的資訊設定為玩家名稱（可隨時於設定畫面中變更）。

本應用程式可離線遊玩。僅於提交分數至排行榜、瀏覽排行榜，以及下文所述的分析、廣告及購買處理等情形下才會進行通訊。

#### 第 4 條（僅儲存於裝置上的資料）

本應用程式亦會將下列資料儲存於使用者裝置的本機儲存空間。這些資料用於離線遊玩及加快顯示速度，除提交分數至排行榜時外，不會傳送至裝置之外。

- 各模式的個人最佳分數
- 玩家資料（玩家名稱、國家/地區、介面語言、「移除廣告」的購買狀態）
- 成就解鎖狀態
- 等待提交至排行榜的保留資料（於離線時產生，恢復連線並傳送後刪除）

解除安裝本應用程式後，裝置上的資料將被刪除。由於匿名 UID 是依裝置發放，解除安裝後將無法復原儲存於雲端的分數及成就。

#### 第 5 條（使用情況分析 — Firebase Analytics）

為改善功能及了解使用情況，本應用程式使用 Google 的 Firebase Analytics，並記錄下列事件：

- `game_start`（遊戲開始）/ `game_finish`（遊戲結束・分數）/ `mode_select`（模式選擇）
- `ranking_view`（瀏覽排行榜）/ `ad_view`（廣告顯示）/ `share_score`（分享分數）

除上述事件外，Firebase Analytics 亦會自動蒐集裝置型號、作業系統版本、大致地區、應用程式版本、語言設定，以及 Google 發放的應用程式執行個體識別碼（假名 ID）等標準資訊。這些資訊用於統計分析，不會用於識別使用者個人身分。Google 對這些資訊的處理遵循 Google 隱私權政策（<https://policies.google.com/privacy>）及「Google 如何使用來自採用 Google 服務之網站或應用程式的資訊」（<https://policies.google.com/technologies/partner-sites>）。

#### 第 6 條（當機報告 — Firebase Crashlytics）

為偵測及修正錯誤，本應用程式使用 Firebase Crashlytics。本應用程式當機時，堆疊追蹤、裝置型號、作業系統版本、應用程式狀態等診斷資訊將傳送給 Google。這些資訊不包含姓名、電子郵件地址等個人資料。

#### 第 7 條（遠端設定 — Firebase Remote Config）

為調整活動營運、排行榜顯示及廣告顯示，本應用程式會從 Firebase Remote Config 取得設定值。取得時 Google 可能會得知使用者的 IP 位址，但本應用程式不會傳送任何可識別使用者的資訊。

#### 第 8 條（廣告 — Google AdMob / UMP）

由於本應用程式免費提供，因此會透過 Google AdMob 顯示廣告（結果畫面的橫幅廣告，以及可自願觀看的獎勵廣告）。

- AdMob 可能會為投放廣告而參考廣告識別碼（Android：廣告 ID；iOS：IDFA）。
- 於歐洲經濟區（EEA）、英國等地區，本應用程式會透過 Google UMP（User Messaging Platform）顯示**同意管理畫面**，並依循使用者的選擇（例如是否允許個人化廣告）。
- 如使用者不同意，或於適用地區，將**僅投放非個人化廣告**。
- AdMob 的隱私處理遵循 Google 的政策（<https://policies.google.com/technologies/ads>）。
- 透過應用程式內購買購入下述「移除廣告」後，將不再顯示廣告。

#### 第 9 條（應用程式內購買 — Unity IAP）

本應用程式提供「移除廣告」的一次性買斷購買（應用程式內購買）。

- 付款由 Apple App Store（iOS）或 Google Play（Android）處理，開發者不會取得信用卡號碼等付款資訊。
- 為驗證及恢復購買，本應用程式會參考各商店管理的購買收據及交易資訊。這些資訊的處理遵循 Apple / Google 的政策。
- 購買狀態（是否已移除廣告）儲存於裝置上。

#### 第 10 條（社群分享）

透過結果畫面的「分享」操作，使用者可自行決定將包含模式名稱、分數、世界排名及主題標籤的文字分享至自己選擇的社群平台或應用程式（X / LINE / Facebook / Instagram 等）。分享由使用者的操作發起，分享目的地的處理遵循各服務的政策。

#### 第 11 條（提供予第三方）

除於提供第 5～10 條所述功能的必要範圍內委託各服務提供者（Google / Apple / Unity）進行處理，以及依法令要求揭露的情形外，本應用程式不會向第三方揭露或提供使用者資訊。此外，公開排行榜上顯示的資訊（第 3 條）因其性質，對所有使用者公開。

#### 第 12 條（兒童使用）

本應用程式**不以未滿 13 歲的使用者為對象**。應用程式內顯示的廣告由 AdMob 投放。請家長或監護人管理未滿 13 歲使用者的安裝、使用及購買行為。如發現有未滿 13 歲使用者的資訊被傳送，開發者將儘速刪除。

#### 第 13 條（使用者的權利）

使用者享有下列權利：

- **刪除資料**：解除安裝本應用程式後，裝置上的資料將被刪除。如希望刪除儲存於雲端的分數、個人資料及成就，請透過第 16 條所列的聯絡方式與我們聯繫。提供您的匿名 UID 後，我們將刪除相應資料。
- **變更顯示資訊**：玩家名稱、國家/地區及語言可隨時於設定畫面中變更。
- **廣告選擇退出**：可於裝置設定中（iOS：設定 > 隱私權與安全性 > 追蹤；Android：設定 > Google > 廣告）重設廣告識別碼或限制追蹤。於 EEA / 英國等地區，可透過應用程式內的同意管理重新設定。
- **GDPR / CCPA**：歐洲經濟區、英國、美國加州等地區的使用者，可依適用法律行使存取、刪除、選擇退出等權利。請透過第 16 條與我們聯繫。

#### 第 14 條（資料的保存與安全）

雲端資料儲存於 Google Cloud（Firebase / Firestore），並透過 Firestore Security Rules 進行存取控制。排行榜的每日及每週分數將於一定期間後自動刪除（Daily：期間結束約 2 天後；Weekly：期間結束約 2 天後；All Time：保留）。

#### 第 15 條（準據法）

本政策的解釋及適用，以日本國法律為準據法。

#### 第 16 條（聯絡方式・本政策的變更）

如對本政策有任何疑問或希望申請刪除資料，請透過下列方式與我們聯繫：

- 電子郵件：`support@haroworks.com`

本政策可能因相關法令修訂或服務內容變更等而進行修訂。修訂後的政策自於本 HTTPS 公開頁面及各商店的應用程式詳細資料頁面上公布之時起生效。如有重大變更，我們亦將透過應用程式內通知或版本說明進行告知。

---

**修訂歷程**

- v1.0（2026-06-12）：初版制定（隨 v1.0.0 MVP 發布生效）。

---

<a id="ko"></a>

## §E. 한국어 (ko)

> 본 번역은 참고용입니다. 본 번역과 일본어판(§A) 또는 영어판(§B) 사이에 차이가 있는 경우 일본어판이 우선합니다.

### 연타 명인 / Tap Champion 개인정보 처리방침

본 앱은 iOS 및 Android 두 플랫폼에서 배포됩니다. 백엔드 구성이 두 플랫폼에서 동일하므로 본 방침은 두 플랫폼 모두를 대상으로 하며, 플랫폼별 사항은 본문 중에 별도로 표기합니다.

본 방침은 연타 명인(Tap Champion, 이하 "본 앱")에서의 개인정보 및 이용자 데이터의 처리에 관하여 정합니다. 본 앱의 제공자 HaroWorks(이하 "개발자")는 다음과 같이 개인정보 및 이용자 데이터를 처리합니다.

#### 제1조 (적용 범위)

본 방침은 개발자가 Apple App Store 및 Google Play에서 배포하는 모바일 앱 "연타 명인 / Tap Champion"의 모든 이용자에게 적용됩니다. 이용자는 본 앱의 이용을 시작한 시점에 본 방침에 동의한 것으로 간주됩니다.

#### 제2조 (계정 및 익명 인증)

본 앱은 이름, 이메일 주소, 전화번호 등의 등록을 요구하지 않습니다. 최초 실행 시 Firebase Authentication의 **익명 로그인**을 통해 이용자를 식별하기 위한 무작위 익명 ID(익명 UID)를 자동으로 발급합니다.

- 익명 UID에는 이름, 이메일 주소, 전화번호, 그 밖의 연락처 정보가 일절 연결되지 않습니다.
- 본 앱에는 소셜 로그인이나 회원 가입 기능이 없습니다.
- 익명 UID는 랭킹에 점수를 전송하고 업적을 저장하는 데 사용됩니다.

#### 제3조 (수집·전송하는 정보)

본 앱은 온라인 랭킹 기능을 제공하기 위해 다음 정보를 개발자의 클라우드 백엔드(Google Cloud Firestore)에 전송·저장합니다.

| 항목 | 내용 | 공개 범위 |
| --- | --- | --- |
| 플레이어 이름(displayName) | 이용자가 설정하는 1~12자의 표시 이름. 초기값은 자동 생성되는 "Player + 숫자" | 공개 랭킹에 표시 |
| 국가(countryCode) | 이용자가 선택하는 국가(국기 표시용, ISO 3166-1 alpha-2). 초기값은 기기의 언어 설정으로부터 추정 | 공개 랭킹에 표시 |
| 점수(score) | 각 모드의 최고 점수 | 공개 랭킹에 표시 |
| 모드 / 기간 | A / AB / ABC / ABCD, Daily / Weekly / All Time 구분 | 공개 랭킹에 표시 |
| 갱신 일시(updatedAt) | 점수가 갱신된 서버 시각 | 공개 랭킹에 표시 |
| 업적 달성 상태 | 각 업적의 달성 일시 | 비공개(본인만) |

**공개 랭킹에 대하여**: 위 항목 중 플레이어 이름, 국가, 점수, 갱신 일시는 세계 랭킹으로서 다른 모든 이용자에게 공개 표시됩니다. 플레이어 이름에 실명이나 개인을 식별할 수 있는 정보를 설정하지 마십시오(설정 화면에서 언제든지 변경할 수 있습니다).

본 앱은 플레이 자체를 오프라인으로 할 수 있습니다. 통신은 랭킹 점수 전송, 랭킹 열람, 그리고 후술하는 분석·광고·결제 처리의 각 경우에만 발생합니다.

#### 제4조 (기기 내에만 저장되는 데이터)

본 앱은 다음 데이터를 이용자의 기기 내 저장소에도 저장합니다. 이 데이터는 오프라인 플레이 및 표시 속도 향상을 위해 사용되며, 랭킹 전송 시를 제외하고 기기 밖으로 전송되지 않습니다.

- 각 모드의 개인 최고 점수
- 플레이어 프로필(플레이어 이름, 국가, UI 언어, 광고 제거 구매 상태)
- 업적 달성 상태
- 랭킹 전송 대기 중인 보류 데이터(오프라인 시 생성되며, 온라인 복귀 후 전송되면 삭제)

앱을 삭제하면 기기 내 데이터는 삭제됩니다. 익명 UID는 기기별로 발급되므로 앱 삭제 후에는 클라우드에 저장된 점수와 업적을 복원할 수 없습니다.

#### 제5조 (이용 현황 분석 — Firebase Analytics)

본 앱은 기능 개선 및 이용 현황 파악을 위해 Google의 Firebase Analytics를 이용합니다. 다음 이벤트가 기록됩니다.

- `game_start`(게임 시작) / `game_finish`(게임 종료·점수) / `mode_select`(모드 선택)
- `ranking_view`(랭킹 열람) / `ad_view`(광고 표시) / `share_score`(점수 공유)

Firebase Analytics는 위 이벤트 외에도 기기 모델, OS 버전, 대략적인 지역, 앱 버전, 언어 설정, Google이 발급하는 앱 인스턴스 식별자(가명 ID) 등의 표준적인 정보를 자동으로 수집합니다. 이 정보는 통계 분석에 사용되며, 이용자 개인을 식별할 목적으로는 사용하지 않습니다. Google의 처리는 Google 개인정보처리방침(<https://policies.google.com/privacy>) 및 "Google 서비스를 사용하는 사이트 또는 앱에서 수집한 정보를 Google이 사용하는 방법"(<https://policies.google.com/technologies/partner-sites>)을 따릅니다.

#### 제6조 (비정상 종료 보고 — Firebase Crashlytics)

본 앱은 결함의 검출 및 수정을 위해 Firebase Crashlytics를 이용합니다. 앱이 비정상 종료된 경우 스택 트레이스, 기기 모델, OS 버전, 앱 상태 등의 진단 정보가 Google에 전송됩니다. 이 정보에는 이름, 이메일 주소 등의 개인정보가 포함되지 않습니다.

#### 제7조 (원격 구성 — Firebase Remote Config)

본 앱은 이벤트 운영, 랭킹 표시, 광고 표시를 조정하기 위해 Firebase Remote Config에서 설정값을 가져옵니다. 가져올 때 Google이 이용자의 IP 주소를 참조하지만, 본 앱은 이용자 식별 정보를 전송하지 않습니다.

#### 제8조 (광고 — Google AdMob / UMP)

본 앱은 무료로 제공되므로 Google AdMob을 통한 광고(결과 화면의 배너 광고 및 선택적으로 시청하는 보상형 광고)를 표시합니다.

- AdMob은 광고 게재를 위해 광고 식별자(Android: 광고 ID, iOS: IDFA)를 참조할 수 있습니다.
- 유럽경제지역(EEA), 영국 등에서는 Google UMP(User Messaging Platform)를 통한 **동의 관리 화면**을 표시하고, 이용자의 선택(맞춤형 광고 허용 여부 등)에 따릅니다.
- 이용자가 동의하지 않는 경우 또는 해당 지역에서는 **비맞춤형 광고**만 게재됩니다.
- AdMob의 개인정보 처리는 Google의 정책(<https://policies.google.com/technologies/ads>)을 따릅니다.
- 후술하는 "광고 제거"를 인앱 결제로 구매하면 광고가 더 이상 표시되지 않습니다.

#### 제9조 (인앱 결제 — Unity IAP)

본 앱은 "광고 제거"의 1회 구매형 결제(인앱 결제)를 제공합니다.

- 결제 처리는 Apple App Store(iOS) 또는 Google Play(Android)가 수행하며, 개발자는 신용카드 번호 등의 결제 정보를 취득하지 않습니다.
- 구매 검증 및 복원을 위해 각 스토어가 관리하는 구매 영수증 및 거래 정보를 참조합니다. 이러한 정보의 처리는 Apple / Google의 정책을 따릅니다.
- 구매 상태(광고 제거 여부)는 기기 내에 저장됩니다.

#### 제10조 (SNS 공유)

결과 화면의 "공유" 조작을 통해 이용자는 자신의 의사에 따라 모드 이름, 점수, 세계 순위, 해시태그가 포함된 텍스트를 이용자가 선택한 SNS·앱(X / LINE / Facebook / Instagram 등)에 공유할 수 있습니다. 공유는 이용자의 조작을 계기로 발생하며, 공유 대상에서의 처리는 각 서비스의 정책을 따릅니다.

#### 제11조 (제3자 제공)

본 앱은 제5조~제10조에 기재된 기능 제공에 필요한 범위에서 각 서비스 제공자(Google / Apple / Unity)에게 처리를 위탁하는 경우 및 법령에 따른 공개 요청이 있는 경우를 제외하고, 이용자의 정보를 제3자에게 공개·제공하지 않습니다. 또한 공개 랭킹에 표시되는 정보(제3조)는 그 성질상 모든 이용자에게 공개됩니다.

#### 제12조 (아동의 이용)

본 앱은 **만 13세 미만의 이용자를 대상으로 하지 않습니다**. 앱 내에 표시되는 광고는 AdMob을 통해 게재됩니다. 보호자께서는 만 13세 미만 이용자의 설치·이용 및 결제를 관리해 주십시오. 만약 만 13세 미만 이용자의 정보가 전송된 사실이 확인된 경우, 개발자는 이를 신속히 삭제합니다.

#### 제13조 (이용자의 권리)

이용자는 다음과 같은 권리를 가집니다.

- **데이터 삭제**: 앱을 삭제하면 기기 내 데이터는 삭제됩니다. 클라우드에 저장된 점수·프로필·업적의 삭제를 원하시는 경우 제16조의 문의처로 연락해 주십시오. 익명 UID를 알려 주시면 해당 데이터를 삭제합니다.
- **표시 정보 변경**: 플레이어 이름, 국가, 언어는 설정 화면에서 언제든지 변경할 수 있습니다.
- **광고 수신 거부(옵트아웃)**: 기기 설정(iOS: 설정 > 개인정보 보호 및 보안 > 추적, Android: 설정 > Google > 광고)에서 광고 식별자를 재설정하거나 추적을 제한할 수 있습니다. EEA / 영국 등에서는 앱 내 동의 관리에서 다시 설정할 수 있습니다.
- **GDPR / CCPA**: 유럽경제지역, 영국, 캘리포니아주 등의 이용자는 적용 법령에 따라 열람·삭제·옵트아웃 등의 권리를 행사할 수 있습니다. 제16조를 통해 연락해 주십시오.

#### 제14조 (데이터 보관 및 보안)

클라우드상의 데이터는 Google Cloud(Firebase / Firestore)에 보관되며, Firestore Security Rules를 통해 접근이 제어됩니다. 랭킹의 일간·주간 점수는 일정 기간이 지나면 자동으로 삭제됩니다(Daily는 기간 종료 약 2일 후, Weekly는 기간 종료 약 2일 후, All Time은 보관).

#### 제15조 (준거법)

본 방침의 해석 및 적용은 일본국 법률에 따릅니다.

#### 제16조 (문의·본 방침의 변경)

본 방침에 관한 문의 및 데이터 삭제 요청은 아래로 연락해 주십시오.

- 이메일: `support@haroworks.com`

본 방침은 관련 법령의 개정, 서비스 내용의 변경 등에 따라 개정될 수 있습니다. 개정된 방침은 본 HTTPS 공개 페이지 및 각 스토어의 앱 상세 페이지에 게시된 시점부터 효력이 발생합니다. 중요한 변경이 있는 경우 앱 내 알림 또는 릴리스 노트를 통해 알려 드립니다.

---

**개정 이력**

- v1.0 (2026-06-12): 최초 제정(v1.0.0 MVP 출시와 함께 시행).

---

<a id="es"></a>

## §F. Español (es)

> Esta traducción se proporciona solo como referencia. En caso de discrepancia entre esta traducción y la versión en japonés (§A) o en inglés (§B), prevalecerá la versión en japonés.

### Política de privacidad de Tap Champion

La App se distribuye tanto en iOS como en Android. Dado que el backend es idéntico en ambas plataformas, esta Política se aplica a las dos; los aspectos específicos de cada plataforma se indican en el texto.

Esta Política de privacidad describe cómo Tap Champion (la "App") trata la información personal y los datos de los usuarios. El desarrollador de la App, HaroWorks (el "Desarrollador"), trata la información personal y los datos de los usuarios de la siguiente manera.

#### Artículo 1 (Ámbito de aplicación)

Esta Política se aplica a todos los usuarios de la aplicación móvil "Tap Champion" distribuida por el Desarrollador a través de Apple App Store y Google Play. Al comenzar a usar la App, se considera que usted ha aceptado esta Política.

#### Artículo 2 (Cuentas y autenticación anónima)

La App no requiere registrar su nombre, dirección de correo electrónico, número de teléfono ni información similar. En el primer inicio, emite automáticamente un identificador anónimo aleatorio (UID anónimo) mediante el **inicio de sesión anónimo** de Firebase Authentication para identificarle.

- El UID anónimo no está asociado a ningún nombre, dirección de correo electrónico, número de teléfono ni otra información de contacto.
- La App no dispone de inicio de sesión con redes sociales ni de registro de miembros.
- El UID anónimo se utiliza para enviar puntuaciones a la clasificación y para guardar los logros.

#### Artículo 3 (Información que recopilamos y transmitimos)

Para ofrecer la clasificación en línea, la App transmite y almacena la siguiente información en el backend en la nube del Desarrollador (Google Cloud Firestore).

| Elemento | Contenido | Visibilidad |
| --- | --- | --- |
| Nombre de jugador (displayName) | Nombre visible de 1 a 12 caracteres que usted establece; por defecto, se genera automáticamente "Player + número" | Se muestra en la clasificación pública |
| País (countryCode) | País que usted selecciona para la bandera (ISO 3166-1 alfa-2); por defecto, se estima a partir del idioma del dispositivo | Se muestra en la clasificación pública |
| Puntuación (score) | Su mejor puntuación en cada modo | Se muestra en la clasificación pública |
| Modo / Período | A / AB / ABC / ABCD, y Daily / Weekly / All Time | Se muestra en la clasificación pública |
| Hora de actualización (updatedAt) | Hora del servidor en que se actualizó su puntuación | Se muestra en la clasificación pública |
| Estado de desbloqueo de logros | Fecha y hora de desbloqueo de cada logro | Privado (solo usted) |

**Sobre la clasificación pública**: de lo anterior, su nombre de jugador, país, puntuación y hora de actualización se muestran públicamente a todos los demás usuarios como parte de la clasificación mundial. No utilice su nombre real ni información que permita identificarle personalmente como nombre de jugador (puede cambiarlo en cualquier momento en la pantalla de Ajustes).

La App se puede jugar sin conexión. Solo se produce comunicación al enviar puntuaciones, al consultar la clasificación y para las funciones de análisis, publicidad y compras descritas a continuación.

#### Artículo 4 (Datos almacenados solo en su dispositivo)

La App también almacena los siguientes datos en el almacenamiento local de su dispositivo, que se utilizan para jugar sin conexión y para agilizar la visualización. No se transmiten fuera de su dispositivo, salvo al enviar puntuaciones.

- Su mejor puntuación en cada modo
- Perfil de jugador (nombre de jugador, país, idioma de la interfaz, estado de compra de la eliminación de anuncios)
- Estado de desbloqueo de logros
- Envíos de puntuación pendientes (creados sin conexión y eliminados tras enviarse al recuperar la conexión)

Al desinstalar la App se eliminan los datos del dispositivo. Como el UID anónimo se emite por dispositivo, las puntuaciones y los logros almacenados en la nube no se pueden restaurar tras la desinstalación.

#### Artículo 5 (Análisis de uso — Firebase Analytics)

La App utiliza Firebase Analytics de Google para mejorar sus funciones y comprender su uso. Se registran los siguientes eventos:

- `game_start` (inicio de partida) / `game_finish` (fin de partida y puntuación) / `mode_select` (selección de modo)
- `ranking_view` (consulta de la clasificación) / `ad_view` (visualización de anuncio) / `share_score` (compartir puntuación)

Además de estos eventos, Firebase Analytics recopila automáticamente información estándar como el modelo del dispositivo, la versión del sistema operativo, la región aproximada, la versión de la App, el idioma y un identificador de instancia de la aplicación emitido por Google (ID seudónimo). Esta información se utiliza para análisis estadísticos y no para identificarle personalmente. El tratamiento por parte de Google se rige por la Política de privacidad de Google (<https://policies.google.com/privacy>) y por "Cómo utiliza Google la información de sitios web o aplicaciones que utilizan sus servicios" (<https://policies.google.com/technologies/partner-sites>).

#### Artículo 6 (Informes de errores — Firebase Crashlytics)

La App utiliza Firebase Crashlytics para detectar y corregir defectos. Cuando la App se bloquea, se envía a Google información de diagnóstico como el seguimiento de la pila, el modelo del dispositivo, la versión del sistema operativo y el estado de la App. Esta información no incluye datos personales como su nombre o dirección de correo electrónico.

#### Artículo 7 (Configuración remota — Firebase Remote Config)

La App obtiene valores de configuración de Firebase Remote Config para ajustar los eventos, la visualización de la clasificación y la configuración de anuncios. Google puede ver su dirección IP durante la obtención, pero la App no transmite ninguna información que le identifique.

#### Artículo 8 (Publicidad — Google AdMob / UMP)

Como la App se ofrece de forma gratuita, muestra anuncios a través de Google AdMob (un anuncio de banner en la pantalla de resultados y un anuncio bonificado opcional).

- AdMob puede consultar un identificador de publicidad (Android: ID de publicidad; iOS: IDFA) para mostrar anuncios.
- En el Espacio Económico Europeo (EEE), el Reino Unido y regiones similares, la App muestra una **pantalla de consentimiento** mediante Google UMP (User Messaging Platform) y respeta sus elecciones (por ejemplo, si permite anuncios personalizados).
- Si usted no da su consentimiento, o en las regiones aplicables, **solo se muestran anuncios no personalizados**.
- Las prácticas de privacidad de AdMob se rigen por la política de Google (<https://policies.google.com/technologies/ads>).
- Si compra "Eliminar anuncios" (véase más abajo), los anuncios dejarán de mostrarse.

#### Artículo 9 (Compras dentro de la App — Unity IAP)

La App ofrece una compra única dentro de la App para "Eliminar anuncios".

- El pago lo procesa Apple App Store (iOS) o Google Play (Android); el Desarrollador no recibe datos de pago como números de tarjeta de crédito.
- Para verificar y restaurar compras, la App consulta los recibos de compra y la información de transacciones gestionados por cada tienda. Su tratamiento se rige por las políticas de Apple / Google.
- El estado de la compra (si se han eliminado los anuncios) se almacena en su dispositivo.

#### Artículo 10 (Compartir en redes sociales)

Mediante "Compartir" en la pantalla de resultados, usted puede, a su elección, compartir un texto que contiene el nombre del modo, la puntuación, la posición mundial y un hashtag en la red social o aplicación que elija (X / LINE / Facebook / Instagram, etc.). El acto de compartir se inicia por su acción, y el tratamiento en el destino se rige por la política de ese servicio.

#### Artículo 11 (Comunicación a terceros)

La App no divulga ni proporciona su información a terceros, salvo cuando encarga su tratamiento a los proveedores de servicios correspondientes (Google / Apple / Unity) en la medida necesaria para prestar las funciones descritas en los Artículos 5 a 10, o cuando lo exija la ley. Tenga en cuenta que la información mostrada en la clasificación pública (Artículo 3) es, por su naturaleza, visible para todos los usuarios.

#### Artículo 12 (Uso por menores)

La App **no está dirigida a usuarios menores de 13 años**. Los anuncios de la App son servidos por AdMob. Los padres y tutores son responsables de gestionar la instalación, el uso y las compras por parte de usuarios menores de 13 años. Si el Desarrollador tiene conocimiento de que se ha transmitido información de un usuario menor de 13 años, la eliminará sin demora.

#### Artículo 13 (Sus derechos)

Usted tiene los siguientes derechos:

- **Eliminación de datos**: al desinstalar la App se eliminan los datos del dispositivo. Para eliminar su puntuación, perfil y logros almacenados en la nube, póngase en contacto con nosotros (Artículo 16); si nos facilita su UID anónimo, eliminaremos esos datos.
- **Cambio de la información mostrada**: puede cambiar su nombre de jugador, país e idioma en cualquier momento en la pantalla de Ajustes.
- **Exclusión de la publicidad**: desde los ajustes de su dispositivo (iOS: Ajustes > Privacidad y seguridad > Rastreo; Android: Ajustes > Google > Anuncios), puede restablecer el identificador de publicidad o limitar el rastreo. En el EEE / Reino Unido, puede volver a configurar el consentimiento desde la gestión de consentimiento de la App.
- **RGPD / CCPA**: los usuarios del EEE, el Reino Unido, California y jurisdicciones similares pueden ejercer derechos como el acceso, la supresión y la exclusión conforme a la legislación aplicable. Póngase en contacto con nosotros según el Artículo 16.

#### Artículo 14 (Conservación y seguridad de los datos)

Los datos en la nube se almacenan en Google Cloud (Firebase / Firestore) y su acceso se controla mediante las Firestore Security Rules. Las puntuaciones de las clasificaciones diaria y semanal se eliminan automáticamente tras un período (Daily: unos 2 días después del final del período; Weekly: unos 2 días después del final del período; All Time: se conservan).

#### Artículo 15 (Legislación aplicable)

Esta Política se interpretará y aplicará de conformidad con las leyes de Japón.

#### Artículo 16 (Contacto / Cambios en esta Política)

Para preguntas sobre esta Política o para solicitar la eliminación de datos, póngase en contacto con:

- Correo electrónico: `support@haroworks.com`

El Desarrollador podrá revisar esta Política cuando así lo exijan cambios en la legislación aplicable o en las funciones de la App. Las versiones revisadas entran en vigor una vez publicadas en esta página HTTPS y en las fichas de las tiendas. Los cambios importantes se comunicarán además mediante notificaciones dentro de la App o notas de la versión.

---

**Historial de revisiones**

- v1.0 (2026-06-12): Versión inicial, en vigor con el lanzamiento del MVP v1.0.0.

---

<a id="fr"></a>

## §G. Français (fr)

> Cette traduction est fournie à titre indicatif uniquement. En cas de divergence entre cette traduction et la version japonaise (§A) ou anglaise (§B), la version japonaise prévaut.

### Politique de confidentialité de Tap Champion

L'Application est distribuée sur iOS et sur Android. Le backend étant identique sur les deux plateformes, la présente Politique couvre les deux ; les éléments propres à chaque plateforme sont signalés dans le texte.

La présente Politique de confidentialité décrit la manière dont Tap Champion (l'« Application ») traite les informations personnelles et les données des utilisateurs. Le développeur de l'Application, HaroWorks (le « Développeur »), traite les informations personnelles et les données des utilisateurs comme suit.

#### Article 1 (Champ d'application)

La présente Politique s'applique à tous les utilisateurs de l'application mobile « Tap Champion » distribuée par le Développeur via l'Apple App Store et Google Play. En commençant à utiliser l'Application, vous êtes réputé avoir accepté la présente Politique.

#### Article 2 (Comptes et authentification anonyme)

L'Application ne requiert pas l'enregistrement de votre nom, de votre adresse e-mail, de votre numéro de téléphone ou d'informations similaires. Au premier lancement, elle émet automatiquement un identifiant anonyme aléatoire (UID anonyme) via la **connexion anonyme** de Firebase Authentication afin de vous identifier.

- Aucun nom, aucune adresse e-mail, aucun numéro de téléphone ni aucune autre coordonnée n'est associé à l'UID anonyme.
- L'Application ne propose ni connexion via les réseaux sociaux ni inscription de membre.
- L'UID anonyme sert à envoyer les scores au classement et à enregistrer les succès.

#### Article 3 (Informations collectées et transmises)

Afin de fournir le classement en ligne, l'Application transmet et stocke les informations suivantes dans le backend cloud du Développeur (Google Cloud Firestore).

| Élément | Contenu | Visibilité |
| --- | --- | --- |
| Nom du joueur (displayName) | Nom d'affichage de 1 à 12 caractères que vous définissez ; par défaut, « Player + numéro » généré automatiquement | Affiché dans le classement public |
| Pays (countryCode) | Pays que vous sélectionnez pour le drapeau (ISO 3166-1 alpha-2) ; par défaut, déduit de la langue de votre appareil | Affiché dans le classement public |
| Score (score) | Votre meilleur score pour chaque mode | Affiché dans le classement public |
| Mode / Période | A / AB / ABC / ABCD, et Daily / Weekly / All Time | Affiché dans le classement public |
| Heure de mise à jour (updatedAt) | Heure du serveur à laquelle votre score a été mis à jour | Affiché dans le classement public |
| État de déblocage des succès | Date et heure de déblocage de chaque succès | Privé (vous uniquement) |

**À propos du classement public** : parmi ces éléments, votre nom de joueur, votre pays, votre score et l'heure de mise à jour sont affichés publiquement à tous les autres utilisateurs dans le cadre du classement mondial. N'utilisez pas votre vrai nom ni d'informations permettant de vous identifier personnellement comme nom de joueur (vous pouvez le modifier à tout moment dans l'écran Réglages).

L'Application peut être utilisée hors ligne. Une communication n'a lieu que lors de l'envoi des scores, de la consultation du classement, ainsi que pour les fonctions d'analyse, de publicité et d'achat décrites ci-dessous.

#### Article 4 (Données stockées uniquement sur votre appareil)

L'Application stocke également les données suivantes dans le stockage local de votre appareil ; elles servent au jeu hors ligne et à accélérer l'affichage. Elles ne sont pas transmises hors de votre appareil, sauf lors de l'envoi des scores.

- Votre meilleur score pour chaque mode
- Profil du joueur (nom du joueur, pays, langue de l'interface, état de l'achat de suppression des publicités)
- État de déblocage des succès
- Envois de scores en attente (créés hors ligne et supprimés après leur envoi lors de la reconnexion)

La désinstallation de l'Application supprime les données présentes sur l'appareil. L'UID anonyme étant émis par appareil, les scores et succès stockés dans le cloud ne peuvent pas être restaurés après la désinstallation.

#### Article 5 (Analyse d'utilisation — Firebase Analytics)

L'Application utilise Firebase Analytics de Google pour améliorer ses fonctionnalités et comprendre son utilisation. Les événements suivants sont enregistrés :

- `game_start` (début de partie) / `game_finish` (fin de partie et score) / `mode_select` (sélection du mode)
- `ranking_view` (consultation du classement) / `ad_view` (affichage d'une publicité) / `share_score` (partage du score)

En plus de ces événements, Firebase Analytics collecte automatiquement des informations standard telles que le modèle de l'appareil, la version du système d'exploitation, la région approximative, la version de l'Application, la langue et un identifiant d'instance d'application émis par Google (identifiant pseudonyme). Ces informations sont utilisées à des fins d'analyse statistique et non pour vous identifier personnellement. Le traitement par Google est régi par les Règles de confidentialité de Google (<https://policies.google.com/privacy>) et par « Comment Google utilise les informations des sites ou applications qui utilisent ses services » (<https://policies.google.com/technologies/partner-sites>).

#### Article 6 (Rapports de plantage — Firebase Crashlytics)

L'Application utilise Firebase Crashlytics pour détecter et corriger les défauts. Lorsque l'Application plante, des informations de diagnostic telles que la trace de la pile, le modèle de l'appareil, la version du système d'exploitation et l'état de l'Application sont envoyées à Google. Ces informations ne comprennent pas de données personnelles telles que votre nom ou votre adresse e-mail.

#### Article 7 (Configuration à distance — Firebase Remote Config)

L'Application récupère des valeurs de configuration depuis Firebase Remote Config afin d'ajuster les événements, l'affichage du classement et les paramètres publicitaires. Google peut avoir connaissance de votre adresse IP lors de cette récupération, mais l'Application ne transmet aucune information permettant de vous identifier.

#### Article 8 (Publicité — Google AdMob / UMP)

L'Application étant fournie gratuitement, elle affiche des publicités via Google AdMob (une bannière sur l'écran des résultats et une publicité avec récompense facultative).

- AdMob peut consulter un identifiant publicitaire (Android : identifiant publicitaire ; iOS : IDFA) pour diffuser des publicités.
- Dans l'Espace économique européen (EEE), au Royaume-Uni et dans des régions similaires, l'Application présente un **écran de consentement** via Google UMP (User Messaging Platform) et respecte vos choix (par exemple, autoriser ou non les publicités personnalisées).
- Si vous ne donnez pas votre consentement, ou dans les régions concernées, **seules des publicités non personnalisées** sont diffusées.
- Les pratiques de confidentialité d'AdMob sont régies par la politique de Google (<https://policies.google.com/technologies/ads>).
- L'achat de « Supprimer les publicités » (voir ci-dessous) met fin à l'affichage des publicités.

#### Article 9 (Achats intégrés — Unity IAP)

L'Application propose un achat intégré unique « Supprimer les publicités ».

- Le paiement est traité par l'Apple App Store (iOS) ou Google Play (Android) ; le Développeur ne reçoit pas les données de paiement telles que les numéros de carte bancaire.
- Pour vérifier et restaurer les achats, l'Application consulte les reçus d'achat et les informations de transaction gérés par chaque boutique. Leur traitement est régi par les politiques d'Apple / de Google.
- L'état de l'achat (publicités supprimées ou non) est stocké sur votre appareil.

#### Article 10 (Partage sur les réseaux sociaux)

Grâce à la fonction « Partager » de l'écran des résultats, vous pouvez, à votre discrétion, partager un texte contenant le nom du mode, le score, le rang mondial et un hashtag vers le réseau social ou l'application de votre choix (X / LINE / Facebook / Instagram, etc.). Le partage est déclenché par votre action, et le traitement par le service de destination est régi par la politique de ce service.

#### Article 11 (Communication à des tiers)

L'Application ne divulgue ni ne fournit vos informations à des tiers, sauf lorsqu'elle confie leur traitement aux prestataires de services concernés (Google / Apple / Unity) dans la mesure nécessaire à la fourniture des fonctions décrites aux articles 5 à 10, ou lorsque la loi l'exige. Veuillez noter que les informations affichées dans le classement public (article 3) sont, par nature, visibles par tous les utilisateurs.

#### Article 12 (Utilisation par les enfants)

L'Application **ne s'adresse pas aux utilisateurs de moins de 13 ans**. Les publicités de l'Application sont diffusées par AdMob. Il incombe aux parents et tuteurs de gérer l'installation, l'utilisation et les achats effectués par les utilisateurs de moins de 13 ans. Si le Développeur apprend que des informations concernant un utilisateur de moins de 13 ans ont été transmises, il les supprimera sans délai.

#### Article 13 (Vos droits)

Vous disposez des droits suivants :

- **Suppression des données** : la désinstallation de l'Application supprime les données présentes sur l'appareil. Pour supprimer votre score, votre profil et vos succès stockés dans le cloud, contactez-nous (article 16) ; si vous nous communiquez votre UID anonyme, nous supprimerons ces données.
- **Modification des informations affichées** : vous pouvez modifier à tout moment votre nom de joueur, votre pays et votre langue dans l'écran Réglages.
- **Refus de la publicité** : depuis les réglages de votre appareil (iOS : Réglages > Confidentialité et sécurité > Suivi ; Android : Paramètres > Google > Annonces), vous pouvez réinitialiser l'identifiant publicitaire ou limiter le suivi. Dans l'EEE / au Royaume-Uni, vous pouvez reconfigurer votre consentement depuis la gestion du consentement intégrée à l'Application.
- **RGPD / CCPA** : les utilisateurs de l'EEE, du Royaume-Uni, de Californie et de juridictions similaires peuvent exercer des droits tels que l'accès, l'effacement et l'opposition conformément à la loi applicable. Veuillez nous contacter selon l'article 16.

#### Article 14 (Conservation et sécurité des données)

Les données dans le cloud sont stockées dans Google Cloud (Firebase / Firestore) et leur accès est contrôlé par les Firestore Security Rules. Les scores des classements quotidien et hebdomadaire sont automatiquement supprimés après un certain délai (Daily : environ 2 jours après la fin de la période ; Weekly : environ 2 jours après la fin de la période ; All Time : conservés).

#### Article 15 (Droit applicable)

La présente Politique est interprétée et appliquée conformément au droit japonais.

#### Article 16 (Contact / Modifications de la présente Politique)

Pour toute question concernant la présente Politique ou pour demander la suppression de données, veuillez contacter :

- E-mail : `support@haroworks.com`

Le Développeur peut réviser la présente Politique lorsque des modifications de la législation applicable ou des fonctionnalités de l'Application l'exigent. Les versions révisées prennent effet dès leur publication sur cette page HTTPS et sur les fiches des boutiques. Les modifications importantes seront en outre communiquées par des notifications dans l'Application ou par les notes de version.

---

**Historique des révisions**

- v1.0 (2026-06-12) : version initiale, en vigueur à compter de la sortie du MVP v1.0.0.

---

<a id="de"></a>

## §H. Deutsch (de)

> Diese Übersetzung dient nur als Referenz. Bei Abweichungen zwischen dieser Übersetzung und der japanischen (§A) oder englischen (§B) Fassung ist die japanische Fassung maßgeblich.

### Datenschutzerklärung von Tap Champion

Die App wird sowohl für iOS als auch für Android angeboten. Da das Backend auf beiden Plattformen identisch ist, gilt diese Erklärung für beide Plattformen; plattformspezifische Punkte sind im Text vermerkt.

Diese Datenschutzerklärung beschreibt, wie Tap Champion (die „App“) mit personenbezogenen Daten und Nutzerdaten umgeht. Der Entwickler der App, HaroWorks (der „Entwickler“), verarbeitet personenbezogene Daten und Nutzerdaten wie folgt.

#### Artikel 1 (Geltungsbereich)

Diese Erklärung gilt für alle Nutzer der mobilen Anwendung „Tap Champion“, die der Entwickler über den Apple App Store und Google Play vertreibt. Mit Beginn der Nutzung der App gilt diese Erklärung als von Ihnen akzeptiert.

#### Artikel 2 (Konten und anonyme Authentifizierung)

Die App erfordert keine Registrierung Ihres Namens, Ihrer E-Mail-Adresse, Ihrer Telefonnummer oder ähnlicher Angaben. Beim ersten Start vergibt sie über die **anonyme Anmeldung** von Firebase Authentication automatisch eine zufällige anonyme Kennung (anonyme UID), um Sie zu identifizieren.

- Mit der anonymen UID sind weder Name, E-Mail-Adresse, Telefonnummer noch sonstige Kontaktdaten verknüpft.
- Die App bietet weder eine Anmeldung über soziale Netzwerke noch eine Mitgliedsregistrierung.
- Die anonyme UID wird verwendet, um Punktzahlen an die Rangliste zu übermitteln und Erfolge zu speichern.

#### Artikel 3 (Erhobene und übermittelte Informationen)

Zur Bereitstellung der Online-Rangliste übermittelt die App die folgenden Informationen an das Cloud-Backend des Entwicklers (Google Cloud Firestore) und speichert sie dort.

| Element | Inhalt | Sichtbarkeit |
| --- | --- | --- |
| Spielername (displayName) | Ein von Ihnen festgelegter Anzeigename mit 1–12 Zeichen; standardmäßig ein automatisch erzeugtes „Player + Zahl“ | Wird in der öffentlichen Rangliste angezeigt |
| Land (countryCode) | Ein von Ihnen gewähltes Land für die Flagge (ISO 3166-1 alpha-2); standardmäßig aus der Gerätesprache abgeleitet | Wird in der öffentlichen Rangliste angezeigt |
| Punktzahl (score) | Ihre Bestpunktzahl pro Modus | Wird in der öffentlichen Rangliste angezeigt |
| Modus / Zeitraum | A / AB / ABC / ABCD sowie Daily / Weekly / All Time | Wird in der öffentlichen Rangliste angezeigt |
| Aktualisierungszeit (updatedAt) | Serverzeit der Aktualisierung Ihrer Punktzahl | Wird in der öffentlichen Rangliste angezeigt |
| Freischaltstatus der Erfolge | Zeitpunkt der Freischaltung jedes Erfolgs | Privat (nur Sie) |

**Zur öffentlichen Rangliste**: Von den oben genannten Angaben werden Ihr Spielername, Ihr Land, Ihre Punktzahl und die Aktualisierungszeit als Teil der Weltrangliste öffentlich für alle anderen Nutzer angezeigt. Verwenden Sie nicht Ihren echten Namen oder Informationen, die Sie persönlich identifizieren, als Spielernamen (Sie können ihn jederzeit im Einstellungsbildschirm ändern).

Die App kann offline gespielt werden. Eine Kommunikation findet nur beim Übermitteln von Punktzahlen, beim Ansehen der Rangliste sowie für die nachfolgend beschriebenen Analyse-, Werbe- und Kauffunktionen statt.

#### Artikel 4 (Nur auf Ihrem Gerät gespeicherte Daten)

Die App speichert außerdem die folgenden Daten im lokalen Speicher Ihres Geräts; sie dienen dem Offline-Spiel und einer schnelleren Anzeige. Sie werden – außer beim Übermitteln von Punktzahlen – nicht von Ihrem Gerät übertragen.

- Ihre Bestpunktzahl pro Modus
- Spielerprofil (Spielername, Land, Sprache der Benutzeroberfläche, Kaufstatus „Werbung entfernen“)
- Freischaltstatus der Erfolge
- Ausstehende Punktzahl-Übermittlungen (offline erstellt und nach dem Senden bei erneuter Verbindung gelöscht)

Durch die Deinstallation der App werden die Daten auf dem Gerät gelöscht. Da die anonyme UID pro Gerät vergeben wird, können in der Cloud gespeicherte Punktzahlen und Erfolge nach der Deinstallation nicht wiederhergestellt werden.

#### Artikel 5 (Nutzungsanalyse — Firebase Analytics)

Die App verwendet Firebase Analytics von Google, um Funktionen zu verbessern und die Nutzung zu verstehen. Die folgenden Ereignisse werden erfasst:

- `game_start` (Spielbeginn) / `game_finish` (Spielende und Punktzahl) / `mode_select` (Modusauswahl)
- `ranking_view` (Aufruf der Rangliste) / `ad_view` (Anzeige von Werbung) / `share_score` (Teilen der Punktzahl)

Zusätzlich zu diesen Ereignissen erfasst Firebase Analytics automatisch Standardinformationen wie Gerätemodell, Betriebssystemversion, ungefähre Region, App-Version, Sprache und eine von Google vergebene App-Instanz-Kennung (pseudonyme ID). Diese Informationen werden für statistische Analysen verwendet und nicht, um Sie persönlich zu identifizieren. Der Umgang durch Google richtet sich nach der Datenschutzerklärung von Google (<https://policies.google.com/privacy>) sowie nach „Wie Google Informationen von Websites oder Apps verwendet, die unsere Dienste nutzen“ (<https://policies.google.com/technologies/partner-sites>).

#### Artikel 6 (Absturzberichte — Firebase Crashlytics)

Die App verwendet Firebase Crashlytics, um Fehler zu erkennen und zu beheben. Wenn die App abstürzt, werden Diagnoseinformationen wie Stacktrace, Gerätemodell, Betriebssystemversion und App-Zustand an Google gesendet. Diese Informationen enthalten keine personenbezogenen Daten wie Ihren Namen oder Ihre E-Mail-Adresse.

#### Artikel 7 (Remote-Konfiguration — Firebase Remote Config)

Die App ruft Konfigurationswerte aus Firebase Remote Config ab, um Events, die Anzeige der Rangliste und Werbeeinstellungen anzupassen. Google kann beim Abruf Ihre IP-Adresse erkennen, die App übermittelt jedoch keine Sie identifizierenden Informationen.

#### Artikel 8 (Werbung — Google AdMob / UMP)

Da die App kostenlos angeboten wird, zeigt sie Werbung über Google AdMob an (ein Banner auf dem Ergebnisbildschirm und eine optionale Prämienanzeige).

- AdMob kann zur Auslieferung von Werbung eine Werbe-ID (Android: Werbe-ID, iOS: IDFA) heranziehen.
- Im Europäischen Wirtschaftsraum (EWR), im Vereinigten Königreich und in vergleichbaren Regionen zeigt die App über Google UMP (User Messaging Platform) einen **Einwilligungsbildschirm** an und richtet sich nach Ihrer Auswahl (z. B. ob personalisierte Werbung erlaubt ist).
- Wenn Sie nicht einwilligen, oder in den betreffenden Regionen, wird **ausschließlich nicht personalisierte Werbung** ausgeliefert.
- Die Datenschutzpraktiken von AdMob richten sich nach der Richtlinie von Google (<https://policies.google.com/technologies/ads>).
- Mit dem Kauf von „Werbung entfernen“ (siehe unten) wird keine Werbung mehr angezeigt.

#### Artikel 9 (In-App-Käufe — Unity IAP)

Die App bietet einen einmaligen In-App-Kauf „Werbung entfernen“ an.

- Die Zahlung wird über den Apple App Store (iOS) oder Google Play (Android) abgewickelt; der Entwickler erhält keine Zahlungsdaten wie Kreditkartennummern.
- Zur Überprüfung und Wiederherstellung von Käufen greift die App auf Kaufbelege und Transaktionsinformationen zurück, die vom jeweiligen Store verwaltet werden. Deren Verarbeitung richtet sich nach den Richtlinien von Apple / Google.
- Der Kaufstatus (ob die Werbung entfernt ist) wird auf Ihrem Gerät gespeichert.

#### Artikel 10 (Teilen in sozialen Netzwerken)

Über „Teilen“ auf dem Ergebnisbildschirm können Sie nach eigenem Ermessen einen Text mit Modusname, Punktzahl, Weltrang und einem Hashtag in einer von Ihnen gewählten Social-App teilen (X / LINE / Facebook / Instagram usw.). Das Teilen erfolgt auf Ihre Veranlassung, und die Verarbeitung beim Zieldienst richtet sich nach dessen Richtlinie.

#### Artikel 11 (Weitergabe an Dritte)

Die App gibt Ihre Informationen nicht an Dritte weiter oder stellt sie ihnen zur Verfügung, es sei denn, sie beauftragt die jeweiligen Dienstleister (Google / Apple / Unity) mit der Verarbeitung, soweit dies zur Bereitstellung der in den Artikeln 5–10 beschriebenen Funktionen erforderlich ist, oder dies ist gesetzlich vorgeschrieben. Bitte beachten Sie, dass die in der öffentlichen Rangliste angezeigten Informationen (Artikel 3) naturgemäß für alle Nutzer sichtbar sind.

#### Artikel 12 (Nutzung durch Kinder)

Die App **richtet sich nicht an Nutzer unter 13 Jahren**. Die Werbung in der App wird von AdMob ausgeliefert. Eltern und Erziehungsberechtigte sind dafür verantwortlich, die Installation, Nutzung und Käufe durch Nutzer unter 13 Jahren zu überwachen. Erlangt der Entwickler Kenntnis davon, dass Informationen eines Nutzers unter 13 Jahren übermittelt wurden, löscht er diese unverzüglich.

#### Artikel 13 (Ihre Rechte)

Sie haben die folgenden Rechte:

- **Datenlöschung**: Durch die Deinstallation der App werden die Daten auf dem Gerät gelöscht. Um Ihre in der Cloud gespeicherte Punktzahl, Ihr Profil und Ihre Erfolge löschen zu lassen, kontaktieren Sie uns (Artikel 16); wenn Sie uns Ihre anonyme UID mitteilen, löschen wir diese Daten.
- **Änderung der angezeigten Informationen**: Sie können Ihren Spielernamen, Ihr Land und Ihre Sprache jederzeit im Einstellungsbildschirm ändern.
- **Widerspruch gegen Werbung**: In den Einstellungen Ihres Geräts (iOS: Einstellungen > Datenschutz & Sicherheit > Tracking; Android: Einstellungen > Google > Anzeigen) können Sie die Werbe-ID zurücksetzen oder das Tracking einschränken. Im EWR / Vereinigten Königreich können Sie Ihre Einwilligung über die Einwilligungsverwaltung in der App neu festlegen.
- **DSGVO / CCPA**: Nutzer im EWR, im Vereinigten Königreich, in Kalifornien und in vergleichbaren Rechtsordnungen können nach geltendem Recht Rechte wie Auskunft, Löschung und Widerspruch (Opt-out) ausüben. Bitte kontaktieren Sie uns gemäß Artikel 16.

#### Artikel 14 (Datenspeicherung und Sicherheit)

Cloud-Daten werden in Google Cloud (Firebase / Firestore) gespeichert, und der Zugriff wird durch Firestore Security Rules kontrolliert. Punktzahlen der täglichen und wöchentlichen Rangliste werden nach einem bestimmten Zeitraum automatisch gelöscht (Daily: etwa 2 Tage nach Ende des Zeitraums; Weekly: etwa 2 Tage nach Ende des Zeitraums; All Time: werden aufbewahrt).

#### Artikel 15 (Anwendbares Recht)

Diese Erklärung wird nach japanischem Recht ausgelegt und angewendet.

#### Artikel 16 (Kontakt / Änderungen dieser Erklärung)

Bei Fragen zu dieser Erklärung oder zur Beantragung der Datenlöschung wenden Sie sich bitte an:

- E-Mail: `support@haroworks.com`

Der Entwickler kann diese Erklärung überarbeiten, wenn Änderungen des geltenden Rechts oder der Funktionen der App dies erfordern. Überarbeitete Fassungen treten in Kraft, sobald sie auf dieser HTTPS-Seite und in den Store-Einträgen veröffentlicht sind. Wesentliche Änderungen werden zusätzlich über Benachrichtigungen in der App oder Versionshinweise mitgeteilt.

---

**Änderungshistorie**

- v1.0 (2026-06-12): Erstfassung, in Kraft mit der Veröffentlichung des MVP v1.0.0.

---

<a id="pt"></a>

## §I. Português (pt)

> Esta tradução é fornecida apenas para referência. Em caso de divergência entre esta tradução e a versão em japonês (§A) ou em inglês (§B), prevalecerá a versão em japonês.

### Política de Privacidade do Tap Champion

O App é distribuído tanto no iOS quanto no Android. Como o backend é idêntico nas duas plataformas, esta Política abrange ambas; os itens específicos de cada plataforma são indicados no texto.

Esta Política de Privacidade descreve como o Tap Champion (o "App") trata informações pessoais e dados dos usuários. O desenvolvedor do App, HaroWorks (o "Desenvolvedor"), trata informações pessoais e dados dos usuários da seguinte forma.

#### Artigo 1 (Âmbito)

Esta Política se aplica a todos os usuários do aplicativo móvel "Tap Champion" distribuído pelo Desenvolvedor por meio da Apple App Store e do Google Play. Ao começar a usar o App, considera-se que você concordou com esta Política.

#### Artigo 2 (Contas e autenticação anônima)

O App não exige o cadastro do seu nome, endereço de e-mail, número de telefone ou informações semelhantes. Na primeira execução, ele emite automaticamente um identificador anônimo aleatório (UID anônimo) por meio do **login anônimo** do Firebase Authentication para identificar você.

- Nenhum nome, endereço de e-mail, número de telefone ou outra informação de contato é associado ao UID anônimo.
- O App não possui login por redes sociais nem cadastro de membros.
- O UID anônimo é usado para enviar pontuações ao ranking e para armazenar conquistas.

#### Artigo 3 (Informações que coletamos e transmitimos)

Para oferecer o ranking on-line, o App transmite e armazena as seguintes informações no backend em nuvem do Desenvolvedor (Google Cloud Firestore).

| Item | Conteúdo | Visibilidade |
| --- | --- | --- |
| Nome do jogador (displayName) | Nome de exibição de 1 a 12 caracteres definido por você; por padrão, um "Player + número" gerado automaticamente | Exibido no ranking público |
| País (countryCode) | País que você seleciona para a bandeira (ISO 3166-1 alfa-2); por padrão, estimado a partir do idioma do dispositivo | Exibido no ranking público |
| Pontuação (score) | Sua melhor pontuação em cada modo | Exibido no ranking público |
| Modo / Período | A / AB / ABC / ABCD, e Daily / Weekly / All Time | Exibido no ranking público |
| Horário de atualização (updatedAt) | Horário do servidor em que sua pontuação foi atualizada | Exibido no ranking público |
| Estado de desbloqueio de conquistas | Data e hora de desbloqueio de cada conquista | Privado (somente você) |

**Sobre o ranking público**: dentre os itens acima, seu nome de jogador, país, pontuação e horário de atualização são exibidos publicamente a todos os outros usuários como parte do ranking mundial. Não use seu nome real nem informações que permitam identificá-lo pessoalmente como nome de jogador (você pode alterá-lo a qualquer momento na tela de Ajustes).

O App pode ser jogado off-line. A comunicação ocorre somente ao enviar pontuações, ao visualizar o ranking e nas funções de análise, publicidade e compras descritas abaixo.

#### Artigo 4 (Dados armazenados somente no seu dispositivo)

O App também armazena os seguintes dados no armazenamento local do seu dispositivo, usados para jogar off-line e para agilizar a exibição. Eles não são transmitidos para fora do seu dispositivo, exceto ao enviar pontuações.

- Sua melhor pontuação em cada modo
- Perfil do jogador (nome do jogador, país, idioma da interface, estado da compra de remoção de anúncios)
- Estado de desbloqueio de conquistas
- Envios de pontuação pendentes (criados quando off-line e excluídos após o envio ao reconectar)

Desinstalar o App exclui os dados do dispositivo. Como o UID anônimo é emitido por dispositivo, as pontuações e conquistas armazenadas na nuvem não podem ser restauradas após a desinstalação.

#### Artigo 5 (Análise de uso — Firebase Analytics)

O App usa o Firebase Analytics do Google para melhorar recursos e entender o uso. Os seguintes eventos são registrados:

- `game_start` (início da partida) / `game_finish` (fim da partida e pontuação) / `mode_select` (seleção de modo)
- `ranking_view` (visualização do ranking) / `ad_view` (exibição de anúncio) / `share_score` (compartilhamento da pontuação)

Além desses eventos, o Firebase Analytics coleta automaticamente informações padrão, como modelo do dispositivo, versão do sistema operacional, região aproximada, versão do App, idioma e um identificador de instância do app emitido pelo Google (ID pseudônimo). Essas informações são usadas para análises estatísticas e não para identificar você pessoalmente. O tratamento pelo Google segue a Política de Privacidade do Google (<https://policies.google.com/privacy>) e "Como o Google usa informações de sites ou apps que utilizam nossos serviços" (<https://policies.google.com/technologies/partner-sites>).

#### Artigo 6 (Relatórios de falhas — Firebase Crashlytics)

O App usa o Firebase Crashlytics para detectar e corrigir defeitos. Quando o App falha, informações de diagnóstico, como o rastreamento de pilha, o modelo do dispositivo, a versão do sistema operacional e o estado do App, são enviadas ao Google. Essas informações não incluem dados pessoais, como seu nome ou endereço de e-mail.

#### Artigo 7 (Configuração remota — Firebase Remote Config)

O App obtém valores de configuração do Firebase Remote Config para ajustar eventos, a exibição do ranking e as configurações de anúncios. O Google pode observar seu endereço IP durante a obtenção, mas o App não transmite nenhuma informação que identifique você.

#### Artigo 8 (Publicidade — Google AdMob / UMP)

Como o App é oferecido gratuitamente, ele exibe anúncios por meio do Google AdMob (um anúncio de banner na tela de resultados e um anúncio premiado opcional).

- O AdMob pode consultar um identificador de publicidade (Android: ID de publicidade; iOS: IDFA) para veicular anúncios.
- No Espaço Econômico Europeu (EEE), no Reino Unido e em regiões semelhantes, o App apresenta uma **tela de consentimento** por meio do Google UMP (User Messaging Platform) e segue suas escolhas (por exemplo, se permite anúncios personalizados).
- Se você não consentir, ou nas regiões aplicáveis, **somente anúncios não personalizados** serão veiculados.
- As práticas de privacidade do AdMob seguem a política do Google (<https://policies.google.com/technologies/ads>).
- Ao comprar "Remover anúncios" (veja abaixo), os anúncios deixam de ser exibidos.

#### Artigo 9 (Compras no App — Unity IAP)

O App oferece uma compra única no App de "Remover anúncios".

- O pagamento é processado pela Apple App Store (iOS) ou pelo Google Play (Android); o Desenvolvedor não recebe dados de pagamento, como números de cartão de crédito.
- Para verificar e restaurar compras, o App consulta os recibos de compra e as informações de transação gerenciados por cada loja. O tratamento desses dados segue as políticas da Apple / do Google.
- O estado da compra (se os anúncios foram removidos) é armazenado no seu dispositivo.

#### Artigo 10 (Compartilhamento em redes sociais)

Usando "Compartilhar" na tela de resultados, você pode, a seu critério, compartilhar um texto contendo o nome do modo, a pontuação, a posição mundial e uma hashtag no app social de sua escolha (X / LINE / Facebook / Instagram etc.). O compartilhamento é iniciado por uma ação sua, e o tratamento no destino segue a política desse serviço.

#### Artigo 11 (Compartilhamento com terceiros)

O App não divulga nem fornece suas informações a terceiros, exceto quando confia o tratamento aos prestadores de serviços pertinentes (Google / Apple / Unity) na medida necessária para fornecer as funções descritas nos Artigos 5 a 10, ou quando exigido por lei. Observe que as informações exibidas no ranking público (Artigo 3) são, por sua natureza, visíveis a todos os usuários.

#### Artigo 12 (Uso por crianças)

O App **não é direcionado a usuários menores de 13 anos**. Os anúncios no App são veiculados pelo AdMob. Pais e responsáveis são responsáveis por gerenciar a instalação, o uso e as compras feitas por usuários menores de 13 anos. Se o Desenvolvedor tomar conhecimento de que informações de um usuário menor de 13 anos foram transmitidas, ele as excluirá prontamente.

#### Artigo 13 (Seus direitos)

Você tem os seguintes direitos:

- **Exclusão de dados**: desinstalar o App exclui os dados do dispositivo. Para excluir sua pontuação, seu perfil e suas conquistas armazenados na nuvem, entre em contato conosco (Artigo 16); se você nos informar seu UID anônimo, excluiremos esses dados.
- **Alteração das informações exibidas**: você pode alterar seu nome de jogador, país e idioma a qualquer momento na tela de Ajustes.
- **Recusa de publicidade**: nas configurações do seu dispositivo (iOS: Ajustes > Privacidade e Segurança > Rastreamento; Android: Configurações > Google > Anúncios), você pode redefinir o identificador de publicidade ou limitar o rastreamento. No EEE / Reino Unido, você pode reconfigurar o consentimento pelo gerenciamento de consentimento no App.
- **GDPR / CCPA**: usuários do EEE, do Reino Unido, da Califórnia e de jurisdições semelhantes podem exercer direitos como acesso, exclusão e recusa (opt-out) nos termos da legislação aplicável. Entre em contato conosco conforme o Artigo 16.

#### Artigo 14 (Retenção e segurança dos dados)

Os dados na nuvem são armazenados no Google Cloud (Firebase / Firestore) e o acesso é controlado pelas Firestore Security Rules. As pontuações dos rankings diário e semanal são excluídas automaticamente após um período (Daily: cerca de 2 dias após o fim do período; Weekly: cerca de 2 dias após o fim do período; All Time: mantidas).

#### Artigo 15 (Lei aplicável)

Esta Política será interpretada e aplicada de acordo com as leis do Japão.

#### Artigo 16 (Contato / Alterações nesta Política)

Para dúvidas sobre esta Política ou para solicitar a exclusão de dados, entre em contato:

- E-mail: `support@haroworks.com`

O Desenvolvedor poderá revisar esta Política quando exigido por alterações na legislação aplicável ou nas funções do App. As versões revisadas entram em vigor assim que publicadas nesta página HTTPS e nas páginas do App nas lojas. Alterações relevantes também serão comunicadas por meio de notificações no App ou de notas de versão.

---

**Histórico de revisões**

- v1.0 (2026-06-12): Versão inicial, em vigor com o lançamento do MVP v1.0.0.

---
