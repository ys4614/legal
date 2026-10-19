---
title: Tap Champion Privacy Policy
permalink: /tapchampion/privacy/
---

# 連打名人 / Tap Champion — Privacy Policy

**発効日 / Effective:** 2026-06-12 ・ **最終更新日 / Last updated:** 2026-10-20 ・ **バージョン / Version:** 1.1 ・ **連絡先 / Contact:** [support@haroworks.com](mailto:support@haroworks.com) ・ **applicationId / Bundle ID:** `com.haroworks.tapchampion`

[← Index](../../)

**Languages / 言語:** [日本語](#ja) ・ [English](#en) ・ [简体中文](#zh-hans) ・ [繁體中文](#zh-hant) ・ [한국어](#ko) ・ [Español](#es) ・ [Français](#fr) ・ [Deutsch](#de) ・ [Português](#pt)

本アプリは iOS / Android の両プラットフォームで配信されます。バックエンド構成は両プラットフォームで共通のため、本ポリシーは両者を対象とします。プラットフォーム固有の事項は本文中に注記します。 / The App is distributed on both iOS and Android. As the backend is identical on both, this Policy covers both platforms; platform-specific items are noted inline.

<a id="ja"></a>

## §A. 日本語 (ja, default)

### 連打名人 プライバシーポリシー

連打名人（Tap Champion、以下「本アプリ」）の提供者 HaroWorks（以下「開発者」）は、本アプリで扱う情報を、何のために・どこへ送り・どれだけの期間保存するかを、以下のとおり定めます。

#### 第 1 条 (適用範囲)

本ポリシーは、開発者が Apple App Store および Google Play で配信するモバイルアプリ「連打名人 / Tap Champion」（iOS / Android。バックエンドは共通）のすべての利用者に適用されます。プラットフォームで異なる点は本文中に注記します。

#### 第 2 条 (アカウントと匿名認証)

本アプリは、氏名・メールアドレス・電話番号等の登録を求めず、会員登録・ソーシャルログインの機能もありません。

- 初回起動時に、Firebase Authentication の**匿名ログイン**で、ランダムな匿名 ID（匿名 UID）が自動で発行されます。匿名 UID に氏名や連絡先は結び付きません。
- 匿名 UID は、ランキングの記録を利用者ごとに区別すること、プレイ記録の照合、不正の防止（第 4 条）に使います。アプリの画面には表示しません。
- 匿名ログインの際、Firebase Authentication は不正利用の防止のため、通信元の IP アドレスと端末のユーザーエージェント（OS・SDK の種類）を受け取ります。

#### 第 3 条 (ランキングに送る情報 — Cloud Firestore)

ゲームが終わり、スコアが 1 点以上で、プレイの開始と終了の記録（第 4 条）が通った場合、本アプリは次の情報を開発者のクラウド（Google Cloud Firestore）へ送り、デイリー・ウィークリー・オールタイムの各ランキングに保存します。自己ベストを更新したときだけ書き換えます。

| 項目 | 内容 | 公開範囲 |
| --- | --- | --- |
| プレイヤー名 | 利用者が設定する 1〜12 文字の表示名。初期値は自動で付く名前 | アプリのランキングに表示 |
| 国 | 国旗の表示用に利用者が選ぶ国（ISO 3166-1 の 2 文字）。初期値は端末の言語から推定 | アプリのランキングに表示 |
| スコア・モード・期間 | ベストスコアと、モード（A / AB / ABC / ABCD）、期間（デイリー / ウィークリー / オールタイム） | アプリのランキングに表示 |
| 更新日時 | スコアを書き込んだサーバーの時刻 | アプリのランキングに表示 |
| 匿名 UID | 記録の持ち主の区別（記録の ID として使用） | アプリには表示しない※ |
| プレイ記録の ID | 第 4 条のプレイ記録との照合用のランダムな ID | アプリには表示しない※ |
| タップの統計 | 第 4 条 (2) の数値 | アプリには表示しない※ |

※ ランキングの記録はアプリから誰でも読み取れる形で保存しているため、「アプリには表示しない」項目も、技術的にはアプリ外から読み取れる場合があります。いずれも氏名・連絡先などを含まない仮名の情報です。

**公開ランキングについて**: プレイヤー名・国・スコア・更新日時は、世界ランキングとして他のすべての利用者に表示されます。プレイヤー名に本名など個人を特定できる情報を使わないでください。プレイヤー名と国は設定画面でいつでも変更でき、次にベストを更新したときの記録から反映されます。

ランキングの閲覧時は、ランキングの上位の記録と自分の順位を読み込みます。プレイ自体は通信がなくても遊べます。

#### 第 4 条 (不正防止のために送る情報 — バージョン 1.4 から)

自動連打ツール・速度改変・メモリ改ざんなどによる不正な記録を防ぐため、次の情報を使います。判定の結果、記録がランキングの対象外になったり、悪質な場合は匿名 UID ごと記録の送信を止める（以下「利用停止」）ことがあります。

1. **プレイ記録（サーバー時刻）**: プレイの開始時と終了時に、モード・開始時刻・終了時刻・スコアを Firestore の利用者ごとの領域（匿名 UID ごと）に書き込みます。時刻はすべてサーバーの時刻で、プレイ時間が不自然に長い・短い記録や、同じ記録の使い回しを見分けるために使います。この領域はアプリからは読み取れません。開始時に通信できないプレイは、ランキングの対象外になります。
2. **タップの統計**: プレイ中、端末の中で各タップの時刻・画面上の位置・指の番号・押した強さ・接地の大きさ（端末が対応している場合）を一時的に使い、次の数値を計算します: タップ数、使った指の数、タップ間隔のばらつき、ボタンごとのタップ位置のばらつき（mm）、1 秒あたりの最大タップ数（全体・指 1 本あたり）、押した強さと接地の大きさの組み合わせの種類の数。**1 回ごとのタップの時刻や位置そのものは送らず**、数値だけをランキングの記録（第 3 条）と Firebase Analytics の `tap_stats` イベント（モード・スコアとともに。判定の基準値を決めるため）に送ります。元のタップの記録はプレイの終了後に破棄します。
3. **App Check（アプリの正当性の確認）**: Firebase App Check により、通信が正規のアプリと端末から来ていることを確かめます。Android では Google Play Integrity API、iOS では Apple の App Attest を使い、Google / Apple が発行する確認用のトークンを Firebase に送ります。トークンは短時間で失効し、開発者は端末の識別子をこれから受け取りません。
4. **利用停止の記録**: 利用停止にした匿名 UID について、理由・日時・削除した記録の件数を Firestore に保存し、誤りがあった場合に戻せるよう、削除した記録の写しを開発者の手元に保管します。

#### 第 5 条 (端末内にのみ保存されるデータ)

次のデータは利用者の端末内に保存し、本ポリシーで送ると定めた場合を除き、端末の外へ送りません。

- 各モードの自己ベスト、通算のプレイ回数・最高連射などの記録、モードの解放状況、チュートリアルの既読
- プロフィールと設定（プレイヤー名・国・言語・機体色・音量・演出の設定・匿名 UID）
- 購入済みの商品（応援パック・広告削除）
- ランキングへの送信待ちのデータ（通信に失敗したとき。スコア・モード・期間・プレイ記録の ID・タップの統計。プレイの開始から 1 時間の期限内に再送し、送信後に削除）
- 共有用に撮ったリザルト画面の画像（端末の一時フォルダ）

アプリを削除すると、端末内のデータは消えます。匿名 UID も新しくなるため、削除前のランキングの記録とは結び付かなくなります。

#### 第 6 条 (利用状況の分析 — Firebase Analytics)

機能の改善と不正の基準値の調整のため、Google の Firebase Analytics を使います。本アプリが記録するイベントは次のとおりです。

- `game_start`（モード）/ `game_finish`（モード・スコア）/ `mode_select` / `mode_unlock` / `ranking_view`（モード・期間）/ `ad_view`
- `tutorial_step` / `tutorial_skip`（チュートリアルの段階）
- `tap_stats`（モード・スコアと第 4 条 (2) の数値）

あわせて Firebase Analytics は、アプリのインスタンス ID、端末の機種、OS・アプリのバージョン、言語、IP アドレスから推定したおおよその地域（国・地域・都市の単位）、起動・画面表示・利用時間、アプリの更新、アプリ内課金のイベント（商品 ID・価格）、広告 ID（Android の広告 ID。iOS では本アプリがトラッキングの許可を求めないため IDFA は取得されず、代わりに IDFV）を自動で収集します。開発者はこれらを統計として見るために使い、広告の配信やターゲティングには使いません。

#### 第 7 条 (クラッシュレポート — Firebase Crashlytics)

不具合を見つけて直すため、Firebase Crashlytics を使います。アプリが異常終了したときなどに、スタックトレース、その時のアプリの状態、端末の機種・OS などの情報、Crashlytics のインストール ID を Google に送ります。

#### 第 8 条 (リモート設定 — Firebase Remote Config)

運用中の設定値を受け取るため、Firebase Remote Config を使います。取得の際、SDK が Firebase のインストール ID、国・言語・タイムゾーン・OS のバージョンを送ります。

#### 第 9 条 (広告 — Google AdMob / UMP)

本アプリは無料で提供するため、Google AdMob の広告を表示します。ホーム画面の下部のバナー広告と、リザルトからホームへ戻るときの全画面広告（30 秒以上の間隔を空ける）です。プレイ中は広告の SDK を呼びません。

- Google Mobile Ads SDK は、広告の配信・効果の測定・不正の防止のため、IP アドレス（おおよその位置の推定に使われます）、端末の識別子（Android の広告 ID・アプリセット ID、iOS の IDFV など）、広告の表示・タップなどの操作、アプリの起動時間などの性能・診断の情報を Google に送ります。Google はこれを Google のポリシー（<https://policies.google.com/technologies/ads>）に従って扱います。
- EEA・英国・スイスなど同意が必要な地域では、Google UMP の同意画面を表示し、利用者の選択に従います。選択は設定画面の「広告のプライバシー設定」から変更できます。それ以外の地域では、端末の設定に応じて、パーソナライズされた広告が表示されることがあります。
- iOS では、本アプリはトラッキングの許可（App Tracking Transparency）を求めません。そのため IDFA は使われません。
- 応援パック（または以前の「広告削除」）を購入すると、広告は表示されなくなります。

#### 第 10 条 (アプリ内課金)

応援パック（3 種類の買い切り。どれも広告の削除付き）と、以前販売していた「広告削除」の復元に対応しています。

- 決済は Apple App Store（iOS）または Google Play（Android）が行い、開発者はクレジットカード番号などの決済情報を受け取りません。
- 購入の確認と復元のため、ストアの購入情報を参照します。購入済みの商品は端末内に保存します。
- 第 6 条のとおり、Firebase Analytics がアプリ内課金のイベント（商品 ID・価格）を記録することがあります。

#### 第 11 条 (共有)

リザルト画面の「共有」を押すと、モード・スコア・称号・ストアの URL の文と、リザルト画面の画像を、OS の共有画面に渡します。送り先は利用者が選び、送り先での扱いは各サービスのポリシーに従います。開発者には送られません。

#### 第 12 条 (第三者への提供)

開発者は利用者の情報を販売しません。次の場合を除き、第三者に提供しません。

- 第 9 条の Google AdMob: 広告 SDK が集めた情報を、Google が自らのポリシーに従って広告の配信・測定・不正の防止に使います。
- 第 3 条の公開ランキング: その性質上、他の利用者に表示されます。
- 業務の委託: Google（Firebase / Google Cloud）に、開発者の指示の範囲でデータの処理と保管を任せます。決済は Apple / Google が行います。
- 法令に基づく場合。

#### 第 13 条 (子どもの利用)

本アプリは 13 歳未満の利用者を対象としていません。保護者の方は、13 歳未満の方によるインストール・利用・購入を管理してください。13 歳未満の方の情報が送られたことが分かった場合、開発者は速やかに削除します。

#### 第 14 条 (保存期間)

| データ | 保存期間 |
| --- | --- |
| デイリー / ウィークリーのランキング | 期間の終了から約 2 日後に自動で削除（削除の処理にさらに 1 日ほどかかることがあります） |
| オールタイムのランキング | サービスの提供中、または削除のご依頼まで |
| プレイ記録（第 4 条 (1)） | 不正の調査のため、サービスの提供中、または削除のご依頼まで |
| 匿名ログインのアカウント | サービスの提供中、または削除のご依頼まで |
| 利用停止の記録と、削除した記録の写し | 利用停止を解除するまで、または不要になるまで |
| Firebase Analytics | Google アナリティクスのデータ保持の設定に従う（ユーザー単位のデータは最長 14 か月） |
| Firebase Crashlytics | Google の定める期間（クラッシュのデータは 90 日） |
| 端末内のデータ | アプリを削除するまで |

#### 第 15 条 (データの保管とセキュリティ)

クラウドのデータは Google Cloud（Firebase / Firestore）に保管し、Firestore Security Rules と App Check でアクセスを制限します。通信はすべて暗号化（TLS）されます。データは利用者の国の外にある Google のサーバーで処理・保管されることがあります。

#### 第 16 条 (利用者の権利とデータの削除)

- **削除のご依頼**: クラウドのデータ（ランキングの記録・プレイ記録・匿名ログインのアカウント）の削除は、メール（<support@haroworks.com>）でお申し込みください。件名に「データ削除のご依頼」と書き、プレイヤー名・国・お使いの OS（iOS / Android）・おおよそのスコアと日時をお知らせください。匿名 UID はアプリに表示されないため、これらから記録を特定します。確認できた記録を、原則 30 日以内に削除してお知らせします。
- Firebase Analytics・Crashlytics・AdMob のデータは、氏名などと結び付かない識別子で保存されるため、開発者が個人を特定して削除できない場合があります。これらは第 14 条の期間が過ぎると削除されます。
- **端末内のデータ**: アプリを削除すると消えます。
- **表示の変更**: プレイヤー名・国・言語は設定画面でいつでも変更できます。
- **広告の設定**: 端末の設定（Android: 設定 > Google > 広告、iOS: 設定 > プライバシーとセキュリティ）で広告 ID のリセットやパーソナライズ広告の停止ができます。同意が必要な地域では、設定画面の「広告のプライバシー設定」から同意を変更できます。
- **各国の法令に基づく権利**: EEA・英国・カリフォルニア州などの利用者は、適用される法令に基づき、アクセス・訂正・削除・処理への異議などの権利を行使できます。上記のメールでご連絡ください。開発者は個人情報を販売しません。

#### 第 17 条 (準拠法)

本ポリシーの解釈および適用は、日本国の法律に準拠します。

#### 第 18 条 (お問い合わせ・本ポリシーの変更)

本ポリシーに関するお問い合わせ・削除のご依頼は、次までご連絡ください。

- メールアドレス: <support@haroworks.com>

本ポリシーは、法令の改正やアプリの変更に合わせて改定することがあります。改定後のポリシーは、このページに掲示した時点から効力を生じます。重要な変更は、アプリのリリースノート等でもお知らせします。

---

**改定履歴**

- v1.1 (2026-10-20): バージョン 1.4 に合わせて全面改定。不正防止のための情報（プレイ記録・タップの統計・App Check・利用停止）を追加。Analytics のイベント、広告の種類と広告 SDK が集める情報、応援パック、共有の内容を実際の動きに合わせ、保存期間と削除の頼み方を明記。クラウドに保存していなかった「実績」の記載を削除。
- v1.0 (2026-06-12): 初版（v1.0.0 のリリースに合わせて発効）。

---

<a id="en"></a>

## §B. English (en-US)

### Tap Champion Privacy Policy

HaroWorks (the "Developer"), the provider of Tap Champion (the "App"), sets out below what information the App handles, why, where it is sent, and how long it is kept.

#### Article 1 (Scope)

This Policy applies to all users of the mobile app "Tap Champion" distributed by the Developer on the Apple App Store and Google Play (iOS / Android, with a shared backend). Differences between platforms are noted in the text.

#### Article 2 (Accounts and Anonymous Authentication)

The App does not ask you to register your name, email address, phone number, or similar information, and it has no membership registration or social login.

- On first launch, a random anonymous identifier (anonymous UID) is issued automatically via Firebase Authentication **anonymous sign-in**. No name or contact information is associated with it.
- The anonymous UID is used to tell users' leaderboard records apart, to match play records, and to prevent cheating (Article 4). It is not shown in the App.
- During anonymous sign-in, Firebase Authentication receives the IP address of the connection and the device's user agent (OS and SDK type) to prevent abuse.

#### Article 3 (Information Sent to the Leaderboard — Cloud Firestore)

When a game ends with a score of 1 or more and the play's start and end records (Article 4) have been accepted, the App sends the following information to the Developer's cloud (Google Cloud Firestore) and stores it on the daily, weekly, and all-time leaderboards. A record is overwritten only when you beat your best.

| Item | Content | Visibility |
| --- | --- | --- |
| Player name | A 1–12 character display name you set; defaults to an automatically assigned name | Shown on the in-app leaderboard |
| Country | A country you choose for the flag (ISO 3166-1 two-letter code); defaults to a guess from your device language | Shown on the in-app leaderboard |
| Score, mode, period | Your best score, the mode (A / AB / ABC / ABCD), and the period (daily / weekly / all-time) | Shown on the in-app leaderboard |
| Updated time | The server time at which the score was written | Shown on the in-app leaderboard |
| Anonymous UID | Identifies the owner of the record (used as the record's ID) | Not shown in the App* |
| Play record ID | A random ID used to match the play record in Article 4 | Not shown in the App* |
| Tap statistics | The values in Article 4 (2) | Not shown in the App* |

\* Leaderboard records are stored so that anyone can read them through the App, so items "not shown in the App" may technically be readable outside the App. None of them contain your name, contact details, or similar; they are pseudonymous.

**About the public leaderboard**: Your player name, country, score, and updated time are shown to all other users as part of the world ranking. Do not use your real name or other personally identifying information as your player name. You can change your player name and country at any time in Settings; the change appears in records written the next time you beat your best.

When you view the leaderboard, the App loads the top records and your own rank. The game itself can be played without a connection.

#### Article 4 (Information Sent to Prevent Cheating — from version 1.4)

To prevent illegitimate records made with auto-tapping tools, speed hacks, memory tampering, and the like, the App uses the following information. As a result of these checks, a record may be excluded from the leaderboard, and in serious cases further submissions from that anonymous UID may be blocked (a "ban").

1. **Play records (server time)**: When a play starts and ends, the App writes the mode, start time, end time, and score to a per-user area of Firestore (one per anonymous UID). All times are server times and are used to detect plays that are unnaturally long or short and records that are reused. The App cannot read this area. A play that starts without a connection is not eligible for the leaderboard.
2. **Tap statistics**: During a play, the App temporarily uses, on your device, the time, on-screen position, finger number, pressure, and contact size (where the device supports them) of each tap to calculate the following values: the number of taps, the number of fingers used, the variation in tap intervals, the variation in tap positions per button (in mm), the maximum taps per second (overall and per finger), and the number of distinct pressure/contact-size combinations. **The time and position of individual taps are not sent.** Only these values are sent, with the leaderboard record (Article 3) and in the Firebase Analytics `tap_stats` event (together with the mode and score, to set the detection thresholds). The raw tap data is discarded after the play ends.
3. **App Check (verifying the App)**: Firebase App Check is used to confirm that requests come from the genuine App on a genuine device. It uses the Google Play Integrity API on Android and Apple's App Attest on iOS, and sends attestation tokens issued by Google / Apple to Firebase. The tokens expire within a short time, and the Developer does not receive device identifiers from them.
4. **Ban records**: For a banned anonymous UID, the reason, date and time, and the number of records removed are stored in Firestore, and the Developer keeps a copy of the removed records so that a mistaken ban can be reversed.

#### Article 5 (Data Stored Only on Your Device)

The following data is stored on your device and is not sent off it, except where this Policy says it is sent.

- Your best score per mode, records such as total plays and best tap rate, unlocked modes, and whether you have seen the tutorial
- Profile and settings (player name, country, language, color theme, volume, effect settings, anonymous UID)
- Purchased items (support packs, ad removal)
- Data waiting to be sent to the leaderboard (when sending fails: score, mode, period, play record ID, tap statistics; resent within one hour of the start of the play and deleted after sending)
- The result-screen image captured for sharing (in the device's temporary folder)

Uninstalling the App deletes the data on your device. Because a new anonymous UID is issued afterwards, your earlier leaderboard records can no longer be linked to you.

#### Article 6 (Usage Analytics — Firebase Analytics)

The App uses Google's Firebase Analytics to improve its features and to tune the cheat-detection thresholds. The App records the following events:

- `game_start` (mode) / `game_finish` (mode, score) / `mode_select` / `mode_unlock` / `ranking_view` (mode, period) / `ad_view`
- `tutorial_step` / `tutorial_skip` (tutorial step)
- `tap_stats` (mode, score, and the values in Article 4 (2))

In addition, Firebase Analytics automatically collects an app-instance ID, device model, OS and app version, language, approximate location estimated from the IP address (country, region, and city level), app launches, screen views, and usage time, app updates, in-app purchase events (product ID and price), and the advertising ID (the Android advertising ID; on iOS the App does not ask for tracking permission, so the IDFA is not available and the IDFV is collected instead). The Developer uses this data to view statistics and does not use it to serve or target ads.

#### Article 7 (Crash Reporting — Firebase Crashlytics)

The App uses Firebase Crashlytics to find and fix defects. When the App crashes, for example, it sends the stack trace, the app's state at that time, device information such as model and OS, and a Crashlytics installation ID to Google.

#### Article 8 (Remote Configuration — Firebase Remote Config)

The App uses Firebase Remote Config to receive operational settings. When fetching, the SDK sends the Firebase installation ID, country, language, time zone, and OS version.

#### Article 9 (Advertising — Google AdMob / UMP)

Because the App is free, it shows ads from Google AdMob: a banner at the bottom of the Home screen, and a full-screen ad when you return from the result screen to Home (at least 30 seconds apart). The ad SDK is not called during play.

- To serve ads, measure their performance, and prevent fraud, the Google Mobile Ads SDK sends Google your IP address (used to estimate approximate location), device identifiers (such as the Android advertising ID and app set ID, or the iOS IDFV), ad interactions such as views and taps, and performance and diagnostic information such as app launch time. Google handles this data under its own policies (<https://policies.google.com/technologies/ads>).
- In regions where consent is required, such as the EEA, the UK, and Switzerland, the App shows a Google UMP consent screen and follows your choices. You can change them from "Ad privacy settings" in Settings. In other regions, personalized ads may be shown depending on your device settings.
- On iOS, the App does not ask for tracking permission (App Tracking Transparency), so the IDFA is not used.
- Purchasing a support pack (or the earlier "Remove ads") stops ads from being shown.

#### Article 10 (In-App Purchases)

The App offers support packs (three one-time purchases, each including ad removal) and restores the previously sold "Remove ads".

- Payment is processed by the Apple App Store (iOS) or Google Play (Android); the Developer does not receive payment details such as credit card numbers.
- The App refers to the store's purchase information to verify and restore purchases, and stores purchased items on your device.
- As stated in Article 6, Firebase Analytics may record in-app purchase events (product ID and price).

#### Article 11 (Sharing)

When you tap "Share" on the result screen, the App passes text with the mode, score, title, and store URL, together with an image of the result screen, to your OS's share sheet. You choose the destination, and handling there follows that service's policy. Nothing is sent to the Developer.

#### Article 12 (Provision to Third Parties)

The Developer does not sell your information and does not provide it to third parties except as follows:

- Google AdMob (Article 9): Google uses the information collected by the ad SDK under its own policies to serve and measure ads and to prevent fraud.
- The public leaderboard (Article 3): by its nature, it is shown to other users.
- Service providers: Google (Firebase / Google Cloud) processes and stores data on the Developer's instructions. Payments are handled by Apple / Google.
- Where required by law.

#### Article 13 (Children's Use)

The App is not directed at users under 13 years of age. Parents and guardians should manage installation, use, and purchases by children under 13. If the Developer learns that information from a child under 13 has been sent, it will delete it promptly.

#### Article 14 (Retention Periods)

| Data | Retention |
| --- | --- |
| Daily / weekly leaderboards | Deleted automatically about 2 days after the period ends (deletion may take up to about one more day) |
| All-time leaderboard | While the service is provided, or until you request deletion |
| Play records (Article 4 (1)) | Kept for investigating cheating while the service is provided, or until you request deletion |
| Anonymous sign-in account | While the service is provided, or until you request deletion |
| Ban records and copies of removed records | Until the ban is lifted or they are no longer needed |
| Firebase Analytics | According to the Google Analytics data-retention setting (user-level data for up to 14 months) |
| Firebase Crashlytics | For the period set by Google (crash data: 90 days) |
| Data on your device | Until you uninstall the App |

#### Article 15 (Storage and Security)

Cloud data is stored in Google Cloud (Firebase / Firestore), and access is restricted by Firestore Security Rules and App Check. All communication is encrypted (TLS). Data may be processed and stored on Google servers outside your country.

#### Article 16 (Your Rights and Data Deletion)

- **Requesting deletion**: To delete your cloud data (leaderboard records, play records, and the anonymous sign-in account), email us at <support@haroworks.com> with the subject "Data deletion request", and tell us your player name, country, OS (iOS / Android), and approximate score and date. Because the anonymous UID is not shown in the App, we identify your records from this information. We will, in principle, delete the records we can confirm within 30 days and let you know.
- Firebase Analytics, Crashlytics, and AdMob data are stored under identifiers that are not linked to your name or similar details, so the Developer may not be able to identify and delete them for an individual. They are deleted when the periods in Article 14 expire.
- **Data on your device**: Deleted when you uninstall the App.
- **Changing what is displayed**: You can change your player name, country, and language at any time in Settings.
- **Ad settings**: In your device settings (Android: Settings > Google > Ads; iOS: Settings > Privacy & Security), you can reset the advertising ID or turn off personalized ads. In regions where consent is required, you can change your consent from "Ad privacy settings" in Settings.
- **Rights under local laws**: Users in the EEA, the UK, California, and elsewhere may exercise rights such as access, correction, deletion, and objection under applicable law. Contact us at the email address above. The Developer does not sell personal information.

#### Article 17 (Governing Law)

This Policy shall be interpreted and applied in accordance with the laws of Japan.

#### Article 18 (Contact / Changes to This Policy)

For questions about this Policy or deletion requests, contact:

- Email: <support@haroworks.com>

The Developer may revise this Policy to reflect changes in law or in the App. A revised Policy takes effect when it is posted on this page. Important changes will also be announced in the App's release notes or by similar means.

---

**Revision history**

- v1.1 (2026-10-20): Fully revised for version 1.4. Added the information used to prevent cheating (play records, tap statistics, App Check, bans). Updated the Analytics events, ad formats and the information collected by the ad SDK, support packs, and sharing to match how the App actually works, and stated retention periods and how to request deletion. Removed the mention of "achievements" stored in the cloud, which the App never did.
- v1.0 (2026-06-12): Initial version, in effect with the v1.0.0 release.

---

<a id="zh-hans"></a>

## §C. 简体中文 (zh-Hans)

> 本译文仅供参考。如本译文与日文版（§A）或英文版（§B）之间存在任何差异，以日文版为准。

### 连打名人 / Tap Champion 隐私政策

连打名人（Tap Champion，以下简称"本应用"）的提供者 HaroWorks（以下简称"开发者"）就本应用所处理的信息，按以下内容规定其使用目的、发送对象以及保存期限。

#### 第 1 条（适用范围）

本政策适用于开发者通过 Apple App Store 和 Google Play 发布的移动应用"连打名人 / Tap Champion"（iOS / Android，后端相同）的所有用户。平台之间的不同之处会在正文中注明。

#### 第 2 条（账户与匿名认证）

本应用不要求登记姓名、电子邮件地址、电话号码等信息，也不提供会员注册或社交账号登录功能。

- 首次启动时，本应用会通过 Firebase Authentication 的**匿名登录**自动生成一个随机的匿名 ID（匿名 UID）。匿名 UID 不与姓名或联系信息相关联。
- 匿名 UID 用于区分各用户的排行榜记录、核对游戏记录以及防止作弊（第 4 条）。匿名 UID 不会显示在应用画面上。
- 进行匿名登录时，为防止滥用，Firebase Authentication 会接收连接来源的 IP 地址以及设备的用户代理（操作系统和 SDK 的类型）。

#### 第 3 条（发送至排行榜的信息 — Cloud Firestore）

当一局游戏结束、分数为 1 分以上，且该局游戏的开始和结束记录（第 4 条）已通过验证时，本应用会将以下信息发送至开发者的云端（Google Cloud Firestore），并保存到每日、每周和总榜各排行榜中。仅在刷新个人最佳成绩时才会改写记录。

| 项目 | 内容 | 公开范围 |
| --- | --- | --- |
| 玩家名称 | 用户设置的 1～12 个字符的显示名称；初始值为自动分配的名称 | 显示在应用内的排行榜上 |
| 国家/地区 | 用户为显示国旗而选择的国家/地区（ISO 3166-1 两字母代码）；初始值根据设备的语言推定 | 显示在应用内的排行榜上 |
| 分数、模式、期间 | 最佳分数、模式（A / AB / ABC / ABCD）以及期间（每日 / 每周 / 总榜） | 显示在应用内的排行榜上 |
| 更新时间 | 写入分数时的服务器时间 | 显示在应用内的排行榜上 |
| 匿名 UID | 用于区分记录的所有者（用作记录的 ID） | 不在应用内显示※ |
| 游戏记录 ID | 用于与第 4 条所述游戏记录进行核对的随机 ID | 不在应用内显示※ |
| 点击统计 | 第 4 条第 (2) 项所述的数值 | 不在应用内显示※ |

※ 由于排行榜记录以任何人都可通过本应用读取的形式保存，因此"不在应用内显示"的项目在技术上也可能被从应用外部读取。这些项目均为不包含姓名、联系方式等的化名信息。

**关于公开排行榜**：玩家名称、国家/地区、分数和更新时间将作为世界排名向其他所有用户显示。请勿将真实姓名等可识别个人身份的信息用作玩家名称。玩家名称和国家/地区可随时在设置画面中更改，更改将从下次刷新最佳成绩时写入的记录起生效。

浏览排行榜时，本应用会读取排行榜靠前的记录以及您自己的排名。游戏本身无需联网即可游玩。

#### 第 4 条（为防止作弊而发送的信息 — 自版本 1.4 起）

为防止利用自动连点工具、变速、篡改内存等手段产生不正当记录，本应用会使用以下信息。根据判定结果，相应记录可能会被排除在排行榜之外；情节严重时，可能会停止接收来自该匿名 UID 的记录提交（以下简称"停用"）。

1. **游戏记录（服务器时间）**：每局游戏开始和结束时，本应用会将模式、开始时间、结束时间和分数写入 Firestore 中按用户划分的区域（每个匿名 UID 一个）。所有时间均为服务器时间，用于识别游戏时长异常偏长或偏短的记录以及被重复使用的记录。本应用无法读取该区域。开始时无法联网的游戏不计入排行榜。
2. **点击统计**：游戏过程中，本应用会在设备上临时使用每次点击的时间、在屏幕上的位置、手指编号、按压力度和接触面积（如设备支持），并计算以下数值：点击次数、使用的手指数、点击间隔的离散程度、各按钮点击位置的离散程度（mm）、每秒最大点击次数（整体及每根手指）、按压力度与接触面积组合的种类数。**本应用不会发送每次点击的时间或位置本身**，只会将这些数值随排行榜记录（第 3 条）发送，并发送至 Firebase Analytics 的 `tap_stats` 事件（连同模式和分数，用于确定判定的基准值）。原始点击记录在游戏结束后即被丢弃。
3. **App Check（确认应用的合法性）**：本应用通过 Firebase App Check 确认通信来自正版应用和真实设备。在 Android 上使用 Google Play Integrity API，在 iOS 上使用 Apple 的 App Attest，并将 Google / Apple 签发的验证令牌发送至 Firebase。令牌会在短时间内失效，开发者不会从中获取设备标识符。
4. **停用记录**：对于已被停用的匿名 UID，本应用会将停用原因、日期时间以及被删除记录的数量保存在 Firestore 中；同时，开发者会保管被删除记录的副本，以便在误判时予以恢复。

#### 第 5 条（仅保存在设备上的数据）

以下数据保存在用户的设备上，除本政策规定会发送的情形外，不会发送到设备之外。

- 各模式的个人最佳分数、累计游戏次数和最高连打速度等记录、模式的解锁状态、是否已阅读教程
- 玩家资料和设置（玩家名称、国家/地区、语言、机体颜色、音量、演出效果设置、匿名 UID）
- 已购买的商品（应援包、去除广告）
- 等待发送至排行榜的数据（发送失败时产生，包括分数、模式、期间、游戏记录 ID 和点击统计；在该局游戏开始后 1 小时的期限内重新发送，发送后删除）
- 为分享而截取的结果画面图片（保存在设备的临时文件夹中）

卸载本应用后，设备上的数据将被删除。由于匿名 UID 也会重新生成，卸载前的排行榜记录将无法再与您关联。

#### 第 6 条（使用情况分析 — Firebase Analytics）

为改进功能和调整作弊判定的基准值，本应用使用 Google 的 Firebase Analytics。本应用记录的事件如下：

- `game_start`（模式）/ `game_finish`（模式、分数）/ `mode_select` / `mode_unlock` / `ranking_view`（模式、期间）/ `ad_view`
- `tutorial_step` / `tutorial_skip`（教程的步骤）
- `tap_stats`（模式、分数以及第 4 条第 (2) 项所述的数值）

此外，Firebase Analytics 还会自动收集应用实例 ID、设备型号、操作系统和应用版本、语言、根据 IP 地址推测的大致位置（以国家、地区、城市为单位）、启动、画面浏览和使用时长、应用更新、应用内购买事件（商品 ID、价格）以及广告标识符（Android 广告 ID；在 iOS 上，由于本应用不请求跟踪许可，因此不会获取 IDFA，而是收集 IDFV）。开发者仅将这些信息用于查看统计数据，不会用于投放广告或广告定向。

#### 第 7 条（崩溃报告 — Firebase Crashlytics）

为发现和修复故障，本应用使用 Firebase Crashlytics。在本应用异常退出等情况下，堆栈跟踪、当时的应用状态、设备型号和操作系统等信息以及 Crashlytics 安装 ID 将发送给 Google。

#### 第 8 条（远程配置 — Firebase Remote Config）

为接收运营中使用的配置值，本应用使用 Firebase Remote Config。获取配置时，SDK 会发送 Firebase 安装 ID、国家/地区、语言、时区和操作系统版本。

#### 第 9 条（广告 — Google AdMob / UMP）

由于本应用免费提供，因此会显示 Google AdMob 的广告，包括主画面底部的横幅广告，以及从结果画面返回主画面时显示的全屏广告（间隔至少 30 秒）。游戏过程中不会调用广告 SDK。

- 为投放广告、衡量广告效果和防止欺诈，Google 移动广告 SDK 会向 Google 发送 IP 地址（用于推测大致位置）、设备标识符（例如 Android 广告 ID 和应用集 ID，或 iOS 的 IDFV）、广告展示和点按等互动信息，以及应用启动时间等性能和诊断信息。Google 依据其政策（<https://policies.google.com/technologies/ads>）处理这些信息。
- 在欧洲经济区（EEA）、英国、瑞士等需要征得同意的地区，本应用会显示 Google UMP 的同意画面，并遵从用户的选择。用户可在设置画面的「广告隐私设置」中更改所做的选择。在其他地区，可能会根据设备的设置显示个性化广告。
- 在 iOS 上，本应用不请求跟踪许可（App Tracking Transparency），因此不会使用 IDFA。
- 购买应援包（或以前销售的"去除广告"）后，将不再显示广告。

#### 第 10 条（应用内购买）

本应用提供应援包（3 种一次性买断商品，均附带去除广告），并支持恢复以前销售的"去除广告"。

- 支付由 Apple App Store（iOS）或 Google Play（Android）处理，开发者不会获取信用卡号等支付信息。
- 为确认和恢复购买，本应用会参考商店的购买信息。已购买的商品保存在设备上。
- 如第 6 条所述，Firebase Analytics 可能会记录应用内购买事件（商品 ID、价格）。

#### 第 11 条（分享）

在结果画面点按"分享"后，本应用会将包含模式、分数、称号和商店 URL 的文字以及结果画面的图片传递给操作系统的分享画面。分享对象由用户选择，分享对象处的处理遵循各服务的政策。这些内容不会发送给开发者。

#### 第 12 条（向第三方提供）

开发者不出售用户的信息。除以下情形外，不会向第三方提供用户的信息。

- 第 9 条所述的 Google AdMob：Google 依据其自身政策，将广告 SDK 收集的信息用于投放和衡量广告以及防止欺诈。
- 第 3 条所述的公开排行榜：因其性质，会向其他用户显示。
- 业务委托：在开发者指示的范围内，委托 Google（Firebase / Google Cloud）处理和保存数据。支付由 Apple / Google 处理。
- 依据法律法规的情形。

#### 第 13 条（儿童使用）

本应用不以未满 13 周岁的用户为对象。请家长或监护人对未满 13 周岁用户的安装、使用及购买行为进行管理。如发现有未满 13 周岁用户的信息被发送，开发者将及时删除。

#### 第 14 条（保存期限）

| 数据 | 保存期限 |
| --- | --- |
| 每日 / 每周排行榜 | 期间结束约 2 天后自动删除（删除处理可能还需要约 1 天） |
| 总榜 | 在服务提供期间，或直至用户申请删除 |
| 游戏记录（第 4 条第 (1) 项） | 为调查作弊，在服务提供期间，或直至用户申请删除 |
| 匿名登录的账户 | 在服务提供期间，或直至用户申请删除 |
| 停用记录及被删除记录的副本 | 直至解除停用，或直至不再需要 |
| Firebase Analytics | 遵循 Google Analytics 的数据保留设置（用户级数据最长 14 个月） |
| Firebase Crashlytics | Google 规定的期限（崩溃数据为 90 天） |
| 设备上的数据 | 直至卸载本应用 |

#### 第 15 条（数据的保存与安全）

云端数据保存在 Google Cloud（Firebase / Firestore）中，并通过 Firestore Security Rules 和 App Check 限制访问。所有通信均经过加密（TLS）。数据可能会在用户所在国家/地区以外的 Google 服务器上处理和保存。

#### 第 16 条（用户的权利与数据的删除）

- **申请删除**：如需删除云端数据（排行榜记录、游戏记录、匿名登录的账户），请发送电子邮件至 <support@haroworks.com> 提出申请。请在邮件主题中注明"数据删除申请"，并告知您的玩家名称、国家/地区、所用操作系统（iOS / Android）以及大致的分数和日期时间。由于匿名 UID 不会显示在应用内，我们将根据这些信息确定您的记录。原则上，我们会在 30 天内删除能够确认的记录，并通知您。
- Firebase Analytics、Crashlytics 和 AdMob 的数据以不与姓名等关联的标识符保存，因此开发者可能无法识别特定个人并删除其数据。这些数据将在第 14 条所述期限届满后被删除。
- **设备上的数据**：卸载本应用后即被删除。
- **更改显示信息**：玩家名称、国家/地区和语言可随时在设置画面中更改。
- **广告设置**：可在设备设置中（Android：设置 > Google > 广告；iOS：设置 > 隐私与安全性）重置广告标识符或停用个性化广告。在需要征得同意的地区，可在设置画面的「广告隐私设置」中更改同意设置。
- **依据各国法律享有的权利**：欧洲经济区、英国、美国加利福尼亚州等地区的用户，可依据适用法律行使访问、更正、删除、反对处理等权利。请通过上述电子邮件与我们联系。开发者不出售个人信息。

#### 第 17 条（准据法）

本政策的解释和适用以日本国法律为准据法。

#### 第 18 条（联系方式・本政策的变更）

如对本政策有任何疑问或希望申请删除数据，请通过以下方式联系我们：

- 电子邮件：<support@haroworks.com>

本政策可能因相关法律法规的修订或本应用的变更而进行修订。修订后的政策自在本页面发布之时起生效。如有重大变更，我们还将通过本应用的版本说明等方式进行告知。

---

**修订历史**

- v1.1（2026-10-20）：配合版本 1.4 进行全面修订。新增为防止作弊而使用的信息（游戏记录、点击统计、App Check、停用）。根据本应用的实际运行情况，更新了 Analytics 事件、广告类型及广告 SDK 收集的信息、应援包以及分享的内容，并明确了保存期限和申请删除的方法。删除了关于"成就"保存在云端的记载（实际上从未保存在云端）。
- v1.0（2026-06-12）：初版制定（随 v1.0.0 发布生效）。

---

<a id="zh-hant"></a>

## §D. 繁體中文 (zh-Hant)

> 本譯文僅供參考。如本譯文與日文版（§A）或英文版（§B）之間有任何歧異，以日文版為準。

### 連打名人 / Tap Champion 隱私權政策

連打名人（Tap Champion，以下簡稱「本應用程式」）的提供者 HaroWorks（以下簡稱「開發者」）依下列規定，說明本應用程式所處理的資訊用於何種目的、傳送至何處，以及保存多長期間。

#### 第 1 條（適用範圍）

本政策適用於開發者透過 Apple App Store 及 Google Play 發布之行動應用程式「連打名人 / Tap Champion」（iOS / Android，後端共用）的所有使用者。各平台的差異會於本文中註明。

#### 第 2 條（帳號與匿名驗證）

本應用程式不要求登錄姓名、電子郵件地址、電話號碼等資訊，亦不提供會員註冊或社群帳號登入功能。

- 首次啟動時，本應用程式會透過 Firebase Authentication 的**匿名登入**，自動產生一組隨機的匿名 ID（匿名 UID）。匿名 UID 不與姓名或聯絡資訊相關聯。
- 匿名 UID 用於區分各使用者的排行榜紀錄、比對遊玩紀錄，以及防止作弊（第 4 條），不會顯示於應用程式畫面上。
- 進行匿名登入時，Firebase Authentication 會為防止濫用而取得連線來源的 IP 位址及裝置的使用者代理程式（作業系統及 SDK 的類型）。

#### 第 3 條（傳送至排行榜的資訊 — Cloud Firestore）

遊戲結束時，如分數為 1 分以上，且遊玩的開始與結束紀錄（第 4 條）已通過檢核，本應用程式會將下列資訊傳送至開發者的雲端（Google Cloud Firestore），並儲存於每日、每週及歷來（All Time）各排行榜。僅於刷新個人最佳紀錄時才會覆寫。

| 項目 | 內容 | 公開範圍 |
| --- | --- | --- |
| 玩家名稱 | 使用者設定的 1～12 個字元的顯示名稱；初始值為自動產生的名稱 | 顯示於應用程式的排行榜 |
| 國家/地區 | 使用者為顯示國旗所選擇的國家/地區（ISO 3166-1 的 2 字母代碼）；初始值依裝置的語言推定 | 顯示於應用程式的排行榜 |
| 分數・模式・期間 | 最佳分數、模式（A / AB / ABC / ABCD）及期間（每日 / 每週 / 歷來） | 顯示於應用程式的排行榜 |
| 更新時間 | 寫入分數時的伺服器時間 | 顯示於應用程式的排行榜 |
| 匿名 UID | 用於區分紀錄的所有者（作為紀錄的 ID 使用） | 不顯示於應用程式※ |
| 遊玩紀錄 ID | 用於與第 4 條遊玩紀錄比對的隨機 ID | 不顯示於應用程式※ |
| 點擊統計 | 第 4 條 (2) 的數值 | 不顯示於應用程式※ |

※ 由於排行榜紀錄是以任何人皆可透過應用程式讀取的形式儲存，標示為「不顯示於應用程式」的項目，在技術上仍可能從應用程式以外讀取。上述項目均為不含姓名、聯絡資訊等的假名資訊。

**關於公開排行榜**：玩家名稱、國家/地區、分數及更新時間將作為世界排名向其他所有使用者顯示。請勿將真實姓名等可識別個人身分的資訊用作玩家名稱。玩家名稱及國家/地區可隨時於設定畫面中變更，變更將自下次刷新最佳紀錄時寫入的紀錄起反映。

瀏覽排行榜時，本應用程式會讀取排行榜前段的紀錄及您本人的名次。遊戲本身無需連線即可遊玩。

#### 第 4 條（為防止作弊而傳送的資訊 — 自 1.4 版起）

為防止使用自動連點工具、變速、竄改記憶體等方式產生不正當紀錄，本應用程式會使用下列資訊。依判定結果，紀錄可能被排除於排行榜之外；情節嚴重者，可能停止該匿名 UID 的所有紀錄提交（以下稱「停權」）。

1. **遊玩紀錄（伺服器時間）**：於遊玩開始及結束時，本應用程式會將模式、開始時間、結束時間及分數寫入 Firestore 中各使用者專屬的區域（依匿名 UID 區分）。時間一律採用伺服器時間，用於辨識遊玩時間不自然地過長或過短的紀錄，以及重複使用同一紀錄的情形。本應用程式無法讀取此區域。開始時無法連線的遊玩，不列入排行榜。
2. **點擊統計**：遊玩期間，本應用程式會於裝置內暫時使用每次點擊的時間、畫面上的位置、手指編號、按壓力道及接觸面積（限裝置支援時），以計算下列數值：點擊次數、使用的手指數、點擊間隔的離散程度、各按鈕點擊位置的離散程度（mm）、每秒最高點擊次數（整體及每根手指）、按壓力道與接觸面積組合的種類數。**不會傳送每次點擊的時間或位置本身**，僅將上述數值傳送至排行榜紀錄（第 3 條）及 Firebase Analytics 的 `tap_stats` 事件（連同模式及分數，用於訂定判定的基準值）。原始的點擊紀錄於遊玩結束後即予捨棄。
3. **App Check（確認應用程式的真實性）**：本應用程式透過 Firebase App Check 確認通訊來自正版應用程式及真實裝置。Android 使用 Google Play Integrity API，iOS 使用 Apple 的 App Attest，並將 Google / Apple 核發的驗證用權杖傳送至 Firebase。權杖會在短時間內失效，開發者不會從中取得裝置識別碼。
4. **停權紀錄**：對於遭停權的匿名 UID，本應用程式會將停權原因、日期時間及已刪除紀錄的筆數儲存於 Firestore；為便於誤判時恢復，開發者會自行保管已刪除紀錄的副本。

#### 第 5 條（僅儲存於裝置上的資料）

下列資料儲存於使用者的裝置內，除本政策規定會傳送的情形外，不會傳送至裝置之外。

- 各模式的個人最佳分數、累計遊玩次數及最高連打速度等紀錄、模式的解鎖狀態、是否已閱讀教學
- 個人檔案與設定（玩家名稱、國家/地區、語言、機體顏色、音量、演出效果設定、匿名 UID）
- 已購買的商品（應援包、移除廣告）
- 等待傳送至排行榜的資料（於傳送失敗時產生：分數、模式、期間、遊玩紀錄 ID、點擊統計；於遊玩開始後 1 小時的期限內重新傳送，傳送後刪除）
- 為分享而擷取的結果畫面圖片（裝置的暫存資料夾）

解除安裝本應用程式後，裝置上的資料將被刪除。由於匿名 UID 也會重新產生，解除安裝前的排行榜紀錄將無法再與您建立關聯。

#### 第 6 條（使用情況分析 — Firebase Analytics）

為改善功能及調整作弊判定的基準值，本應用程式使用 Google 的 Firebase Analytics。本應用程式記錄的事件如下：

- `game_start`（模式）/ `game_finish`（模式、分數）/ `mode_select` / `mode_unlock` / `ranking_view`（模式、期間）/ `ad_view`
- `tutorial_step` / `tutorial_skip`（教學的階段）
- `tap_stats`（模式、分數及第 4 條 (2) 的數值）

此外，Firebase Analytics 會自動蒐集應用程式執行個體 ID、裝置型號、作業系統及應用程式版本、語言、依 IP 位址推定的大致地區（國家、地區及城市層級）、啟動・畫面瀏覽・使用時間、應用程式更新、應用程式內購買事件（商品 ID、價格），以及廣告 ID（Android 的廣告 ID；iOS 上由於本應用程式不要求追蹤授權，因此不會取得 IDFA，改為取得 IDFV）。開發者僅將這些資料用於查看統計，不會用於投放廣告或廣告鎖定。

#### 第 7 條（當機報告 — Firebase Crashlytics）

為發現並修正錯誤，本應用程式使用 Firebase Crashlytics。於本應用程式異常終止等情形時，會將堆疊追蹤、當時的應用程式狀態、裝置型號及作業系統等資訊，以及 Crashlytics 安裝 ID 傳送給 Google。

#### 第 8 條（遠端設定 — Firebase Remote Config）

為接收營運中的設定值，本應用程式使用 Firebase Remote Config。取得設定時，SDK 會傳送 Firebase 安裝 ID、國家、語言、時區及作業系統版本。

#### 第 9 條（廣告 — Google AdMob / UMP）

由於本應用程式免費提供，因此會顯示 Google AdMob 的廣告，包括主畫面下方的橫幅廣告，以及從結果畫面返回主畫面時的全螢幕廣告（間隔至少 30 秒）。遊玩期間不會呼叫廣告 SDK。

- 為投放廣告、評估成效及防止詐欺，Google Mobile Ads SDK 會將 IP 位址（用於推定大致位置）、裝置識別碼（Android 的廣告 ID 及應用程式集 ID、iOS 的 IDFV 等）、廣告的顯示及點擊等互動，以及應用程式啟動時間等效能與診斷資訊傳送給 Google。Google 依其政策（<https://policies.google.com/technologies/ads>）處理這些資訊。
- 於歐洲經濟區（EEA）、英國、瑞士等需取得同意的地區，本應用程式會顯示 Google UMP 的同意畫面，並依循使用者的選擇。使用者可透過設定畫面中的「廣告隱私設定」變更選擇。於其他地區，可能會依裝置設定顯示個人化廣告。
- 於 iOS 上，本應用程式不要求追蹤授權（App Tracking Transparency），因此不會使用 IDFA。
- 購買應援包（或先前的「移除廣告」）後，將不再顯示廣告。

#### 第 10 條（應用程式內購買）

本應用程式提供應援包（3 種一次性買斷商品，皆附移除廣告），並支援恢復先前販售的「移除廣告」。

- 付款由 Apple App Store（iOS）或 Google Play（Android）處理，開發者不會取得信用卡號碼等付款資訊。
- 為驗證及恢復購買，本應用程式會參考商店的購買資訊。已購買的商品儲存於裝置上。
- 如第 6 條所述，Firebase Analytics 可能會記錄應用程式內購買事件（商品 ID、價格）。

#### 第 11 條（分享）

按下結果畫面的「分享」後，本應用程式會將包含模式、分數、稱號及商店 URL 的文字，以及結果畫面的圖片，交給作業系統的分享畫面。分享對象由使用者選擇，分享目的地的處理遵循各服務的政策。這些內容不會傳送給開發者。

#### 第 12 條（提供予第三方）

開發者不會販售使用者的資訊。除下列情形外，不會提供予第三方。

- 第 9 條的 Google AdMob：Google 會依其政策，將廣告 SDK 所蒐集的資訊用於投放及評估廣告、防止詐欺。
- 第 3 條的公開排行榜：因其性質，會向其他使用者顯示。
- 業務委託：於開發者指示的範圍內，委託 Google（Firebase / Google Cloud）處理及保存資料。付款由 Apple / Google 處理。
- 依法令要求的情形。

#### 第 13 條（兒童使用）

本應用程式不以未滿 13 歲的使用者為對象。請家長或監護人管理未滿 13 歲者的安裝、使用及購買行為。如發現有未滿 13 歲者的資訊被傳送，開發者將儘速刪除。

#### 第 14 條（保存期間）

| 資料 | 保存期間 |
| --- | --- |
| 每日 / 每週排行榜 | 於期間結束約 2 天後自動刪除（刪除處理可能需再約 1 天） |
| 歷來排行榜 | 於服務提供期間，或直至您申請刪除為止 |
| 遊玩紀錄（第 4 條 (1)） | 為調查作弊，於服務提供期間，或直至您申請刪除為止 |
| 匿名登入帳號 | 於服務提供期間，或直至您申請刪除為止 |
| 停權紀錄及已刪除紀錄的副本 | 直至解除停權，或不再需要為止 |
| Firebase Analytics | 依 Google Analytics 的資料保留設定（使用者層級資料最長 14 個月） |
| Firebase Crashlytics | 依 Google 規定的期間（當機資料為 90 天） |
| 裝置上的資料 | 直至解除安裝本應用程式為止 |

#### 第 15 條（資料的保存與安全）

雲端資料儲存於 Google Cloud（Firebase / Firestore），並透過 Firestore Security Rules 及 App Check 限制存取。所有通訊均經加密（TLS）。資料可能於使用者所在國家/地區以外的 Google 伺服器上處理及儲存。

#### 第 16 條（使用者的權利與資料刪除）

- **申請刪除**：如需刪除雲端資料（排行榜紀錄、遊玩紀錄及匿名登入帳號），請以電子郵件（<support@haroworks.com>）提出申請。請於主旨註明「資料刪除申請」，並告知玩家名稱、國家/地區、使用的作業系統（iOS / Android），以及大致的分數與日期時間。由於匿名 UID 不會顯示於應用程式中，我們將依據上述資訊找出您的紀錄。經確認的紀錄，原則上將於 30 日內刪除並通知您。
- Firebase Analytics、Crashlytics 及 AdMob 的資料係以不與姓名等相關聯的識別碼儲存，因此開發者可能無法識別特定個人並予以刪除。這些資料將於第 14 條所定期間屆滿後刪除。
- **裝置上的資料**：解除安裝本應用程式後即刪除。
- **變更顯示資訊**：玩家名稱、國家/地區及語言可隨時於設定畫面中變更。
- **廣告設定**：可於裝置設定中（Android：設定 > Google > 廣告；iOS：設定 > 隱私權與安全性）重設廣告 ID 或停用個人化廣告。於需取得同意的地區，可透過設定畫面中的「廣告隱私設定」變更同意。
- **依各國法令享有的權利**：歐洲經濟區、英國、美國加州等地區的使用者，可依適用法令行使存取、更正、刪除及反對處理等權利。請透過上述電子郵件與我們聯繫。開發者不會販售個人資料。

#### 第 17 條（準據法）

本政策的解釋及適用，以日本國法律為準據法。

#### 第 18 條（聯絡方式・本政策的變更）

如對本政策有任何疑問或希望申請刪除資料，請透過下列方式與我們聯繫：

- 電子郵件：<support@haroworks.com>

本政策可能因法令修訂或應用程式變更而進行修訂。修訂後的政策自於本頁面公布之時起生效。如有重大變更，我們亦將透過應用程式的版本說明等方式進行告知。

---

**修訂歷程**

- v1.1（2026-10-20）：配合 1.4 版全面修訂。新增用於防止作弊的資訊（遊玩紀錄、點擊統計、App Check、停權）。依本應用程式的實際運作，更新 Analytics 事件、廣告類型及廣告 SDK 蒐集的資訊、應援包及分享內容，並明確記載保存期間及申請刪除的方式。刪除原本未曾儲存於雲端的「成就」相關記載。
- v1.0（2026-06-12）：初版（隨 v1.0.0 發布生效）。

---

<a id="ko"></a>

## §E. 한국어 (ko)

> 본 번역은 참고용입니다. 본 번역과 일본어판(§A) 또는 영어판(§B) 사이에 차이가 있는 경우 일본어판이 우선합니다.

### 연타 명인 / Tap Champion 개인정보 처리방침

연타 명인(Tap Champion, 이하 "본 앱")의 제공자 HaroWorks(이하 "개발자")는 본 앱에서 다루는 정보를 어떤 목적으로, 어디로 보내며, 얼마 동안 보관하는지를 다음과 같이 정합니다.

#### 제1조 (적용 범위)

본 방침은 개발자가 Apple App Store 및 Google Play에서 배포하는 모바일 앱 "연타 명인 / Tap Champion"(iOS / Android, 백엔드는 공통)의 모든 이용자에게 적용됩니다. 플랫폼에 따라 다른 사항은 본문 중에 별도로 표기합니다.

#### 제2조 (계정 및 익명 인증)

본 앱은 이름, 이메일 주소, 전화번호 등의 등록을 요구하지 않으며, 회원 가입이나 소셜 로그인 기능도 없습니다.

- 최초 실행 시 Firebase Authentication의 **익명 로그인**을 통해 무작위 익명 ID(익명 UID)가 자동으로 발급됩니다. 익명 UID에는 이름이나 연락처가 연결되지 않습니다.
- 익명 UID는 랭킹 기록을 이용자별로 구별하고, 플레이 기록을 대조하며, 부정행위를 방지(제4조)하는 데 사용됩니다. 앱 화면에는 표시되지 않습니다.
- 익명 로그인 시 Firebase Authentication은 부정 이용을 방지하기 위해 접속 IP 주소와 기기의 사용자 에이전트(OS 및 SDK 종류)를 수신합니다.

#### 제3조 (랭킹에 전송하는 정보 — Cloud Firestore)

게임이 종료되고 점수가 1점 이상이며 플레이 시작 및 종료 기록(제4조)이 정상적으로 처리된 경우, 본 앱은 다음 정보를 개발자의 클라우드(Google Cloud Firestore)로 전송하여 일간·주간·전체 기간의 각 랭킹에 저장합니다. 기록은 개인 최고 점수를 경신한 경우에만 덮어씁니다.

| 항목 | 내용 | 공개 범위 |
| --- | --- | --- |
| 플레이어 이름 | 이용자가 설정하는 1~12자의 표시 이름. 초기값은 자동으로 지정되는 이름 | 앱의 랭킹에 표시 |
| 국가 | 국기 표시를 위해 이용자가 선택하는 국가(ISO 3166-1의 2자리 코드). 초기값은 기기의 언어로부터 추정 | 앱의 랭킹에 표시 |
| 점수·모드·기간 | 최고 점수와 모드(A / AB / ABC / ABCD), 기간(일간 / 주간 / 전체 기간) | 앱의 랭킹에 표시 |
| 갱신 일시 | 점수를 기록한 서버 시각 | 앱의 랭킹에 표시 |
| 익명 UID | 기록 소유자의 구별(기록의 ID로 사용) | 앱에는 표시하지 않음※ |
| 플레이 기록 ID | 제4조의 플레이 기록과 대조하기 위한 무작위 ID | 앱에는 표시하지 않음※ |
| 탭 통계 | 제4조 (2)의 수치 | 앱에는 표시하지 않음※ |

※ 랭킹 기록은 앱을 통해 누구나 읽을 수 있는 형태로 저장되므로, "앱에는 표시하지 않음" 항목도 기술적으로는 앱 밖에서 읽힐 수 있습니다. 모두 이름이나 연락처 등을 포함하지 않는 가명 정보입니다.

**공개 랭킹에 대하여**: 플레이어 이름, 국가, 점수, 갱신 일시는 세계 랭킹으로서 다른 모든 이용자에게 표시됩니다. 플레이어 이름에 실명 등 개인을 식별할 수 있는 정보를 사용하지 마십시오. 플레이어 이름과 국가는 설정 화면에서 언제든지 변경할 수 있으며, 다음에 최고 점수를 경신할 때의 기록부터 반영됩니다.

랭킹을 열람할 때는 랭킹 상위 기록과 본인의 순위를 불러옵니다. 플레이 자체는 통신 없이도 할 수 있습니다.

#### 제4조 (부정행위 방지를 위해 전송하는 정보 — 버전 1.4부터)

자동 연타 도구, 속도 조작, 메모리 변조 등에 의한 부정한 기록을 방지하기 위해 다음 정보를 사용합니다. 판정 결과에 따라 기록이 랭킹 대상에서 제외되거나, 악질적인 경우에는 해당 익명 UID의 기록 전송 자체를 차단(이하 "이용 정지")할 수 있습니다.

1. **플레이 기록(서버 시각)**: 플레이 시작 시와 종료 시에 모드, 시작 시각, 종료 시각, 점수를 Firestore의 이용자별 영역(익명 UID별)에 기록합니다. 시각은 모두 서버 시각이며, 플레이 시간이 부자연스럽게 길거나 짧은 기록이나 동일한 기록의 재사용을 가려내는 데 사용합니다. 이 영역은 앱에서 읽을 수 없습니다. 시작 시에 통신할 수 없었던 플레이는 랭킹 대상에서 제외됩니다.
2. **탭 통계**: 플레이 중 기기 내에서 각 탭의 시각, 화면상의 위치, 손가락 번호, 누른 세기, 접촉 크기(기기가 지원하는 경우)를 일시적으로 사용하여 다음 수치를 계산합니다: 탭 수, 사용한 손가락 수, 탭 간격의 편차, 버튼별 탭 위치의 편차(mm), 1초당 최대 탭 수(전체 및 손가락 1개당), 누른 세기와 접촉 크기 조합의 종류 수. **개별 탭의 시각이나 위치 자체는 전송하지 않으며**, 수치만을 랭킹 기록(제3조)과 Firebase Analytics의 `tap_stats` 이벤트(모드·점수와 함께. 판정 기준값을 정하기 위함)로 전송합니다. 원래의 탭 기록은 플레이 종료 후 폐기합니다.
3. **App Check(앱의 정당성 확인)**: Firebase App Check를 통해 통신이 정규 앱과 기기에서 온 것인지 확인합니다. Android에서는 Google Play Integrity API, iOS에서는 Apple의 App Attest를 사용하며, Google / Apple이 발급하는 확인용 토큰을 Firebase로 전송합니다. 토큰은 짧은 시간 내에 만료되며, 개발자는 이 토큰으로부터 기기 식별자를 받지 않습니다.
4. **이용 정지 기록**: 이용 정지된 익명 UID에 대해 사유, 일시, 삭제한 기록의 건수를 Firestore에 저장하며, 착오가 있었을 경우 되돌릴 수 있도록 삭제한 기록의 사본을 개발자가 보관합니다.

#### 제5조 (기기 내에만 저장되는 데이터)

다음 데이터는 이용자의 기기 내에 저장되며, 본 방침에서 전송한다고 정한 경우를 제외하고 기기 밖으로 전송되지 않습니다.

- 각 모드의 개인 최고 점수, 누적 플레이 횟수·최고 연사 속도 등의 기록, 모드 잠금 해제 상태, 튜토리얼 열람 여부
- 프로필 및 설정(플레이어 이름, 국가, 언어, 기체 색상, 음량, 연출 설정, 익명 UID)
- 구매한 상품(응원 팩, 광고 제거)
- 랭킹 전송 대기 중인 데이터(통신에 실패한 경우. 점수, 모드, 기간, 플레이 기록 ID, 탭 통계. 플레이 시작부터 1시간의 기한 내에 재전송하며, 전송 후 삭제)
- 공유를 위해 캡처한 결과 화면 이미지(기기의 임시 폴더)

앱을 삭제하면 기기 내 데이터는 삭제됩니다. 익명 UID도 새로 발급되므로, 삭제 전의 랭킹 기록과는 더 이상 연결되지 않습니다.

#### 제6조 (이용 현황 분석 — Firebase Analytics)

기능 개선 및 부정행위 판정 기준값의 조정을 위해 Google의 Firebase Analytics를 이용합니다. 본 앱이 기록하는 이벤트는 다음과 같습니다.

- `game_start`(모드) / `game_finish`(모드·점수) / `mode_select` / `mode_unlock` / `ranking_view`(모드·기간) / `ad_view`
- `tutorial_step` / `tutorial_skip`(튜토리얼 단계)
- `tap_stats`(모드·점수 및 제4조 (2)의 수치)

또한 Firebase Analytics는 앱 인스턴스 ID, 기기 모델, OS 및 앱 버전, 언어, IP 주소로부터 추정한 대략적인 지역(국가·지역·도시 단위), 실행·화면 표시·이용 시간, 앱 업데이트, 인앱 결제 이벤트(상품 ID·가격), 광고 ID(Android의 광고 ID. iOS에서는 본 앱이 추적 허용을 요청하지 않으므로 IDFA는 수집되지 않으며, 대신 IDFV)를 자동으로 수집합니다. 개발자는 이를 통계로 확인하는 데 사용하며, 광고 게재나 타기팅에는 사용하지 않습니다.

#### 제7조 (비정상 종료 보고 — Firebase Crashlytics)

결함을 발견하고 수정하기 위해 Firebase Crashlytics를 이용합니다. 앱이 비정상 종료된 경우 등에 스택 트레이스, 그 시점의 앱 상태, 기기 모델·OS 등의 정보, Crashlytics 설치 ID를 Google에 전송합니다.

#### 제8조 (원격 구성 — Firebase Remote Config)

운영 중의 설정값을 받기 위해 Firebase Remote Config를 이용합니다. 가져올 때 SDK가 Firebase 설치 ID, 국가, 언어, 시간대, OS 버전을 전송합니다.

#### 제9조 (광고 — Google AdMob / UMP)

본 앱은 무료로 제공되므로 Google AdMob 광고를 표시합니다. 홈 화면 하단의 배너 광고와, 결과 화면에서 홈으로 돌아갈 때의 전면 광고(30초 이상의 간격을 둠)입니다. 플레이 중에는 광고 SDK를 호출하지 않습니다.

- Google Mobile Ads SDK는 광고 게재, 효과 측정 및 부정 방지를 위해 IP 주소(대략적인 위치 추정에 사용됨), 기기 식별자(Android의 광고 ID·앱 세트 ID, iOS의 IDFV 등), 광고 조회·탭 등의 상호작용, 앱 실행 시간 등의 성능·진단 정보를 Google에 전송합니다. Google은 이를 Google의 정책(<https://policies.google.com/technologies/ads>)에 따라 처리합니다.
- EEA, 영국, 스위스 등 동의가 필요한 지역에서는 Google UMP의 동의 화면을 표시하고 이용자의 선택에 따릅니다. 선택은 설정 화면의 "광고 개인정보 설정"에서 변경할 수 있습니다. 그 밖의 지역에서는 기기 설정에 따라 맞춤형 광고가 표시될 수 있습니다.
- iOS에서 본 앱은 추적 허용(App Tracking Transparency)을 요청하지 않습니다. 따라서 IDFA는 사용되지 않습니다.
- 응원 팩(또는 이전의 "광고 제거")을 구매하면 광고가 더 이상 표시되지 않습니다.

#### 제10조 (인앱 결제)

응원 팩(3종의 1회 구매형 상품. 모두 광고 제거 포함)과 이전에 판매하던 "광고 제거"의 복원을 지원합니다.

- 결제는 Apple App Store(iOS) 또는 Google Play(Android)가 수행하며, 개발자는 신용카드 번호 등의 결제 정보를 받지 않습니다.
- 구매 확인 및 복원을 위해 스토어의 구매 정보를 참조합니다. 구매한 상품은 기기 내에 저장합니다.
- 제6조와 같이 Firebase Analytics가 인앱 결제 이벤트(상품 ID·가격)를 기록할 수 있습니다.

#### 제11조 (공유)

결과 화면에서 "공유"를 누르면 모드, 점수, 칭호, 스토어 URL이 담긴 문구와 결과 화면 이미지를 OS의 공유 화면에 전달합니다. 공유 대상은 이용자가 선택하며, 공유 대상에서의 처리는 각 서비스의 정책을 따릅니다. 개발자에게는 전송되지 않습니다.

#### 제12조 (제3자 제공)

개발자는 이용자의 정보를 판매하지 않습니다. 다음의 경우를 제외하고 제3자에게 제공하지 않습니다.

- 제9조의 Google AdMob: 광고 SDK가 수집한 정보를 Google이 자체 정책에 따라 광고 게재·측정·부정 방지에 사용합니다.
- 제3조의 공개 랭킹: 그 성질상 다른 이용자에게 표시됩니다.
- 업무 위탁: Google(Firebase / Google Cloud)에 개발자의 지시 범위 내에서 데이터의 처리와 보관을 맡깁니다. 결제는 Apple / Google이 수행합니다.
- 법령에 따른 경우.

#### 제13조 (아동의 이용)

본 앱은 만 13세 미만의 이용자를 대상으로 하지 않습니다. 보호자께서는 만 13세 미만 이용자의 설치·이용·결제를 관리해 주십시오. 만 13세 미만 이용자의 정보가 전송된 사실이 확인된 경우, 개발자는 이를 신속히 삭제합니다.

#### 제14조 (보관 기간)

| 데이터 | 보관 기간 |
| --- | --- |
| 일간 / 주간 랭킹 | 기간 종료 약 2일 후 자동 삭제(삭제 처리에 하루 정도 더 걸릴 수 있음) |
| 전체 기간 랭킹 | 서비스 제공 기간 중, 또는 삭제 요청 시까지 |
| 플레이 기록(제4조 (1)) | 부정행위 조사를 위해 서비스 제공 기간 중, 또는 삭제 요청 시까지 |
| 익명 로그인 계정 | 서비스 제공 기간 중, 또는 삭제 요청 시까지 |
| 이용 정지 기록 및 삭제한 기록의 사본 | 이용 정지를 해제할 때까지, 또는 불필요해질 때까지 |
| Firebase Analytics | Google 애널리틱스의 데이터 보관 설정에 따름(사용자 단위 데이터는 최대 14개월) |
| Firebase Crashlytics | Google이 정하는 기간(비정상 종료 데이터는 90일) |
| 기기 내 데이터 | 앱을 삭제할 때까지 |

#### 제15조 (데이터 보관 및 보안)

클라우드상의 데이터는 Google Cloud(Firebase / Firestore)에 보관되며, Firestore Security Rules와 App Check를 통해 접근이 제한됩니다. 통신은 모두 암호화(TLS)됩니다. 데이터는 이용자의 국가 밖에 있는 Google 서버에서 처리·보관될 수 있습니다.

#### 제16조 (이용자의 권리 및 데이터 삭제)

- **삭제 요청**: 클라우드 데이터(랭킹 기록, 플레이 기록, 익명 로그인 계정)의 삭제는 이메일(<support@haroworks.com>)로 신청해 주십시오. 제목에 "데이터 삭제 요청"이라고 쓰고, 플레이어 이름, 국가, 사용 중인 OS(iOS / Android), 대략적인 점수와 일시를 알려 주십시오. 익명 UID는 앱에 표시되지 않으므로, 이 정보를 바탕으로 기록을 특정합니다. 확인된 기록은 원칙적으로 30일 이내에 삭제하고 그 결과를 알려 드립니다.
- Firebase Analytics, Crashlytics, AdMob의 데이터는 이름 등과 연결되지 않는 식별자로 저장되므로, 개발자가 개인을 특정하여 삭제하지 못할 수 있습니다. 이러한 데이터는 제14조의 기간이 지나면 삭제됩니다.
- **기기 내 데이터**: 앱을 삭제하면 삭제됩니다.
- **표시 정보 변경**: 플레이어 이름, 국가, 언어는 설정 화면에서 언제든지 변경할 수 있습니다.
- **광고 설정**: 기기 설정(Android: 설정 > Google > 광고, iOS: 설정 > 개인정보 보호 및 보안)에서 광고 ID를 재설정하거나 맞춤형 광고를 중지할 수 있습니다. 동의가 필요한 지역에서는 설정 화면의 "광고 개인정보 설정"에서 동의를 변경할 수 있습니다.
- **각국 법령에 따른 권리**: EEA, 영국, 캘리포니아주 등의 이용자는 적용 법령에 따라 열람·정정·삭제·처리에 대한 이의 제기 등의 권리를 행사할 수 있습니다. 위 이메일로 연락해 주십시오. 개발자는 개인정보를 판매하지 않습니다.

#### 제17조 (준거법)

본 방침의 해석 및 적용은 일본국 법률에 따릅니다.

#### 제18조 (문의·본 방침의 변경)

본 방침에 관한 문의 및 삭제 요청은 아래로 연락해 주십시오.

- 이메일: <support@haroworks.com>

본 방침은 법령의 개정이나 앱의 변경에 맞추어 개정될 수 있습니다. 개정된 방침은 이 페이지에 게시된 시점부터 효력이 발생합니다. 중요한 변경은 앱의 릴리스 노트 등을 통해서도 알려 드립니다.

---

**개정 이력**

- v1.1 (2026-10-20): 버전 1.4에 맞추어 전면 개정. 부정행위 방지를 위한 정보(플레이 기록, 탭 통계, App Check, 이용 정지)를 추가. Analytics 이벤트, 광고의 종류와 광고 SDK가 수집하는 정보, 응원 팩, 공유 내용을 실제 동작에 맞게 수정하고, 보관 기간과 삭제 요청 방법을 명시. 클라우드에 저장하지 않았던 "업적"에 관한 기재를 삭제.
- v1.0 (2026-06-12): 최초 제정(v1.0.0 출시와 함께 시행).

---

<a id="es"></a>

## §F. Español (es)

> Esta traducción se proporciona solo como referencia. En caso de discrepancia entre esta traducción y la versión en japonés (§A) o en inglés (§B), prevalecerá la versión en japonés.

### Política de privacidad de Tap Champion

HaroWorks (el "Desarrollador"), proveedor de Tap Champion (la "App"), establece a continuación qué información trata la App, con qué finalidad, a dónde se envía y durante cuánto tiempo se conserva.

#### Artículo 1 (Ámbito de aplicación)

Esta Política se aplica a todos los usuarios de la aplicación móvil "Tap Champion" distribuida por el Desarrollador a través de Apple App Store y Google Play (iOS / Android, con un backend común). Las diferencias entre plataformas se indican en el texto.

#### Artículo 2 (Cuentas y autenticación anónima)

La App no le pide registrar su nombre, dirección de correo electrónico, número de teléfono ni información similar, y no dispone de registro de miembros ni de inicio de sesión con redes sociales.

- En el primer inicio, se emite automáticamente un identificador anónimo aleatorio (UID anónimo) mediante el **inicio de sesión anónimo** de Firebase Authentication. No se le asocia ningún nombre ni información de contacto.
- El UID anónimo se utiliza para distinguir los registros de la clasificación de cada usuario, para cotejar los registros de partida y para prevenir trampas (Artículo 4). No se muestra en la App.
- Durante el inicio de sesión anónimo, Firebase Authentication recibe la dirección IP de la conexión y el agente de usuario del dispositivo (tipo de sistema operativo y de SDK) para prevenir usos indebidos.

#### Artículo 3 (Información enviada a la clasificación — Cloud Firestore)

Cuando una partida termina con una puntuación de 1 o más y se han aceptado los registros de inicio y fin de la partida (Artículo 4), la App envía la siguiente información a la nube del Desarrollador (Google Cloud Firestore) y la almacena en las clasificaciones diaria, semanal y de todos los tiempos. Un registro solo se sobrescribe cuando usted supera su mejor marca.

| Elemento | Contenido | Visibilidad |
| --- | --- | --- |
| Nombre de jugador | Nombre visible de 1 a 12 caracteres que usted establece; por defecto, un nombre asignado automáticamente | Se muestra en la clasificación de la App |
| País | País que usted elige para la bandera (código de dos letras ISO 3166-1); por defecto, se estima a partir del idioma del dispositivo | Se muestra en la clasificación de la App |
| Puntuación, modo, período | Su mejor puntuación, el modo (A / AB / ABC / ABCD) y el período (diario / semanal / de todos los tiempos) | Se muestra en la clasificación de la App |
| Hora de actualización | Hora del servidor en que se escribió la puntuación | Se muestra en la clasificación de la App |
| UID anónimo | Identifica al titular del registro (se usa como ID del registro) | No se muestra en la App* |
| ID del registro de partida | ID aleatorio que se usa para cotejar el registro de partida del Artículo 4 | No se muestra en la App* |
| Estadísticas de toques | Los valores del Artículo 4 (2) | No se muestra en la App* |

\* Los registros de la clasificación se almacenan de forma que cualquiera puede leerlos a través de la App, por lo que los elementos que "no se muestran en la App" pueden, técnicamente, leerse fuera de la App. Ninguno de ellos contiene su nombre, datos de contacto ni información similar; son datos seudónimos.

**Sobre la clasificación pública**: su nombre de jugador, país, puntuación y hora de actualización se muestran a todos los demás usuarios como parte de la clasificación mundial. No utilice su nombre real ni otra información que permita identificarle personalmente como nombre de jugador. Puede cambiar su nombre de jugador y su país en cualquier momento en la pantalla de Ajustes; el cambio se reflejará en los registros que se escriban la próxima vez que supere su mejor marca.

Al consultar la clasificación, la App carga los primeros puestos y su propia posición. El juego en sí se puede jugar sin conexión.

#### Artículo 4 (Información enviada para prevenir trampas — a partir de la versión 1.4)

Para prevenir registros ilegítimos obtenidos con herramientas de toques automáticos, aceleradores de velocidad, manipulación de la memoria y métodos similares, la App utiliza la siguiente información. Como resultado de estas comprobaciones, un registro puede quedar excluido de la clasificación y, en casos graves, pueden bloquearse los envíos posteriores de ese UID anónimo (un "bloqueo").

1. **Registros de partida (hora del servidor)**: al iniciarse y al terminar una partida, la App escribe el modo, la hora de inicio, la hora de fin y la puntuación en un área de Firestore propia de cada usuario (una por UID anónimo). Todas las horas son del servidor y se utilizan para detectar partidas anormalmente largas o cortas y registros reutilizados. La App no puede leer esta área. Una partida que se inicia sin conexión no puede optar a la clasificación.
2. **Estadísticas de toques**: durante una partida, la App utiliza temporalmente en su dispositivo la hora, la posición en la pantalla, el número de dedo, la presión y el tamaño de contacto (si el dispositivo los admite) de cada toque para calcular los siguientes valores: el número de toques, el número de dedos utilizados, la variación de los intervalos entre toques, la variación de la posición de los toques por botón (en mm), el máximo de toques por segundo (en total y por dedo) y el número de combinaciones distintas de presión y tamaño de contacto. **No se envían la hora ni la posición de cada toque individual.** Solo se envían estos valores, con el registro de la clasificación (Artículo 3) y en el evento `tap_stats` de Firebase Analytics (junto con el modo y la puntuación, para fijar los umbrales de detección). Los datos brutos de los toques se descartan al terminar la partida.
3. **App Check (verificación de la App)**: se utiliza Firebase App Check para confirmar que las solicitudes proceden de la App auténtica en un dispositivo auténtico. Utiliza la API Google Play Integrity en Android y App Attest de Apple en iOS, y envía a Firebase tokens de certificación emitidos por Google / Apple. Los tokens caducan en poco tiempo, y el Desarrollador no recibe identificadores del dispositivo a partir de ellos.
4. **Registros de bloqueo**: para un UID anónimo bloqueado, se almacenan en Firestore el motivo, la fecha y hora y el número de registros eliminados, y el Desarrollador conserva una copia de los registros eliminados para poder revertir un bloqueo erróneo.

#### Artículo 5 (Datos almacenados solo en su dispositivo)

Los siguientes datos se almacenan en su dispositivo y no se envían fuera de él, salvo en los casos en que esta Política indica que se envían.

- Su mejor puntuación en cada modo, registros como el total de partidas y la mejor velocidad de toques, los modos desbloqueados y si ha visto el tutorial
- Perfil y ajustes (nombre de jugador, país, idioma, tema de color, volumen, ajustes de efectos, UID anónimo)
- Artículos comprados (packs de apoyo, eliminación de anuncios)
- Datos pendientes de envío a la clasificación (cuando falla el envío: puntuación, modo, período, ID del registro de partida, estadísticas de toques; se reenvían dentro de la hora siguiente al inicio de la partida y se eliminan tras enviarse)
- La imagen de la pantalla de resultados capturada para compartir (en la carpeta temporal del dispositivo)

Al desinstalar la App se eliminan los datos de su dispositivo. Como después se emite un nuevo UID anónimo, sus registros anteriores de la clasificación ya no podrán vincularse a usted.

#### Artículo 6 (Análisis de uso — Firebase Analytics)

La App utiliza Firebase Analytics de Google para mejorar sus funciones y ajustar los umbrales de detección de trampas. La App registra los siguientes eventos:

- `game_start` (modo) / `game_finish` (modo, puntuación) / `mode_select` / `mode_unlock` / `ranking_view` (modo, período) / `ad_view`
- `tutorial_step` / `tutorial_skip` (paso del tutorial)
- `tap_stats` (modo, puntuación y los valores del Artículo 4 (2))

Además, Firebase Analytics recopila automáticamente un ID de instancia de la aplicación, el modelo del dispositivo, las versiones del sistema operativo y de la App, el idioma, la ubicación aproximada estimada a partir de la dirección IP (a nivel de país, región y ciudad), los inicios de la App, las visualizaciones de pantalla y el tiempo de uso, las actualizaciones de la App, los eventos de compras dentro de la App (ID del producto y precio) y el identificador de publicidad (el ID de publicidad de Android; en iOS, la App no solicita permiso de rastreo, por lo que el IDFA no está disponible y en su lugar se recopila el IDFV). El Desarrollador utiliza estos datos para consultar estadísticas y no los utiliza para servir ni segmentar anuncios.

#### Artículo 7 (Informes de errores — Firebase Crashlytics)

La App utiliza Firebase Crashlytics para detectar y corregir defectos. Por ejemplo, cuando la App se bloquea, envía a Google el seguimiento de la pila, el estado de la App en ese momento, información del dispositivo como el modelo y el sistema operativo, y un ID de instalación de Crashlytics.

#### Artículo 8 (Configuración remota — Firebase Remote Config)

La App utiliza Firebase Remote Config para recibir valores de configuración operativa. Durante la obtención, el SDK envía el ID de instalación de Firebase, el país, el idioma, la zona horaria y la versión del sistema operativo.

#### Artículo 9 (Publicidad — Google AdMob / UMP)

Como la App es gratuita, muestra anuncios de Google AdMob: un banner en la parte inferior de la pantalla de inicio y un anuncio a pantalla completa al volver de la pantalla de resultados a la de inicio (con al menos 30 segundos de intervalo). El SDK de anuncios no se llama durante la partida.

- Para servir anuncios, medir su rendimiento y prevenir el fraude, el SDK de Google Mobile Ads envía a Google su dirección IP (que se utiliza para estimar la ubicación aproximada), identificadores del dispositivo (como el ID de publicidad y el ID de conjunto de aplicaciones de Android, o el IDFV de iOS), interacciones con los anuncios como visualizaciones y toques, e información de rendimiento y diagnóstico como el tiempo de inicio de la App. Google trata estos datos conforme a sus propias políticas (<https://policies.google.com/technologies/ads>).
- En las regiones en las que se requiere consentimiento, como el EEE, el Reino Unido y Suiza, la App muestra una pantalla de consentimiento de Google UMP y respeta sus elecciones. Puede cambiarlas desde "Privacidad de anuncios" en la pantalla de Ajustes. En otras regiones, pueden mostrarse anuncios personalizados según la configuración de su dispositivo.
- En iOS, la App no solicita permiso de rastreo (App Tracking Transparency), por lo que no se utiliza el IDFA.
- Al comprar un pack de apoyo (o el anterior "Eliminar anuncios"), los anuncios dejan de mostrarse.

#### Artículo 10 (Compras dentro de la App)

La App ofrece packs de apoyo (tres compras únicas, cada una de las cuales incluye la eliminación de anuncios) y permite restaurar el "Eliminar anuncios" que se vendía anteriormente.

- El pago lo procesa Apple App Store (iOS) o Google Play (Android); el Desarrollador no recibe datos de pago como números de tarjeta de crédito.
- La App consulta la información de compra de la tienda para verificar y restaurar las compras, y almacena los artículos comprados en su dispositivo.
- Como se indica en el Artículo 6, Firebase Analytics puede registrar eventos de compras dentro de la App (ID del producto y precio).

#### Artículo 11 (Compartir)

Al tocar "Compartir" en la pantalla de resultados, la App pasa a la hoja para compartir de su sistema operativo un texto con el modo, la puntuación, el título y la URL de la tienda, junto con una imagen de la pantalla de resultados. Usted elige el destino, y el tratamiento en él se rige por la política de ese servicio. No se envía nada al Desarrollador.

#### Artículo 12 (Comunicación a terceros)

El Desarrollador no vende su información y no la proporciona a terceros, salvo en los siguientes casos:

- Google AdMob (Artículo 9): Google utiliza la información recopilada por el SDK de anuncios conforme a sus propias políticas para servir y medir anuncios y para prevenir el fraude.
- La clasificación pública (Artículo 3): por su naturaleza, se muestra a otros usuarios.
- Proveedores de servicios: Google (Firebase / Google Cloud) trata y almacena los datos siguiendo las instrucciones del Desarrollador. Los pagos los gestionan Apple / Google.
- Cuando lo exija la ley.

#### Artículo 13 (Uso por menores)

La App no está dirigida a usuarios menores de 13 años. Los padres y tutores deben gestionar la instalación, el uso y las compras por parte de menores de 13 años. Si el Desarrollador tiene conocimiento de que se ha enviado información de un menor de 13 años, la eliminará sin demora.

#### Artículo 14 (Plazos de conservación)

| Datos | Conservación |
| --- | --- |
| Clasificaciones diaria / semanal | Se eliminan automáticamente unos 2 días después del final del período (la eliminación puede tardar hasta un día más aproximadamente) |
| Clasificación de todos los tiempos | Mientras se preste el servicio, o hasta que usted solicite su eliminación |
| Registros de partida (Artículo 4 (1)) | Se conservan para investigar trampas mientras se preste el servicio, o hasta que usted solicite su eliminación |
| Cuenta de inicio de sesión anónimo | Mientras se preste el servicio, o hasta que usted solicite su eliminación |
| Registros de bloqueo y copias de los registros eliminados | Hasta que se levante el bloqueo o dejen de ser necesarios |
| Firebase Analytics | Según la configuración de conservación de datos de Google Analytics (datos a nivel de usuario durante un máximo de 14 meses) |
| Firebase Crashlytics | Durante el período establecido por Google (datos de bloqueos: 90 días) |
| Datos en su dispositivo | Hasta que desinstale la App |

#### Artículo 15 (Almacenamiento y seguridad)

Los datos en la nube se almacenan en Google Cloud (Firebase / Firestore), y el acceso se restringe mediante las Firestore Security Rules y App Check. Todas las comunicaciones están cifradas (TLS). Los datos pueden tratarse y almacenarse en servidores de Google situados fuera de su país.

#### Artículo 16 (Sus derechos y eliminación de datos)

- **Solicitud de eliminación**: para eliminar sus datos en la nube (registros de la clasificación, registros de partida y la cuenta de inicio de sesión anónimo), envíenos un correo electrónico a <support@haroworks.com> con el asunto "Solicitud de eliminación de datos" e indíquenos su nombre de jugador, país, sistema operativo (iOS / Android) y la puntuación y fecha aproximadas. Como el UID anónimo no se muestra en la App, identificamos sus registros a partir de esta información. En principio, eliminaremos los registros que podamos confirmar en un plazo de 30 días y se lo comunicaremos.
- Los datos de Firebase Analytics, Crashlytics y AdMob se almacenan con identificadores que no están vinculados a su nombre ni a datos similares, por lo que es posible que el Desarrollador no pueda identificarlos y eliminarlos para una persona concreta. Se eliminan cuando vencen los plazos del Artículo 14.
- **Datos en su dispositivo**: se eliminan al desinstalar la App.
- **Cambio de la información mostrada**: puede cambiar su nombre de jugador, país e idioma en cualquier momento en la pantalla de Ajustes.
- **Configuración de anuncios**: en la configuración de su dispositivo (Android: Ajustes > Google > Anuncios; iOS: Ajustes > Privacidad y seguridad), puede restablecer el ID de publicidad o desactivar los anuncios personalizados. En las regiones en las que se requiere consentimiento, puede cambiar su consentimiento desde "Privacidad de anuncios" en la pantalla de Ajustes.
- **Derechos conforme a la legislación local**: los usuarios del EEE, el Reino Unido, California y otros lugares pueden ejercer derechos como el acceso, la rectificación, la supresión y la oposición conforme a la legislación aplicable. Póngase en contacto con nosotros en la dirección de correo electrónico indicada arriba. El Desarrollador no vende información personal.

#### Artículo 17 (Legislación aplicable)

Esta Política se interpretará y aplicará de conformidad con las leyes de Japón.

#### Artículo 18 (Contacto / Cambios en esta Política)

Para preguntas sobre esta Política o solicitudes de eliminación, póngase en contacto con:

- Correo electrónico: <support@haroworks.com>

El Desarrollador podrá revisar esta Política para reflejar cambios en la legislación o en la App. La Política revisada entra en vigor en el momento en que se publica en esta página. Los cambios importantes se comunicarán además en las notas de la versión de la App o por medios similares.

---

**Historial de revisiones**

- v1.1 (2026-10-20): Revisión completa para la versión 1.4. Se añadió la información utilizada para prevenir trampas (registros de partida, estadísticas de toques, App Check, bloqueos). Se actualizaron los eventos de Analytics, los formatos de anuncios y la información recopilada por el SDK de anuncios, los packs de apoyo y la función de compartir para que coincidan con el funcionamiento real de la App, y se indicaron los plazos de conservación y cómo solicitar la eliminación. Se eliminó la mención de los "logros" almacenados en la nube, algo que la App nunca hizo.
- v1.0 (2026-06-12): Versión inicial, en vigor con el lanzamiento de la v1.0.0.

---

<a id="fr"></a>

## §G. Français (fr)

> Cette traduction est fournie à titre indicatif uniquement. En cas de divergence entre cette traduction et la version japonaise (§A) ou anglaise (§B), la version japonaise prévaut.

### Politique de confidentialité de Tap Champion

HaroWorks (le « Développeur »), fournisseur de Tap Champion (l'« Application »), expose ci-dessous les informations traitées par l'Application, les finalités de ce traitement, leurs destinataires et leur durée de conservation.

#### Article 1 (Champ d'application)

La présente Politique s'applique à tous les utilisateurs de l'application mobile « Tap Champion » distribuée par le Développeur via l'Apple App Store et Google Play (iOS / Android, avec un backend commun). Les différences entre les plateformes sont signalées dans le texte.

#### Article 2 (Comptes et authentification anonyme)

L'Application ne vous demande pas d'enregistrer votre nom, votre adresse e-mail, votre numéro de téléphone ou d'autres informations similaires, et ne propose ni inscription de membre ni connexion via les réseaux sociaux.

- Au premier lancement, un identifiant anonyme aléatoire (UID anonyme) est émis automatiquement via la **connexion anonyme** de Firebase Authentication. Aucun nom ni aucune coordonnée n'y est associé.
- L'UID anonyme sert à distinguer les enregistrements de chaque utilisateur dans le classement, à rapprocher les relevés de partie et à prévenir la triche (article 4). Il n'est pas affiché dans l'Application.
- Lors de la connexion anonyme, Firebase Authentication reçoit l'adresse IP de la connexion et l'agent utilisateur de l'appareil (type de système d'exploitation et de SDK) afin de prévenir les abus.

#### Article 3 (Informations envoyées au classement — Cloud Firestore)

Lorsqu'une partie se termine avec un score d'au moins 1 et que les relevés de début et de fin de la partie (article 4) ont été acceptés, l'Application envoie les informations suivantes au cloud du Développeur (Google Cloud Firestore) et les enregistre dans les classements quotidien, hebdomadaire et de tous les temps. Un enregistrement n'est remplacé que lorsque vous battez votre meilleur score.

| Élément | Contenu | Visibilité |
| --- | --- | --- |
| Nom du joueur | Nom d'affichage de 1 à 12 caractères que vous définissez ; par défaut, un nom attribué automatiquement | Affiché dans le classement de l'Application |
| Pays | Pays que vous choisissez pour le drapeau (code ISO 3166-1 à deux lettres) ; par défaut, déduit de la langue de votre appareil | Affiché dans le classement de l'Application |
| Score, mode, période | Votre meilleur score, le mode (A / AB / ABC / ABCD) et la période (quotidien / hebdomadaire / de tous les temps) | Affiché dans le classement de l'Application |
| Heure de mise à jour | Heure du serveur à laquelle le score a été enregistré | Affiché dans le classement de l'Application |
| UID anonyme | Identifie le titulaire de l'enregistrement (utilisé comme identifiant de l'enregistrement) | Non affiché dans l'Application\* |
| Identifiant du relevé de partie | Identifiant aléatoire servant à rapprocher l'enregistrement du relevé de partie de l'article 4 | Non affiché dans l'Application\* |
| Statistiques de frappe | Les valeurs de l'article 4 (2) | Non affiché dans l'Application\* |

\* Les enregistrements du classement sont stockés de manière à pouvoir être lus par n'importe qui via l'Application ; les éléments « non affichés dans l'Application » peuvent donc, techniquement, être lus en dehors de l'Application. Aucun d'eux ne contient votre nom, vos coordonnées ou des informations similaires ; il s'agit d'informations pseudonymes.

**À propos du classement public** : votre nom de joueur, votre pays, votre score et l'heure de mise à jour sont affichés à tous les autres utilisateurs dans le cadre du classement mondial. N'utilisez pas votre vrai nom ni d'autres informations permettant de vous identifier personnellement comme nom de joueur. Vous pouvez modifier à tout moment votre nom de joueur et votre pays dans l'écran Réglages ; la modification apparaît dans les enregistrements écrits la prochaine fois que vous battez votre meilleur score.

Lorsque vous consultez le classement, l'Application charge les meilleurs enregistrements et votre propre rang. Le jeu lui-même peut être joué sans connexion.

#### Article 4 (Informations envoyées pour prévenir la triche — à partir de la version 1.4)

Afin d'empêcher les enregistrements illégitimes obtenus au moyen d'outils de frappe automatique, d'accélérateurs de vitesse (speed hacks), de modifications de la mémoire, etc., l'Application utilise les informations suivantes. À l'issue de ces vérifications, un enregistrement peut être exclu du classement et, dans les cas graves, les envois ultérieurs depuis l'UID anonyme concerné peuvent être bloqués (un « bannissement »).

1. **Relevés de partie (heure du serveur)** : au début et à la fin d'une partie, l'Application écrit le mode, l'heure de début, l'heure de fin et le score dans un espace de Firestore propre à chaque utilisateur (un par UID anonyme). Toutes les heures sont celles du serveur et servent à détecter les parties anormalement longues ou courtes ainsi que les enregistrements réutilisés. L'Application ne peut pas lire cet espace. Une partie commencée sans connexion n'est pas éligible au classement.
2. **Statistiques de frappe** : pendant une partie, l'Application utilise temporairement, sur votre appareil, l'heure, la position à l'écran, le numéro du doigt, la pression et la taille de la zone de contact (si l'appareil les prend en charge) de chaque frappe pour calculer les valeurs suivantes : le nombre de frappes, le nombre de doigts utilisés, la variation des intervalles entre les frappes, la variation de la position des frappes pour chaque bouton (en mm), le nombre maximal de frappes par seconde (au total et par doigt) et le nombre de combinaisons distinctes de pression et de taille de contact. **L'heure et la position de chaque frappe ne sont pas envoyées.** Seules ces valeurs sont envoyées, avec l'enregistrement du classement (article 3) et dans l'événement `tap_stats` de Firebase Analytics (avec le mode et le score, afin de fixer les seuils de détection). Les données brutes des frappes sont supprimées à la fin de la partie.
3. **App Check (vérification de l'Application)** : Firebase App Check sert à confirmer que les requêtes proviennent de l'Application authentique, exécutée sur un appareil authentique. Il utilise l'API Google Play Integrity sur Android et App Attest d'Apple sur iOS, et envoie à Firebase des jetons d'attestation émis par Google / Apple. Ces jetons expirent au bout d'un court délai, et le Développeur n'en tire aucun identifiant d'appareil.
4. **Enregistrements de bannissement** : pour un UID anonyme banni, le motif, la date et l'heure, ainsi que le nombre d'enregistrements supprimés sont conservés dans Firestore, et le Développeur conserve une copie des enregistrements supprimés afin de pouvoir annuler un bannissement prononcé par erreur.

#### Article 5 (Données stockées uniquement sur votre appareil)

Les données suivantes sont stockées sur votre appareil et n'en sont pas transmises, sauf dans les cas où la présente Politique prévoit leur envoi.

- Votre meilleur score pour chaque mode, des records tels que le nombre total de parties et la meilleure cadence de frappe, les modes débloqués et le fait que vous ayez vu ou non le tutoriel
- Profil et réglages (nom du joueur, pays, langue, thème de couleurs, volume, réglages des effets, UID anonyme)
- Articles achetés (packs de soutien, suppression des publicités)
- Données en attente d'envoi au classement (en cas d'échec de l'envoi : score, mode, période, identifiant du relevé de partie, statistiques de frappe ; renvoyées dans l'heure qui suit le début de la partie et supprimées après leur envoi)
- L'image de l'écran des résultats capturée pour le partage (dans le dossier temporaire de l'appareil)

La désinstallation de l'Application supprime les données présentes sur votre appareil. Un nouvel UID anonyme étant émis par la suite, vos enregistrements antérieurs dans le classement ne peuvent plus vous être rattachés.

#### Article 6 (Analyse d'utilisation — Firebase Analytics)

L'Application utilise Firebase Analytics de Google pour améliorer ses fonctionnalités et ajuster les seuils de détection de la triche. L'Application enregistre les événements suivants :

- `game_start` (mode) / `game_finish` (mode, score) / `mode_select` / `mode_unlock` / `ranking_view` (mode, période) / `ad_view`
- `tutorial_step` / `tutorial_skip` (étape du tutoriel)
- `tap_stats` (mode, score et valeurs de l'article 4 (2))

En outre, Firebase Analytics collecte automatiquement un identifiant d'instance d'application, le modèle de l'appareil, les versions du système d'exploitation et de l'Application, la langue, une localisation approximative estimée à partir de l'adresse IP (au niveau du pays, de la région et de la ville), les lancements de l'Application, les affichages d'écran et la durée d'utilisation, les mises à jour de l'Application, les événements d'achat intégré (identifiant du produit et prix) ainsi que l'identifiant publicitaire (l'identifiant publicitaire Android ; sur iOS, l'Application ne demande pas l'autorisation de suivi, de sorte que l'IDFA n'est pas disponible et que l'IDFV est collecté à la place). Le Développeur utilise ces données pour consulter des statistiques et ne les utilise pas pour diffuser ou cibler des publicités.

#### Article 7 (Rapports de plantage — Firebase Crashlytics)

L'Application utilise Firebase Crashlytics pour détecter et corriger les défauts. Lorsque l'Application plante, par exemple, elle envoie à Google la trace de la pile, l'état de l'Application à ce moment-là, des informations sur l'appareil telles que le modèle et le système d'exploitation, ainsi qu'un identifiant d'installation Crashlytics.

#### Article 8 (Configuration à distance — Firebase Remote Config)

L'Application utilise Firebase Remote Config pour recevoir des paramètres de fonctionnement. Lors de la récupération, le SDK envoie l'identifiant d'installation Firebase, le pays, la langue, le fuseau horaire et la version du système d'exploitation.

#### Article 9 (Publicité — Google AdMob / UMP)

L'Application étant gratuite, elle affiche des publicités de Google AdMob : une bannière en bas de l'écran d'accueil et une publicité plein écran lorsque vous revenez de l'écran des résultats à l'écran d'accueil (à au moins 30 secondes d'intervalle). Le SDK publicitaire n'est pas sollicité pendant les parties.

- Afin de diffuser des publicités, d'en mesurer les performances et de prévenir la fraude, le SDK Google Mobile Ads envoie à Google votre adresse IP (utilisée pour estimer votre localisation approximative), des identifiants d'appareil (tels que l'identifiant publicitaire Android et l'identifiant de groupe d'applications (app set ID), ou l'IDFV sur iOS), les interactions avec les publicités, telles que les affichages et les appuis, ainsi que des informations de performance et de diagnostic, telles que l'heure de lancement de l'Application. Google traite ces données conformément à ses propres règles (<https://policies.google.com/technologies/ads>).
- Dans les régions où un consentement est requis, comme l'EEE, le Royaume-Uni et la Suisse, l'Application affiche un écran de consentement Google UMP et respecte vos choix. Vous pouvez les modifier depuis « Confidentialité des publicités » dans l'écran Réglages. Dans les autres régions, des publicités personnalisées peuvent être diffusées selon les réglages de votre appareil.
- Sur iOS, l'Application ne demande pas l'autorisation de suivi (App Tracking Transparency) ; l'IDFA n'est donc pas utilisé.
- L'achat d'un pack de soutien (ou de l'ancien achat « Supprimer les publicités ») met fin à l'affichage des publicités.

#### Article 10 (Achats intégrés)

L'Application propose des packs de soutien (trois achats uniques, comprenant chacun la suppression des publicités) et permet de restaurer l'achat « Supprimer les publicités » vendu précédemment.

- Le paiement est traité par l'Apple App Store (iOS) ou Google Play (Android) ; le Développeur ne reçoit pas les données de paiement telles que les numéros de carte bancaire.
- L'Application consulte les informations d'achat de la boutique pour vérifier et restaurer les achats, et stocke les articles achetés sur votre appareil.
- Comme indiqué à l'article 6, Firebase Analytics peut enregistrer les événements d'achat intégré (identifiant du produit et prix).

#### Article 11 (Partage)

Lorsque vous appuyez sur « Partager » dans l'écran des résultats, l'Application transmet à la feuille de partage de votre système d'exploitation un texte indiquant le mode, le score, le titre obtenu et l'URL de la boutique, accompagné d'une image de l'écran des résultats. Vous choisissez la destination, et le traitement par celle-ci est régi par la politique du service concerné. Rien n'est envoyé au Développeur.

#### Article 12 (Communication à des tiers)

Le Développeur ne vend pas vos informations et ne les communique pas à des tiers, sauf dans les cas suivants :

- Google AdMob (article 9) : Google utilise les informations collectées par le SDK publicitaire, conformément à ses propres règles, pour diffuser et mesurer les publicités et prévenir la fraude.
- Le classement public (article 3) : par nature, il est affiché aux autres utilisateurs.
- Prestataires de services : Google (Firebase / Google Cloud) traite et stocke les données sur instruction du Développeur. Les paiements sont traités par Apple / Google.
- Lorsque la loi l'exige.

#### Article 13 (Utilisation par les enfants)

L'Application ne s'adresse pas aux utilisateurs de moins de 13 ans. Il incombe aux parents et tuteurs de gérer l'installation, l'utilisation et les achats effectués par les enfants de moins de 13 ans. Si le Développeur apprend que des informations concernant un enfant de moins de 13 ans ont été transmises, il les supprimera sans délai.

#### Article 14 (Durées de conservation)

| Données | Conservation |
| --- | --- |
| Classements quotidien / hebdomadaire | Supprimés automatiquement environ 2 jours après la fin de la période (la suppression peut prendre jusqu'à environ un jour de plus) |
| Classement de tous les temps | Pendant la durée de fourniture du service, ou jusqu'à ce que vous en demandiez la suppression |
| Relevés de partie (article 4 (1)) | Conservés pour les enquêtes sur la triche pendant la durée de fourniture du service, ou jusqu'à ce que vous en demandiez la suppression |
| Compte de connexion anonyme | Pendant la durée de fourniture du service, ou jusqu'à ce que vous en demandiez la suppression |
| Enregistrements de bannissement et copies des enregistrements supprimés | Jusqu'à la levée du bannissement ou jusqu'à ce qu'ils ne soient plus nécessaires |
| Firebase Analytics | Selon le paramètre de conservation des données de Google Analytics (données au niveau de l'utilisateur pendant 14 mois au maximum) |
| Firebase Crashlytics | Pendant la durée fixée par Google (données de plantage : 90 jours) |
| Données sur votre appareil | Jusqu'à la désinstallation de l'Application |

#### Article 15 (Stockage et sécurité)

Les données dans le cloud sont stockées dans Google Cloud (Firebase / Firestore), et leur accès est restreint par les Firestore Security Rules et App Check. Toutes les communications sont chiffrées (TLS). Les données peuvent être traitées et stockées sur des serveurs de Google situés en dehors de votre pays.

#### Article 16 (Vos droits et suppression des données)

- **Demande de suppression** : pour supprimer vos données dans le cloud (enregistrements du classement, relevés de partie et compte de connexion anonyme), écrivez-nous à <support@haroworks.com> avec l'objet « Demande de suppression de données », en indiquant votre nom de joueur, votre pays, votre système d'exploitation (iOS / Android) ainsi que votre score et la date approximatifs. L'UID anonyme n'étant pas affiché dans l'Application, nous identifions vos enregistrements à partir de ces informations. En principe, nous supprimons dans un délai de 30 jours les enregistrements que nous pouvons confirmer et vous en informons.
- Les données de Firebase Analytics, de Crashlytics et d'AdMob sont stockées sous des identifiants qui ne sont pas liés à votre nom ou à des informations similaires ; il se peut donc que le Développeur ne puisse pas les identifier ni les supprimer pour une personne donnée. Elles sont supprimées à l'expiration des durées prévues à l'article 14.
- **Données sur votre appareil** : supprimées lors de la désinstallation de l'Application.
- **Modification des informations affichées** : vous pouvez modifier à tout moment votre nom de joueur, votre pays et votre langue dans l'écran Réglages.
- **Réglages publicitaires** : dans les réglages de votre appareil (Android : Paramètres > Google > Annonces ; iOS : Réglages > Confidentialité et sécurité), vous pouvez réinitialiser l'identifiant publicitaire ou désactiver les publicités personnalisées. Dans les régions où un consentement est requis, vous pouvez modifier votre consentement depuis « Confidentialité des publicités » dans l'écran Réglages.
- **Droits prévus par les législations locales** : les utilisateurs de l'EEE, du Royaume-Uni, de Californie et d'ailleurs peuvent exercer des droits tels que l'accès, la rectification, l'effacement et l'opposition conformément à la loi applicable. Contactez-nous à l'adresse e-mail ci-dessus. Le Développeur ne vend pas d'informations personnelles.

#### Article 17 (Droit applicable)

La présente Politique est interprétée et appliquée conformément au droit japonais.

#### Article 18 (Contact / Modifications de la présente Politique)

Pour toute question concernant la présente Politique ou pour toute demande de suppression, veuillez contacter :

- E-mail : <support@haroworks.com>

Le Développeur peut réviser la présente Politique pour tenir compte de modifications de la législation ou de l'Application. Toute version révisée prend effet dès sa publication sur cette page. Les modifications importantes seront également annoncées dans les notes de version de l'Application ou par des moyens similaires.

---

**Historique des révisions**

- v1.1 (2026-10-20) : révision complète pour la version 1.4. Ajout des informations utilisées pour prévenir la triche (relevés de partie, statistiques de frappe, App Check, bannissements). Mise à jour des événements Analytics, des formats publicitaires et des informations collectées par le SDK publicitaire, des packs de soutien et du partage afin de refléter le fonctionnement réel de l'Application, et précision des durées de conservation et de la manière de demander la suppression. Suppression de la mention des « succès » stockés dans le cloud, ce que l'Application n'a jamais fait.
- v1.0 (2026-06-12) : version initiale, en vigueur à compter de la sortie de la v1.0.0.

---

<a id="de"></a>

## §H. Deutsch (de)

> Diese Übersetzung dient nur als Referenz. Bei Abweichungen zwischen dieser Übersetzung und der japanischen (§A) oder englischen (§B) Fassung ist die japanische Fassung maßgeblich.

### Datenschutzerklärung von Tap Champion

HaroWorks (der „Entwickler“), Anbieter von Tap Champion (die „App“), legt im Folgenden dar, welche Informationen die App verarbeitet, zu welchem Zweck, wohin sie übermittelt werden und wie lange sie gespeichert werden.

#### Artikel 1 (Geltungsbereich)

Diese Erklärung gilt für alle Nutzer der mobilen Anwendung „Tap Champion“, die der Entwickler über den Apple App Store und Google Play vertreibt (iOS / Android, mit gemeinsamem Backend). Unterschiede zwischen den Plattformen sind im Text vermerkt.

#### Artikel 2 (Konten und anonyme Authentifizierung)

Die App verlangt keine Registrierung Ihres Namens, Ihrer E-Mail-Adresse, Ihrer Telefonnummer oder ähnlicher Angaben und bietet weder eine Mitgliedsregistrierung noch eine Anmeldung über soziale Netzwerke.

- Beim ersten Start wird über die **anonyme Anmeldung** von Firebase Authentication automatisch eine zufällige anonyme Kennung (anonyme UID) vergeben. Mit ihr sind weder Name noch Kontaktdaten verknüpft.
- Die anonyme UID wird verwendet, um die Ranglisteneinträge der einzelnen Nutzer voneinander zu unterscheiden, Spielaufzeichnungen abzugleichen und Betrug zu verhindern (Artikel 4). Sie wird in der App nicht angezeigt.
- Bei der anonymen Anmeldung erhält Firebase Authentication zur Verhinderung von Missbrauch die IP-Adresse der Verbindung sowie den User-Agent des Geräts (Betriebssystem und SDK-Typ).

#### Artikel 3 (An die Rangliste übermittelte Informationen — Cloud Firestore)

Endet ein Spiel mit einer Punktzahl von 1 oder mehr und wurden die Start- und Endaufzeichnungen des Spiels (Artikel 4) akzeptiert, übermittelt die App die folgenden Informationen an die Cloud des Entwicklers (Google Cloud Firestore) und speichert sie in der täglichen, der wöchentlichen und der Allzeit-Rangliste. Ein Eintrag wird nur überschrieben, wenn Sie Ihre Bestleistung übertreffen.

| Element | Inhalt | Sichtbarkeit |
| --- | --- | --- |
| Spielername | Ein von Ihnen festgelegter Anzeigename mit 1–12 Zeichen; standardmäßig ein automatisch vergebener Name | Wird in der Rangliste der App angezeigt |
| Land | Ein von Ihnen gewähltes Land für die Flagge (zweistelliger Code nach ISO 3166-1); standardmäßig aus der Gerätesprache abgeleitet | Wird in der Rangliste der App angezeigt |
| Punktzahl, Modus, Zeitraum | Ihre Bestpunktzahl, der Modus (A / AB / ABC / ABCD) und der Zeitraum (täglich / wöchentlich / Allzeit) | Wird in der Rangliste der App angezeigt |
| Aktualisierungszeit | Die Serverzeit, zu der die Punktzahl geschrieben wurde | Wird in der Rangliste der App angezeigt |
| Anonyme UID | Kennzeichnet den Inhaber des Eintrags (dient als ID des Eintrags) | Wird in der App nicht angezeigt* |
| ID der Spielaufzeichnung | Eine zufällige ID zum Abgleich mit der Spielaufzeichnung nach Artikel 4 | Wird in der App nicht angezeigt* |
| Tipp-Statistiken | Die Werte nach Artikel 4 (2) | Wird in der App nicht angezeigt* |

\* Ranglisteneinträge werden so gespeichert, dass jeder sie über die App lesen kann. Daher können auch Elemente, die „in der App nicht angezeigt“ werden, technisch gesehen außerhalb der App lesbar sein. Keines davon enthält Ihren Namen, Ihre Kontaktdaten oder Ähnliches; es handelt sich um pseudonyme Informationen.

**Zur öffentlichen Rangliste**: Ihr Spielername, Ihr Land, Ihre Punktzahl und die Aktualisierungszeit werden als Teil der Weltrangliste allen anderen Nutzern angezeigt. Verwenden Sie nicht Ihren echten Namen oder andere Informationen, die Sie persönlich identifizieren, als Spielernamen. Sie können Spielernamen und Land jederzeit im Einstellungsbildschirm ändern; die Änderung erscheint in den Einträgen, die beim nächsten Übertreffen Ihrer Bestleistung geschrieben werden.

Wenn Sie die Rangliste ansehen, lädt die App die bestplatzierten Einträge und Ihren eigenen Rang. Das Spiel selbst kann ohne Verbindung gespielt werden.

#### Artikel 4 (Zur Verhinderung von Betrug übermittelte Informationen — ab Version 1.4)

Um unzulässige Einträge zu verhindern, die mit automatischen Tipp-Werkzeugen, Geschwindigkeitsmanipulationen, Speichermanipulationen oder Ähnlichem erzielt werden, verwendet die App die folgenden Informationen. Als Ergebnis dieser Prüfungen kann ein Eintrag von der Rangliste ausgeschlossen werden; in schwerwiegenden Fällen können weitere Übermittlungen von dieser anonymen UID gesperrt werden (eine „Sperre“).

1. **Spielaufzeichnungen (Serverzeit)**: Zu Beginn und am Ende eines Spiels schreibt die App den Modus, die Startzeit, die Endzeit und die Punktzahl in einen nutzerbezogenen Bereich von Firestore (einen pro anonymer UID). Alle Zeiten sind Serverzeiten und dienen dazu, Spiele mit unnatürlich langer oder kurzer Dauer sowie wiederverwendete Einträge zu erkennen. Die App kann diesen Bereich nicht lesen. Ein Spiel, das ohne Verbindung beginnt, kommt für die Rangliste nicht in Betracht.
2. **Tipp-Statistiken**: Während eines Spiels verwendet die App auf Ihrem Gerät vorübergehend Zeitpunkt, Bildschirmposition, Fingernummer, Druck und Kontaktgröße (sofern das Gerät dies unterstützt) jedes Tippens, um die folgenden Werte zu berechnen: die Anzahl der Tipps, die Anzahl der verwendeten Finger, die Streuung der Tippabstände, die Streuung der Tipppositionen je Schaltfläche (in mm), die maximale Anzahl an Tipps pro Sekunde (insgesamt und je Finger) sowie die Anzahl unterschiedlicher Kombinationen aus Druck und Kontaktgröße. **Zeitpunkt und Position einzelner Tipps werden nicht übermittelt.** Nur diese Werte werden übermittelt, und zwar mit dem Ranglisteneintrag (Artikel 3) und im Firebase-Analytics-Ereignis `tap_stats` (zusammen mit Modus und Punktzahl, um die Schwellenwerte für die Erkennung festzulegen). Die Rohdaten der Tipps werden nach dem Ende des Spiels verworfen.
3. **App Check (Überprüfung der App)**: Mit Firebase App Check wird bestätigt, dass Anfragen von der echten App auf einem echten Gerät stammen. Dabei werden unter Android die Google Play Integrity API und unter iOS App Attest von Apple verwendet, und von Google / Apple ausgestellte Bestätigungstoken werden an Firebase gesendet. Die Token verfallen nach kurzer Zeit, und der Entwickler erhält daraus keine Gerätekennungen.
4. **Sperraufzeichnungen**: Für eine gesperrte anonyme UID werden der Grund, Datum und Uhrzeit sowie die Anzahl der entfernten Einträge in Firestore gespeichert, und der Entwickler bewahrt eine Kopie der entfernten Einträge auf, damit eine irrtümliche Sperre rückgängig gemacht werden kann.

#### Artikel 5 (Nur auf Ihrem Gerät gespeicherte Daten)

Die folgenden Daten werden auf Ihrem Gerät gespeichert und nicht von ihm übertragen, außer soweit diese Erklärung eine Übermittlung vorsieht.

- Ihre Bestpunktzahl pro Modus, Aufzeichnungen wie die Gesamtzahl der Spiele und die beste Tipprate, freigeschaltete Modi sowie die Angabe, ob Sie das Tutorial gesehen haben
- Profil und Einstellungen (Spielername, Land, Sprache, Farbthema, Lautstärke, Effekteinstellungen, anonyme UID)
- Gekaufte Artikel (Unterstützerpakete, Werbeentfernung)
- Daten, die auf die Übermittlung an die Rangliste warten (wenn die Übermittlung fehlschlägt: Punktzahl, Modus, Zeitraum, ID der Spielaufzeichnung, Tipp-Statistiken; sie werden innerhalb einer Stunde nach Beginn des Spiels erneut gesendet und nach dem Senden gelöscht)
- Das zum Teilen aufgenommene Bild des Ergebnisbildschirms (im temporären Ordner des Geräts)

Durch die Deinstallation der App werden die Daten auf Ihrem Gerät gelöscht. Da danach eine neue anonyme UID vergeben wird, können Ihre früheren Ranglisteneinträge nicht mehr mit Ihnen verknüpft werden.

#### Artikel 6 (Nutzungsanalyse — Firebase Analytics)

Die App verwendet Firebase Analytics von Google, um ihre Funktionen zu verbessern und die Schwellenwerte für die Betrugserkennung abzustimmen. Die App erfasst die folgenden Ereignisse:

- `game_start` (Modus) / `game_finish` (Modus, Punktzahl) / `mode_select` / `mode_unlock` / `ranking_view` (Modus, Zeitraum) / `ad_view`
- `tutorial_step` / `tutorial_skip` (Tutorial-Schritt)
- `tap_stats` (Modus, Punktzahl und die Werte nach Artikel 4 (2))

Darüber hinaus erfasst Firebase Analytics automatisch eine App-Instanz-ID, das Gerätemodell, die Betriebssystem- und App-Version, die Sprache, den anhand der IP-Adresse geschätzten ungefähren Standort (auf Ebene von Land, Region und Stadt), App-Starts, Bildschirmaufrufe und Nutzungsdauer, App-Aktualisierungen, In-App-Kauf-Ereignisse (Produkt-ID und Preis) sowie die Werbe-ID (die Android-Werbe-ID; unter iOS fragt die App nicht nach der Tracking-Erlaubnis, daher ist die IDFA nicht verfügbar, und stattdessen wird die IDFV erfasst). Der Entwickler verwendet diese Daten zur Ansicht von Statistiken und nicht zur Auslieferung oder Ausrichtung von Werbung.

#### Artikel 7 (Absturzberichte — Firebase Crashlytics)

Die App verwendet Firebase Crashlytics, um Fehler zu finden und zu beheben. Wenn die App beispielsweise abstürzt, sendet sie den Stacktrace, den Zustand der App zu diesem Zeitpunkt, Geräteinformationen wie Modell und Betriebssystem sowie eine Crashlytics-Installations-ID an Google.

#### Artikel 8 (Remote-Konfiguration — Firebase Remote Config)

Die App verwendet Firebase Remote Config, um Betriebseinstellungen zu empfangen. Beim Abruf sendet das SDK die Firebase-Installations-ID, das Land, die Sprache, die Zeitzone und die Betriebssystemversion.

#### Artikel 9 (Werbung — Google AdMob / UMP)

Da die App kostenlos angeboten wird, zeigt sie Werbung von Google AdMob an: ein Banner am unteren Rand des Startbildschirms sowie eine Vollbildanzeige, wenn Sie vom Ergebnisbildschirm zum Startbildschirm zurückkehren (im Abstand von mindestens 30 Sekunden). Während des Spiels wird das Werbe-SDK nicht aufgerufen.

- Zur Auslieferung von Werbung, zur Messung ihrer Wirkung und zur Betrugsverhinderung sendet das Google Mobile Ads SDK Ihre IP-Adresse (zur Schätzung des ungefähren Standorts verwendet), Gerätekennungen (etwa die Android-Werbe-ID und die App-Set-ID oder die iOS-IDFV), Interaktionen mit Anzeigen wie Aufrufe und Tipps sowie Leistungs- und Diagnoseinformationen wie die App-Startzeit an Google. Google verarbeitet diese Daten nach seinen eigenen Richtlinien (<https://policies.google.com/technologies/ads>).
- In Regionen, in denen eine Einwilligung erforderlich ist, etwa im EWR, im Vereinigten Königreich und in der Schweiz, zeigt die App einen Einwilligungsbildschirm von Google UMP an und richtet sich nach Ihrer Auswahl. Sie können diese über „Anzeigen-Datenschutz“ im Einstellungsbildschirm ändern. In anderen Regionen kann je nach Ihren Geräteeinstellungen personalisierte Werbung angezeigt werden.
- Unter iOS fragt die App nicht nach der Tracking-Erlaubnis (App Tracking Transparency), daher wird die IDFA nicht verwendet.
- Mit dem Kauf eines Unterstützerpakets (oder des früheren „Werbung entfernen“) wird keine Werbung mehr angezeigt.

#### Artikel 10 (In-App-Käufe)

Die App bietet Unterstützerpakete an (drei Einmalkäufe, jeweils einschließlich Werbeentfernung) und stellt das früher verkaufte „Werbung entfernen“ wieder her.

- Die Zahlung wird über den Apple App Store (iOS) oder Google Play (Android) abgewickelt; der Entwickler erhält keine Zahlungsdaten wie Kreditkartennummern.
- Zur Überprüfung und Wiederherstellung von Käufen greift die App auf die Kaufinformationen des Stores zurück und speichert gekaufte Artikel auf Ihrem Gerät.
- Wie in Artikel 6 angegeben, kann Firebase Analytics In-App-Kauf-Ereignisse (Produkt-ID und Preis) erfassen.

#### Artikel 11 (Teilen)

Wenn Sie auf dem Ergebnisbildschirm auf „Teilen“ tippen, übergibt die App einen Text mit Modus, Punktzahl, Titel und Store-URL zusammen mit einem Bild des Ergebnisbildschirms an das Teilen-Menü Ihres Betriebssystems. Sie wählen das Ziel, und die Verarbeitung dort richtet sich nach der Richtlinie des jeweiligen Dienstes. An den Entwickler wird nichts gesendet.

#### Artikel 12 (Weitergabe an Dritte)

Der Entwickler verkauft Ihre Informationen nicht und gibt sie nicht an Dritte weiter, außer in den folgenden Fällen:

- Google AdMob (Artikel 9): Google verwendet die vom Werbe-SDK erfassten Informationen nach seinen eigenen Richtlinien zur Auslieferung und Messung von Werbung sowie zur Betrugsverhinderung.
- Die öffentliche Rangliste (Artikel 3): Sie wird naturgemäß anderen Nutzern angezeigt.
- Dienstleister: Google (Firebase / Google Cloud) verarbeitet und speichert Daten im Auftrag und nach Weisung des Entwicklers. Zahlungen werden von Apple / Google abgewickelt.
- Soweit dies gesetzlich vorgeschrieben ist.

#### Artikel 13 (Nutzung durch Kinder)

Die App richtet sich nicht an Nutzer unter 13 Jahren. Eltern und Erziehungsberechtigte sollten die Installation, Nutzung und Käufe durch Kinder unter 13 Jahren überwachen. Erlangt der Entwickler Kenntnis davon, dass Informationen eines Kindes unter 13 Jahren übermittelt wurden, löscht er diese unverzüglich.

#### Artikel 14 (Speicherdauer)

| Daten | Speicherdauer |
| --- | --- |
| Tägliche / wöchentliche Rangliste | Automatische Löschung etwa 2 Tage nach Ende des Zeitraums (die Löschung kann bis zu etwa einen weiteren Tag dauern) |
| Allzeit-Rangliste | Solange der Dienst angeboten wird oder bis Sie die Löschung beantragen |
| Spielaufzeichnungen (Artikel 4 (1)) | Zur Untersuchung von Betrug aufbewahrt, solange der Dienst angeboten wird oder bis Sie die Löschung beantragen |
| Konto der anonymen Anmeldung | Solange der Dienst angeboten wird oder bis Sie die Löschung beantragen |
| Sperraufzeichnungen und Kopien entfernter Einträge | Bis die Sperre aufgehoben wird oder sie nicht mehr benötigt werden |
| Firebase Analytics | Gemäß der Einstellung zur Datenaufbewahrung in Google Analytics (Daten auf Nutzerebene bis zu 14 Monate) |
| Firebase Crashlytics | Für den von Google festgelegten Zeitraum (Absturzdaten: 90 Tage) |
| Daten auf Ihrem Gerät | Bis Sie die App deinstallieren |

#### Artikel 15 (Speicherung und Sicherheit)

Cloud-Daten werden in Google Cloud (Firebase / Firestore) gespeichert, und der Zugriff wird durch Firestore Security Rules und App Check beschränkt. Die gesamte Kommunikation ist verschlüsselt (TLS). Daten können auf Servern von Google außerhalb Ihres Landes verarbeitet und gespeichert werden.

#### Artikel 16 (Ihre Rechte und Datenlöschung)

- **Löschantrag**: Um Ihre Cloud-Daten (Ranglisteneinträge, Spielaufzeichnungen und das Konto der anonymen Anmeldung) löschen zu lassen, senden Sie uns eine E-Mail an <support@haroworks.com> mit dem Betreff „Antrag auf Datenlöschung“ und teilen Sie uns Ihren Spielernamen, Ihr Land, Ihr Betriebssystem (iOS / Android) sowie die ungefähre Punktzahl und das ungefähre Datum mit. Da die anonyme UID in der App nicht angezeigt wird, ermitteln wir Ihre Einträge anhand dieser Angaben. Die Einträge, die wir bestätigen können, löschen wir grundsätzlich innerhalb von 30 Tagen und benachrichtigen Sie darüber.
- Daten von Firebase Analytics, Crashlytics und AdMob werden unter Kennungen gespeichert, die nicht mit Ihrem Namen oder ähnlichen Angaben verknüpft sind. Daher kann der Entwickler sie möglicherweise keiner einzelnen Person zuordnen und löschen. Sie werden nach Ablauf der in Artikel 14 genannten Fristen gelöscht.
- **Daten auf Ihrem Gerät**: Werden durch die Deinstallation der App gelöscht.
- **Änderung der angezeigten Informationen**: Sie können Ihren Spielernamen, Ihr Land und Ihre Sprache jederzeit im Einstellungsbildschirm ändern.
- **Werbeeinstellungen**: In den Einstellungen Ihres Geräts (Android: Einstellungen > Google > Anzeigen; iOS: Einstellungen > Datenschutz & Sicherheit) können Sie die Werbe-ID zurücksetzen oder personalisierte Werbung deaktivieren. In Regionen, in denen eine Einwilligung erforderlich ist, können Sie Ihre Einwilligung über „Anzeigen-Datenschutz“ im Einstellungsbildschirm ändern.
- **Rechte nach örtlichem Recht**: Nutzer im EWR, im Vereinigten Königreich, in Kalifornien und anderswo können nach geltendem Recht Rechte wie Auskunft, Berichtigung, Löschung und Widerspruch ausüben. Bitte kontaktieren Sie uns unter der oben genannten E-Mail-Adresse. Der Entwickler verkauft keine personenbezogenen Daten.

#### Artikel 17 (Anwendbares Recht)

Diese Erklärung wird nach japanischem Recht ausgelegt und angewendet.

#### Artikel 18 (Kontakt / Änderungen dieser Erklärung)

Bei Fragen zu dieser Erklärung oder für Löschanträge wenden Sie sich bitte an:

- E-Mail: <support@haroworks.com>

Der Entwickler kann diese Erklärung überarbeiten, um Änderungen des geltenden Rechts oder der App Rechnung zu tragen. Eine überarbeitete Erklärung tritt in Kraft, sobald sie auf dieser Seite veröffentlicht ist. Wesentliche Änderungen werden zusätzlich in den Versionshinweisen der App oder auf ähnliche Weise mitgeteilt.

---

**Änderungshistorie**

- v1.1 (2026-10-20): Vollständige Überarbeitung für Version 1.4. Die zur Betrugsverhinderung verwendeten Informationen (Spielaufzeichnungen, Tipp-Statistiken, App Check, Sperren) wurden ergänzt. Die Analytics-Ereignisse, die Werbeformate und die vom Werbe-SDK erfassten Informationen, die Unterstützerpakete sowie das Teilen wurden an die tatsächliche Funktionsweise der App angepasst, und Speicherdauern sowie das Verfahren für Löschanträge wurden angegeben. Der Hinweis auf in der Cloud gespeicherte „Erfolge“, die die App nie gespeichert hat, wurde entfernt.
- v1.0 (2026-06-12): Erstfassung, in Kraft mit der Veröffentlichung von v1.0.0.

---

<a id="pt"></a>

## §I. Português (pt)

> Esta tradução é fornecida apenas para referência. Em caso de divergência entre esta tradução e a versão em japonês (§A) ou em inglês (§B), prevalecerá a versão em japonês.

### Política de Privacidade do Tap Champion

A HaroWorks (o "Desenvolvedor"), fornecedora do Tap Champion (o "App"), descreve abaixo quais informações o App trata, para quê, para onde são enviadas e por quanto tempo são mantidas.

#### Artigo 1 (Âmbito)

Esta Política se aplica a todos os usuários do aplicativo móvel "Tap Champion" distribuído pelo Desenvolvedor na Apple App Store e no Google Play (iOS / Android, com um backend comum). As diferenças entre as plataformas são indicadas no texto.

#### Artigo 2 (Contas e autenticação anônima)

O App não pede que você cadastre seu nome, endereço de e-mail, número de telefone ou informações semelhantes, e não possui cadastro de membros nem login por redes sociais.

- Na primeira execução, um identificador anônimo aleatório (UID anônimo) é emitido automaticamente por meio do **login anônimo** do Firebase Authentication. Nenhum nome ou informação de contato é associado a ele.
- O UID anônimo é usado para distinguir os registros de cada usuário no ranking, para conferir os registros de partida e para prevenir trapaças (Artigo 4). Ele não é exibido no App.
- Durante o login anônimo, o Firebase Authentication recebe o endereço IP da conexão e o agente de usuário do dispositivo (tipo de sistema operacional e de SDK) para prevenir abusos.

#### Artigo 3 (Informações enviadas ao ranking — Cloud Firestore)

Quando uma partida termina com pontuação de 1 ou mais e os registros de início e fim da partida (Artigo 4) são aceitos, o App envia as seguintes informações à nuvem do Desenvolvedor (Google Cloud Firestore) e as armazena nos rankings diário, semanal e de todos os tempos. Um registro só é substituído quando você supera sua melhor pontuação.

| Item | Conteúdo | Visibilidade |
| --- | --- | --- |
| Nome do jogador | Nome de exibição de 1 a 12 caracteres definido por você; por padrão, um nome atribuído automaticamente | Exibido no ranking do App |
| País | País que você escolhe para a bandeira (código de duas letras da ISO 3166-1); por padrão, estimado a partir do idioma do dispositivo | Exibido no ranking do App |
| Pontuação, modo, período | Sua melhor pontuação, o modo (A / AB / ABC / ABCD) e o período (diário / semanal / de todos os tempos) | Exibido no ranking do App |
| Horário de atualização | Horário do servidor em que a pontuação foi gravada | Exibido no ranking do App |
| UID anônimo | Identifica o titular do registro (usado como ID do registro) | Não exibido no App* |
| ID do registro de partida | ID aleatório usado para conferir o registro de partida do Artigo 4 | Não exibido no App* |
| Estatísticas de toques | Os valores do Artigo 4 (2) | Não exibido no App* |

\* Os registros do ranking são armazenados de forma que qualquer pessoa possa lê-los por meio do App; por isso, os itens "não exibidos no App" podem, tecnicamente, ser lidos fora do App. Nenhum deles contém seu nome, dados de contato ou similares; são informações pseudônimas.

**Sobre o ranking público**: seu nome de jogador, país, pontuação e horário de atualização são exibidos a todos os outros usuários como parte do ranking mundial. Não use seu nome real nem outras informações que permitam identificá-lo pessoalmente como nome de jogador. Você pode alterar seu nome de jogador e seu país a qualquer momento na tela de Ajustes; a alteração aparece nos registros gravados na próxima vez que você superar sua melhor pontuação.

Ao visualizar o ranking, o App carrega os primeiros registros e a sua própria posição. O jogo em si pode ser jogado sem conexão.

#### Artigo 4 (Informações enviadas para prevenir trapaças — a partir da versão 1.4)

Para prevenir registros ilegítimos feitos com ferramentas de toque automático, aceleradores de velocidade (speed hacks), adulteração de memória e práticas semelhantes, o App usa as informações a seguir. Como resultado dessas verificações, um registro pode ser excluído do ranking e, em casos graves, novos envios desse UID anônimo podem ser bloqueados (um "banimento").

1. **Registros de partida (horário do servidor)**: quando uma partida começa e termina, o App grava o modo, o horário de início, o horário de término e a pontuação em uma área do Firestore separada por usuário (uma por UID anônimo). Todos os horários são do servidor e são usados para detectar partidas de duração anormalmente longa ou curta e registros reutilizados. O App não consegue ler essa área. Uma partida iniciada sem conexão não é elegível para o ranking.
2. **Estatísticas de toques**: durante a partida, o App usa temporariamente, no seu dispositivo, o horário, a posição na tela, o número do dedo, a pressão e o tamanho do contato (quando o dispositivo os suporta) de cada toque para calcular os seguintes valores: o número de toques, o número de dedos usados, a variação dos intervalos entre toques, a variação das posições de toque em cada botão (em mm), o máximo de toques por segundo (no total e por dedo) e o número de combinações distintas de pressão e tamanho de contato. **O horário e a posição de cada toque individual não são enviados.** Somente esses valores são enviados, junto com o registro do ranking (Artigo 3) e no evento `tap_stats` do Firebase Analytics (junto com o modo e a pontuação, para definir os limites de detecção). Os dados brutos dos toques são descartados após o fim da partida.
3. **App Check (verificação do App)**: o Firebase App Check é usado para confirmar que as solicitações vêm do App genuíno em um dispositivo genuíno. Ele usa a Google Play Integrity API no Android e o App Attest da Apple no iOS, e envia ao Firebase tokens de atestado emitidos pelo Google / pela Apple. Os tokens expiram em pouco tempo, e o Desenvolvedor não recebe identificadores do dispositivo por meio deles.
4. **Registros de banimento**: para um UID anônimo banido, o motivo, a data e hora e o número de registros removidos são armazenados no Firestore, e o Desenvolvedor mantém uma cópia dos registros removidos para que um banimento equivocado possa ser revertido.

#### Artigo 5 (Dados armazenados somente no seu dispositivo)

Os dados a seguir são armazenados no seu dispositivo e não são enviados para fora dele, exceto quando esta Política indica que são enviados.

- Sua melhor pontuação em cada modo, registros como o total de partidas e a melhor taxa de toques, os modos desbloqueados e se você já viu o tutorial
- Perfil e configurações (nome do jogador, país, idioma, tema de cores, volume, configurações de efeitos, UID anônimo)
- Itens comprados (pacotes de apoio, remoção de anúncios)
- Dados aguardando envio ao ranking (quando o envio falha: pontuação, modo, período, ID do registro de partida, estatísticas de toques; reenviados em até uma hora após o início da partida e excluídos após o envio)
- A imagem da tela de resultados capturada para compartilhamento (na pasta temporária do dispositivo)

Desinstalar o App exclui os dados do seu dispositivo. Como um novo UID anônimo é emitido depois disso, seus registros anteriores no ranking deixam de poder ser vinculados a você.

#### Artigo 6 (Análise de uso — Firebase Analytics)

O App usa o Firebase Analytics do Google para melhorar seus recursos e ajustar os limites de detecção de trapaças. O App registra os seguintes eventos:

- `game_start` (modo) / `game_finish` (modo, pontuação) / `mode_select` / `mode_unlock` / `ranking_view` (modo, período) / `ad_view`
- `tutorial_step` / `tutorial_skip` (etapa do tutorial)
- `tap_stats` (modo, pontuação e os valores do Artigo 4 (2))

Além disso, o Firebase Analytics coleta automaticamente um ID de instância do app, o modelo do dispositivo, as versões do sistema operacional e do App, o idioma, a localização aproximada estimada a partir do endereço IP (em nível de país, região e cidade), as inicializações do App, as visualizações de tela e o tempo de uso, as atualizações do App, os eventos de compra no App (ID do produto e preço) e o ID de publicidade (o ID de publicidade do Android; no iOS, o App não pede permissão de rastreamento, portanto o IDFA não está disponível e, em seu lugar, é coletado o IDFV). O Desenvolvedor usa esses dados para consultar estatísticas e não os usa para veicular ou direcionar anúncios.

#### Artigo 7 (Relatórios de falhas — Firebase Crashlytics)

O App usa o Firebase Crashlytics para encontrar e corrigir defeitos. Quando o App falha, por exemplo, ele envia ao Google o rastreamento de pilha, o estado do App naquele momento, informações do dispositivo, como modelo e sistema operacional, e um ID de instalação do Crashlytics.

#### Artigo 8 (Configuração remota — Firebase Remote Config)

O App usa o Firebase Remote Config para receber configurações operacionais. Ao fazer a obtenção, o SDK envia o ID de instalação do Firebase, o país, o idioma, o fuso horário e a versão do sistema operacional.

#### Artigo 9 (Publicidade — Google AdMob / UMP)

Como o App é gratuito, ele exibe anúncios do Google AdMob: um banner na parte inferior da tela inicial e um anúncio em tela cheia quando você volta da tela de resultados para a tela inicial (com intervalo de pelo menos 30 segundos). O SDK de anúncios não é acionado durante a partida.

- Para veicular anúncios, medir seu desempenho e prevenir fraudes, o Google Mobile Ads SDK envia ao Google seu endereço IP (usado para estimar a localização aproximada), identificadores do dispositivo (como o ID de publicidade e o ID do conjunto de apps no Android, ou o IDFV no iOS), interações com anúncios, como visualizações e toques, e informações de desempenho e diagnóstico, como o tempo de inicialização do App. O Google trata esses dados de acordo com suas próprias políticas (<https://policies.google.com/technologies/ads>).
- Em regiões onde o consentimento é exigido, como o EEE, o Reino Unido e a Suíça, o App exibe uma tela de consentimento do Google UMP e segue suas escolhas. Você pode alterá-las em "Privacidade de anúncios", na tela de Ajustes. Em outras regiões, anúncios personalizados podem ser exibidos conforme as configurações do seu dispositivo.
- No iOS, o App não pede permissão de rastreamento (App Tracking Transparency), portanto o IDFA não é usado.
- A compra de um pacote de apoio (ou do antigo "Remover anúncios") faz com que os anúncios deixem de ser exibidos.

#### Artigo 10 (Compras no App)

O App oferece pacotes de apoio (três compras únicas, cada uma incluindo a remoção de anúncios) e permite restaurar o "Remover anúncios" vendido anteriormente.

- O pagamento é processado pela Apple App Store (iOS) ou pelo Google Play (Android); o Desenvolvedor não recebe dados de pagamento, como números de cartão de crédito.
- O App consulta as informações de compra da loja para verificar e restaurar compras, e armazena os itens comprados no seu dispositivo.
- Conforme o Artigo 6, o Firebase Analytics pode registrar eventos de compra no App (ID do produto e preço).

#### Artigo 11 (Compartilhamento)

Quando você toca em "Compartilhar" na tela de resultados, o App passa um texto com o modo, a pontuação, o título e o URL da loja, junto com uma imagem da tela de resultados, para a tela de compartilhamento do seu sistema operacional. Você escolhe o destino, e o tratamento nele segue a política desse serviço. Nada é enviado ao Desenvolvedor.

#### Artigo 12 (Fornecimento a terceiros)

O Desenvolvedor não vende suas informações e não as fornece a terceiros, exceto nos seguintes casos:

- Google AdMob (Artigo 9): o Google usa as informações coletadas pelo SDK de anúncios, de acordo com suas próprias políticas, para veicular e medir anúncios e prevenir fraudes.
- O ranking público (Artigo 3): por sua natureza, ele é exibido aos outros usuários.
- Prestadores de serviços: o Google (Firebase / Google Cloud) processa e armazena dados conforme as instruções do Desenvolvedor. Os pagamentos são processados pela Apple / pelo Google.
- Quando exigido por lei.

#### Artigo 13 (Uso por crianças)

O App não é direcionado a usuários menores de 13 anos. Pais e responsáveis devem gerenciar a instalação, o uso e as compras feitas por crianças menores de 13 anos. Se o Desenvolvedor tomar conhecimento de que informações de uma criança menor de 13 anos foram enviadas, ele as excluirá prontamente.

#### Artigo 14 (Prazos de retenção)

| Dados | Retenção |
| --- | --- |
| Rankings diário / semanal | Excluídos automaticamente cerca de 2 dias após o fim do período (a exclusão pode levar até cerca de mais um dia) |
| Ranking de todos os tempos | Enquanto o serviço for prestado ou até que você solicite a exclusão |
| Registros de partida (Artigo 4 (1)) | Mantidos para a investigação de trapaças enquanto o serviço for prestado ou até que você solicite a exclusão |
| Conta de login anônimo | Enquanto o serviço for prestado ou até que você solicite a exclusão |
| Registros de banimento e cópias dos registros removidos | Até que o banimento seja revogado ou até que deixem de ser necessários |
| Firebase Analytics | Conforme a configuração de retenção de dados do Google Analytics (dados no nível do usuário por até 14 meses) |
| Firebase Crashlytics | Pelo período definido pelo Google (dados de falhas: 90 dias) |
| Dados no seu dispositivo | Até que você desinstale o App |

#### Artigo 15 (Armazenamento e segurança)

Os dados na nuvem são armazenados no Google Cloud (Firebase / Firestore), e o acesso é restrito pelas Firestore Security Rules e pelo App Check. Toda a comunicação é criptografada (TLS). Os dados podem ser processados e armazenados em servidores do Google fora do seu país.

#### Artigo 16 (Seus direitos e exclusão de dados)

- **Solicitação de exclusão**: para excluir seus dados na nuvem (registros do ranking, registros de partida e a conta de login anônimo), envie um e-mail para <support@haroworks.com> com o assunto "Solicitação de exclusão de dados" e informe seu nome de jogador, país, sistema operacional (iOS / Android) e a pontuação e a data aproximadas. Como o UID anônimo não é exibido no App, identificamos seus registros a partir dessas informações. Em princípio, excluiremos em até 30 dias os registros que pudermos confirmar e avisaremos você.
- Os dados do Firebase Analytics, do Crashlytics e do AdMob são armazenados com identificadores que não estão vinculados ao seu nome ou a dados semelhantes; por isso, o Desenvolvedor pode não conseguir identificá-los e excluí-los individualmente. Eles são excluídos quando os prazos do Artigo 14 expiram.
- **Dados no seu dispositivo**: são excluídos quando você desinstala o App.
- **Alteração das informações exibidas**: você pode alterar seu nome de jogador, país e idioma a qualquer momento na tela de Ajustes.
- **Configurações de anúncios**: nas configurações do seu dispositivo (Android: Configurações > Google > Anúncios; iOS: Ajustes > Privacidade e Segurança), você pode redefinir o ID de publicidade ou desativar os anúncios personalizados. Em regiões onde o consentimento é exigido, você pode alterar seu consentimento em "Privacidade de anúncios", na tela de Ajustes.
- **Direitos previstos nas leis locais**: usuários do EEE, do Reino Unido, da Califórnia e de outros lugares podem exercer direitos como acesso, correção, exclusão e oposição nos termos da legislação aplicável. Entre em contato conosco pelo endereço de e-mail acima. O Desenvolvedor não vende informações pessoais.

#### Artigo 17 (Lei aplicável)

Esta Política será interpretada e aplicada de acordo com as leis do Japão.

#### Artigo 18 (Contato / Alterações nesta Política)

Para dúvidas sobre esta Política ou solicitações de exclusão, entre em contato:

- E-mail: <support@haroworks.com>

O Desenvolvedor poderá revisar esta Política para refletir alterações na legislação ou no App. A Política revisada entra em vigor quando publicada nesta página. Alterações importantes também serão comunicadas nas notas de versão do App ou por meios semelhantes.

---

**Histórico de revisões**

- v1.1 (2026-10-20): Revisão completa para a versão 1.4. Foram adicionadas as informações usadas para prevenir trapaças (registros de partida, estatísticas de toques, App Check, banimentos). Os eventos do Analytics, os formatos de anúncio e as informações coletadas pelo SDK de anúncios, os pacotes de apoio e o compartilhamento foram atualizados para corresponder ao funcionamento real do App, e foram especificados os prazos de retenção e como solicitar a exclusão. Foi removida a menção a "conquistas" armazenadas na nuvem, algo que o App nunca fez.
- v1.0 (2026-06-12): Versão inicial, em vigor com o lançamento da v1.0.0.

---
