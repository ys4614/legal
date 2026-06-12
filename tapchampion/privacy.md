---
title: Tap Champion Privacy Policy
permalink: /tapchampion/privacy/
---

# 連打名人 / Tap Champion — Privacy Policy

**発効日 / Effective:** 2026-06-12 ・ **バージョン / Version:** 1.0 ・ **連絡先 / Contact:** [support@haroworks.com](mailto:support@haroworks.com) ・ **applicationId / Bundle ID:** `com.haroworks.tapchampion`

[← Index](../../)

本アプリは iOS / Android の両プラットフォームで配信されます。バックエンド構成は両プラットフォームで共通のため、本ポリシーは両者を対象とします。プラットフォーム固有の事項は本文中に注記します。 / The App is distributed on both iOS and Android. As the backend is identical on both, this Policy covers both platforms; platform-specific items are noted inline.

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

本アプリはプレイ自体をオフラインで実行できます。通信が発生するのは、スコアのランキング送信、ランキングの閲覧、後述の分析・広告・課金処理の各場面に限られます（第 15 非機能要件: オフラインプレイ可能）。

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
