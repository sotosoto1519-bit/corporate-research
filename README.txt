法人リサーチ AI Ver.0.6 — 個人用クラウド版

初回設定（Windows PC）
1. https://aistudio.google.com/apikey で無料プランのプロジェクトのAPIキーを発行。課金を有効にしないこと。既存の有料プロジェクトを使わないこと。
2. https://dash.cloudflare.com/ で無料アカウントを作成。Workers Freeを選択。
3. https://nodejs.org/ からNode.js LTSをインストール。
4. ZIPを展開し、そのフォルダでPowerShellまたはコマンドプロンプトを開く。
5. 次のコマンドを順に実行する。
   npx wrangler login
   npx wrangler deploy
   npx wrangler secret put GEMINI_API_KEY
   npx wrangler secret put APP_PASSWORD
   APIキーと自分専用の長いランダムな英数字パスワードをそれぞれ入力。公開チャットに貼らない。
6. deploy時に表示された https://...workers.dev をPC/iPadのブラウザで開く。
   ユーザー名 owner / 設定したパスワードでログイン。
7. iPadではSafariの共有→ホーム画面に追加。

使い方
公開されたPDF、DOCX、XLSX、CSV、TXT、PNG、JPEG、WEBPを選択（複数可）。公開資料の確認にチェックし、自動調査開始。法人と役員を抽出して4名ずつ検索する。結果は端末のブラウザ内に保存。CSVで移行・保管可能。履歴は端末間で同期しない。
Word/Excelは内部XMLを抽出してAIに渡す。旧DOC/XLSは変換が必要。埋め込み画像、複雑な書式、暗号化ファイルは非対応。1ファイル8MB、送信全体約16MBまで。Office解析に外部CDNのfflateを使用。
モデル: gemini-2.5-flash-lite。無料枠は変動する。429などのエラーで停止し、別モデルや有料サービスへの自動切替はしない。無料枠の数値をアプリが独自に検証する仕組みはないため、課金無効のプロジェクトが必須。停止ボタンは以降の処理を止めるが送信済みリクエストは取消できない場合がある。
全候補は要確認扱い。出典URLと検索メタデータを照合し、人の同一性・法人情報を確認してから使用する。個人の私的連絡先は対象外。無料APIへの送信データはGoogleのサービス改善に利用される場合がある。公開資料以外は送信しない。

料金: https://ai.google.dev/gemini-api/docs/pricing
利用条件: https://ai.google.dev/gemini-api/terms
Workers: https://developers.cloudflare.com/workers/

検証: JavaScript構文チェック済み。実API、公開環境、iPad実機は未検証。APIキー・Cloudflareアカウントは同梱していない。
