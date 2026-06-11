---
title: TsubuTalk Privacy Policy (Android)
permalink: /tsubutalk/privacy-android/
---

# つぶトレ / TsubuTalk — Privacy Policy (Android)

**発効日 / Effective:** 2026-05-16 ・ **バージョン / Version:** 1.0 ・ **連絡先 / Contact:** [support@haroworks.com](mailto:support@haroworks.com) ・ **applicationId:** `app.tsubutalk.mobile`

[← Index](../../)

## §A. 日本語 (ja, default)

### つぶトレ プライバシーポリシー

つぶトレ (以下「本アプリ」) における個人情報および利用者データの取扱いについて定めます。本アプリの提供者 (以下「開発者」) は以下のとおり個人情報および利用者データを取扱います。

#### 第 1 条 (適用範囲)

本ポリシーは、開発者が Google Play で配信する Android アプリ「つぶトレ」 (applicationId: `app.tsubutalk.mobile`) のすべての利用者に適用されます。本アプリの利用を開始した時点で、利用者は本ポリシーに同意したものとみなします。

#### 第 2 条 (収集しない情報)

本アプリは以下の個人情報を**一切収集しません**。

- 氏名、住所、電話番号、メールアドレス
- 生年月日、性別、職業
- 位置情報
- 端末識別子 (IMEI、Android ID、シリアル番号)
- 連絡先、SMS、通話履歴

本アプリにアカウント登録機能はありません。アプリの利用は完全に匿名で行われます。

#### 第 3 条 (端末内にのみ保存されるデータ)

本アプリは以下のデータを利用者の端末内ストレージ (`filesDir` および Room データベース) にのみ保存します。これらのデータは開発者を含む第三者に送信されることはなく、開発者は端末内のデータを取得・閲覧する手段を持ちません。

- 録音音声 (AAC / M4A 形式、`filesDir/recordings/` に保存)
- 文字起こし結果 (transcript)
- スコア (声量・話速・フィラー率・発音明瞭度の 4 軸)
- 録音メタデータ (録音日時、長さ、お題選択履歴、UI 言語タグ (ja / en / zh-CN / zh-TW / ko のいずれか))
- マイクキャリブレーション値
- 外部 AI チャット連携の送信履歴 (送信日時 / テンプレート種別 / 送信先プロバイダ / UI ロケールのみ。送信した本文・transcript は保存しません)
- アプリ設定 (UI 言語、認識言語、テーマモード、優先 AI プロバイダ)

端末バックアップ機能は無効化されています (`android:allowBackup="false"`)。クラウドや他端末への自動同期は行われません。データを別端末に移行したい場合は、設定画面の「データエクスポート」から SAF (Storage Access Framework) 経由で JSON ファイルとして書き出してください。

#### 第 4 条 (外部送信が発生する場面)

本アプリが外部のサーバー・サービスと通信するのは、以下の 3 つの場面に限られます。

1. **音声認識モデルの初回ダウンロード**
   - 初回起動時、Hugging Face またはミラーサーバーから音声認識モデル (whisper.cpp、多言語モデル: ja / en / zh-CN / zh-TW / ko を 1 ファイルでカバー) のバイナリ (約 466 MB) をダウンロードします。
   - ダウンロード中はモデル配布サーバーが利用者の IP アドレスを参照しますが、本アプリは利用者識別情報を送信しません。
