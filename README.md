# Music-Notes

子供向けの楽譜アプリ（単音メロディをカタカナの「ドレミ」で表示）の試作リポジトリです。

## 使い方（iPad）

MIDI キーボードを使うときは、App Store の「Web MIDI Browser」で **https://tajirikey.github.io/Music-Notes/** を開きます（iPad の Safari は MIDI 非対応）。
この入口ページは、キャッシュを避けて毎回最新版のアプリへ移動します。ブックマークはこの URL にしてください。
音は KORG Module Pro などの音源アプリで鳴らし、このアプリは判定と表示だけを行います。

| ページ | URL | 内容 |
|---|---|---|
| [`app/`](app/index.html) | https://tajirikey.github.io/Music-Notes/app/ | 演奏画面の試作。曲を選び、光っている音を弾くと次へ進む |
| [`mic-test/`](mic-test/index.html) | https://tajirikey.github.io/Music-Notes/mic-test/ | マイク・MIDI の聞き取りテスト |

## 構成メモ

- 入力は `noteOn(midi)` に統一（MIDI・画面の鍵盤。マイクはあとで追加する予定）
- 判定はオクターブを区別しない（「ド」ならどの「ド」でも正解）
- 曲データは MIDI 番号の配列で、1つの配列が楽譜の1行。著作権の切れた曲のみ収録
- 記録は localStorage に保存
- バージョンは `app/index.html` の `APP_VERSION` と `app/version.json` の両方を更新する。曲選び画面の下に表示され、古いときは「あたらしい ばんに する」ボタンが出る