2. **広告配信 (全利用者、Google AdMob)**
   - 本アプリは完全無料で提供され、全利用者にバナー広告 (フィードバック画面) およびインタースティシャル広告 (ASR 処理中) を表示するため、Google AdMob SDK が動作します。
   - **ターゲティング広告 (パーソナライズド広告) は無効化**しており、AdMob は非個別化広告のみを配信します。
   - AdMob は広告 ID (Advertising ID) を SDK 内で参照しますが、本アプリは広告 ID をサーバーに送信しません。
   - AdMob のプライバシーに関する取扱いは Google のポリシー (<https://policies.google.com/privacy>) に従います。
3. **外部 AI チャット連携 (利用者の明示的操作起点)**
   - 録音詳細画面で「ChatGPT / Gemini / Claude で深掘りする」等のボタンを押下した場合に限り、Share Intent / クリップボード / ブラウザ起動を経由して、利用者が選択したテキスト (transcript + プロンプトテンプレート) が利用者の意思で外部 AI チャットアプリ・Web に送信されます。
   - 送信は利用者の操作を起点として発生し、本アプリは AI 各社の API を直接呼び出しません。
   - 送信先 AI チャット (OpenAI / Google / Anthropic) のプライバシーに関する取扱いは、各社のポリシーに従います:
     - OpenAI (ChatGPT): <https://openai.com/policies/privacy-policy>
     - Google (Gemini): <https://policies.google.com/privacy>
     - Anthropic (Claude): <https://www.anthropic.com/legal/privacy>

上記 3 経路以外の egress は発生しません。録音音声・transcript・スコア等のデータは、利用者の明示的操作 (上記 3. の Share Intent / クリップボード操作、または JSON エクスポート) を経ずに端末外に送信されることはありません。

本アプリは完全無料で提供され、サブスクリプション / 買い切りのアプリ内課金は一切ありません。そのため Google Play Billing SDK は統合されておらず、課金・ライセンスチェック目的の Google Play との通信は発生しません。

#### 第 5 条 (第三者提供)

本アプリは、利用者の個人情報および端末内データを、第三者に対して開示・提供しません。法令に基づく開示要請があった場合を除きます。

#### 第 6 条 (クラッシュレポート・分析の不使用)

本アプリは Firebase Crashlytics、Sentry、Google Analytics などの外部クラッシュレポート・分析サービスを利用しません。アプリの不具合は利用者からのフィードバック (本ポリシー第 11 条記載のメールアドレス) を通じて開発者に伝達される設計です。

#### 第 7 条 (子どもの利用)

本アプリは **13 歳未満の利用者を対象としていません**。アプリ内に表示される広告は AdMob によって配信され、ターゲティング広告は無効化していますが、広告内容の年齢適合性を保証するものではありません。13 歳未満の利用者が本アプリを利用しないよう、保護者の方は本アプリのインストール・利用について管理してください。

万一、13 歳未満の利用者から個人情報が送信された事実が判明した場合、開発者は速やかにデータを削除します (端末内データの場合、利用者または保護者が設定画面の「データ全削除」を実行することで完全削除可能)。

#### 第 8 条 (利用者の権利)

利用者は以下の権利を有します。

- **データ削除権**: 設定画面の「データ管理」 > 「データを全て削除」、またはアプリ本体のアンインストールにより、端末内のすべてのデータを完全に削除できます。
- **データポータビリティ**: 設定画面の「データエクスポート」より、すべての録音メタデータ・transcript・スコア・キャリブレーション値を JSON 形式で書き出し、他端末に移行できます。
- **広告 ID リセット**: Android の「設定 > Google > 広告」より広告 ID のリセット・パーソナライズド広告のオプトアウトを行うことができます (Android OS の機能)。

開発者は端末内データを保持していないため、開発者に対して「データの開示請求」「訂正請求」「利用停止請求」を行う必要はありません (すべて端末内で利用者自身が完結できます)。

#### 第 9 条 (準拠法)

本ポリシーの解釈および適用は、日本国の法律に準拠します。

#### 第 10 条 (本ポリシーの変更)

本ポリシーは、関連法令の改正・サービス内容の変更等に伴い、開発者が必要と判断した場合に改定されることがあります。改定後のポリシーは、本書の HTTPS 公開ページおよび Google Play のアプリ詳細ページ「プライバシーポリシー」リンクに掲示された時点から効力を生じます。重要な変更がある場合は、アプリ内通知またはリリースノートで利用者に通知します。

#### 第 11 条 (お問い合わせ)

本ポリシーに関するお問い合わせは、以下のメールアドレスまでご連絡ください。

- メールアドレス: `support@haroworks.com`
- アプリ内からの送信: 設定 > アプリ情報 > 「フィードバックを送る」より、お使いのメールクライアントで上記宛先にメールを作成できます。

---

**改定履歴**

- v1.0 (2026-05-16): 初版策定 (v1.0 リリースに合わせて発効)。
- v1.0 (2026-05-19 更新): 5 ロケール多言語 (ja / en / zh-CN / zh-TW / ko) + 完全無料化を反映。第 3 条で UI 言語タグの値域を列挙、`uiLocale` カラム追加と整合。第 4 条を 4 経路 → 3 経路に縮減 (Google Play 課金通信を削除)、AdMob を「無料版のみ」→「全利用者」に変更、whisper を多言語モデル明記。アプリ設定リストから「課金状態キャッシュ」削除。発効日 2026-05-16 とバージョン番号 1.0 は据え置き。

---

## §B. English (en-US)

### TsubuTalk Privacy Policy

This Privacy Policy describes how TsubuTalk (the "App") handles personal information and user data. The developer of the App (the "Developer") handles personal information and user data as follows.

#### Article 1 (Scope)

This Policy applies to all users of the Android application "TsubuTalk" (applicationId: `app.tsubutalk.mobile`) distributed by the Developer through Google Play. By starting to use the App, you are deemed to have agreed to this Policy.

#### Article 2 (Information We Do Not Collect)

The App **does not collect** any of the following personal information:

- Name, address, phone number, or email address
- Date of birth, gender, or occupation
- Location data
- Device identifiers (IMEI, Android ID, serial number)
- Contacts, SMS messages, or call history

The App has no account registration. Use of the App is fully anonymous.

#### Article 3 (Data Stored Only on Your Device)

The App stores the following data exclusively in your device's local storage (`filesDir` and Room database). This data is never transmitted to any third party, including the Developer, and the Developer has no means of accessing data stored on your device.

- Audio recordings (AAC / M4A, stored under `filesDir/recordings/`)
- Transcripts
- Scores (volume, speech rate, filler rate, pronunciation clarity)
- Recording metadata (timestamp, duration, topic selections, UI language tag (one of ja / en / zh-CN / zh-TW / ko))
- Microphone calibration values
- External AI chat hand-off logs (timestamp / template kind / target provider / UI locale only — the prompt text and transcript are not stored in the log)
- App settings (UI language, recognition language, theme mode, preferred AI provider)

Device backup is disabled (`android:allowBackup="false"`). No automatic sync to the cloud or other devices occurs. To migrate data to another device, use Settings > Data Export to write a JSON file via the Storage Access Framework (SAF).

#### Article 4 (When External Communication Occurs)

The App communicates with external servers or services **only in the three cases below**.

1. **First-time download of the speech-recognition model**
   - On first launch, the App downloads the whisper.cpp model binary (approx. 466 MB, a multilingual model covering ja / en / zh-CN / zh-TW / ko in a single file) from Hugging Face or a mirror server.
   - During download, the model server may observe your IP address; however, the App itself transmits no identifying user information.
2. **Ad delivery (all users, via Google AdMob)**
   - The App is completely free, and the Google AdMob SDK serves a banner ad (on the feedback screen) and an interstitial ad (during analysis) to all users.
   - **Personalized advertising is disabled**; AdMob serves only non-personalized ads.
   - The AdMob SDK references the device's Advertising ID internally, but the App itself does not transmit the Advertising ID to its own servers.
   - AdMob's privacy practices follow Google's policy (<https://policies.google.com/privacy>).
3. **External AI chat hand-off (user-initiated only)**
   - Only when you explicitly tap a button such as "Open in ChatGPT / Gemini / Claude" on the recording detail screen, the text you have selected (transcript + prompt template) is sent — at your direction — to an external AI chat app or web service via Share Intent, clipboard, or a browser launch.
   - Transmission is always initiated by your action. The App does not call any AI provider's API directly.
   - The privacy practices of the destination AI chat services (OpenAI / Google / Anthropic) follow their respective policies:
     - OpenAI (ChatGPT): <https://openai.com/policies/privacy-policy>
     - Google (Gemini): <https://policies.google.com/privacy>
     - Anthropic (Claude): <https://www.anthropic.com/legal/privacy>

No egress occurs outside the three channels above. Audio recordings, transcripts, scores, and similar data are never transmitted off your device without your explicit action (a Share Intent, clipboard operation, or JSON export under the three channels above).

The App is provided completely free of charge, with no subscriptions or in-app purchases of any kind. The Google Play Billing SDK is therefore not integrated, and no billing / license-check communication with Google Play occurs.

#### Article 5 (Third-Party Sharing)

The App does not disclose or provide your personal information or on-device data to any third party, except where required by law.

#### Article 6 (No Crash Reporting or Analytics)

The App does not use external crash-reporting or analytics services such as Firebase Crashlytics, Sentry, or Google Analytics. Issues are intended to reach the Developer only through user feedback emails (see Article 11).

#### Article 7 (Children's Use)

The App **is not directed at users under 13 years of age**. Ads inside the App are served by AdMob with personalized advertising disabled; however, ad content suitability for any specific age group cannot be guaranteed. Parents and guardians are responsible for managing the installation and use of the App by users under 13.

If the Developer becomes aware that personal information has been transmitted by a user under 13, the Developer will promptly delete such data. On-device data can be fully erased by the user or guardian via Settings > Data Management > Delete All Data.

#### Article 8 (Your Rights)

You have the following rights with respect to App data:

- **Right to delete**: Use Settings > Data Management > Delete All Data, or uninstall the App, to permanently delete all data stored on your device.
- **Data portability**: Use Settings > Data Export to export all recording metadata, transcripts, scores, and calibration values as a JSON file, which you can move to another device.
- **Advertising ID reset**: You can reset your Advertising ID or opt out of personalized advertising from Android's Settings > Google > Ads.

Because the Developer does not retain any of your data, there is no need to submit access, correction, or restriction requests to the Developer — you control all data directly on your device.

#### Article 9 (Governing Law)

This Policy shall be interpreted and applied in accordance with the laws of Japan.

#### Article 10 (Changes to This Policy)

The Developer may revise this Policy when required by changes in applicable laws or in the App's features. Revised versions take effect once posted on this HTTPS page and linked from the Privacy Policy field on the Google Play listing. Material changes will additionally be communicated to users via in-app notifications or release notes.

#### Article 11 (Contact)

For questions about this Policy, please contact:

- Email: `support@haroworks.com`
- From within the App: Settings > About > Send feedback opens your mail client pre-populated with the address above.

---

**Revision history**

- v1.0 (2026-05-16): Initial draft, in effect with the v1.0 release.
- v1.0 (2026-05-19 update): Reflected 5-locale multilingual support (ja / en / zh-CN / zh-TW / ko) and the completely-free monetization decision. Article 3 enumerates UI language tag values and adds `uiLocale` to the hand-off log fields. Article 4 reduced from 4 to 3 channels (Google Play billing channel removed); AdMob is now described as serving all users; the whisper model is described as multilingual. The "billing-state cache" entry was removed from the app settings list. The effective date 2026-05-16 and version number 1.0 are unchanged.

---

