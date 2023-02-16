# alg-hugo-theme

## License

オリジナルのテーマは[hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack)です。クレジット表記`Theme Stack designed by Jimmy`を消さないでください。

ライセンスはFork元リポジトリの[GNU General Public License v3.0](https://github.com/CaiJimmy/hugo-theme-stack/blob/master/LICENSE)を引き継ぎます。

## Requirements

**Hugo Extended**の0.87.0以上が必要です。

## Installation

```sh
git submodule add git@github.com:RICORA/alg-hugo-theme/ themes/alg-hugo-theme
```

元の`config.yaml`をテーマに同梱されている`./exampleSite/config.yaml`で上書きしてください。

## Features

独自実装したもののみ記載しています。独自実装でないものについては本家リポジトリのドキュメントを参照してください。

### Layouts

#### メンバーページ

linksを改変したものです。メンバーの情報は以下のように記述を追加してください。使用できるアイコンは[Icons](#Icons)のビットマップアイコンを参照してください。

```yml
title: メンバー
links:
  - title: 坊っちゃん
    description: 創立125周年を記念して誕生したイメージキャラクター「坊っちゃん」。夏目漱石の小説『坊っちゃん』で、主人公が本学の前身である東京物理学校を卒業し、松山の中学校に数学の教師として赴任した設定にちなんで誕生しました。
    image: https://avatars.githubusercontent.com/u/33452053
    social:
      - icon: brand-github
        link: https://github.com/RICORA
      - icon: brand-twitter
        link: https://twitter.com/ricora_alg
      - link: https://tus-ricora.com/

  - title: マドンナちゃん
    description: 『坊っちゃん』に登場する「マドンナ」をモチーフにサブキャラクターとして誕生した「マドンナちゃん」。東京理科大学が女子中高生向けに行っている「科学のマドンナ」プロジェクトの広報活動などで活躍しています。
    image: https://avatars.githubusercontent.com/u/33452053
    social:
      - icon: brand-zenn
        link: https://zenn.dev/p/ricora
      - icon: brand-atcoder
        link: https://atcoder.jp/users/tourist

menu:
  main:
    weight: 0
    params:
      icon: users
slug: member
```

#### 記事のEmoji

記事に対してEmojiを設定できます。設定したEmojiはその記事のサムネイル画像として表示されます。

Emojiを設定するには記事のヘッダー内に以下のような記述を追加してください。Unicode文字番号を16進数で指定します。

```yml
emoji: 270F
```

#### Google Search Consoleの認証用タグ

`config.yaml`に以下のような記述を追加してください。

```yml
params:
  googleSiteVerification: XXXXXXX_XXXX-XXXXXXXXXXXX-XXXXXX-XXXXXXXXXX
```

#### OGP画像

OGP画像は`./opengraph/`以下にある画像が参照されます。[tcardgen](https://github.com/RICORA/tcardgen)の使用を想定しています。

#### 記事の最終更新日時の表示

記事のヘッダー内の`lastmod`にある日時が表示されます。

```yml
date: 2023-01-01T00:00:00+09:00
lastmod: 2023-01-04T18:00:00+09:00
```

### Shortcodes

#### Linkcard

リンクをOGPを使用してカード形式で表示できます。

本文中で以下のように使用します。

```md
{{< linkcard url=https://example.com/ >}}
```

#### Slide

SpeakerDeck, Google Slides, Marp等のスライドの埋め込みを表示できます。

本文中で以下のように使用します。

```md
{{< slide url=https://example.com/ >}}
```

#### Schedule

スケジュールをカード形式で表示できます。

記事のヘッダー内に以下のような記述を追加してください。

```yml
schedule:
  - title: 春の新歓 オンライン合同説明会
    date: 4/10 (日) 13:00-13:10
    detail: 理科大春の新歓公式Zoomにて、私たちの活動紹介をします。

  - title: 新入部員向け説明会
    date: 4/13 (水) 18:30-21:00
    detail: 講義棟K405教室にて、プログラミング入門講座を開催します。

  - title: 春の新歓 対面ブース
    date: 4/17 (日) 10:00-16:00
    detail: 講義棟K304教室にて、私たちの活動紹介をします。履修相談も大歓迎です。
```

本文中で以下のように使用します。

```md
{{< schedule url=https://example.com/ >}}
```

### Widgets

#### Twitter

Twitterのタイムラインを表示します。

`config.yaml`に以下のような記述を追加してください。

```yml
params:
  widgets:
    homepage:
      - type: twitter
        params:
          screenName: ricora_alg
```

### Icons

#### 汎用

[tabler-icons](https://github.com/tabler/tabler-icons)のベクター画像を使用しています。

|ファイル名|画像|
|:-:|:-:|
|`activity.svg`|![activity.svg](assets/icons/activity.svg)|
|`brand-youtube.svg`|![brand-youtube.svg](assets/icons/brand-youtube.svg)|
|`info-circle.svg`|![info-circle.svg](assets/icons/info-circle.svg)|
|`mail.svg`|![mail.svg](assets/icons/mail.svg)|
|`news.svg`|![news.svg](assets/icons/news.svg)|
|`star.svg`|![star.svg](assets/icons/star.svg)|
|`users.svg`|![users.svg](assets/icons/users.svg)|

#### メンバーページ用

メンバーページではビットマップ画像を使用しています。

|ファイル名|画像|
|:-:|:-:|
|`brand-atcoder.png`|<img src="assets/icons/brand-atcoder.png" height="24px">|
|`brand-github.png`|<img src="assets/icons/brand-github.png" height="24px">|
|`brand-hatenablog.png`|<img src="assets/icons/brand-hatenablog.png" height="24px">|
|`brand-note.png`|<img src="assets/icons/brand-note.png" height="24px">|
|`brand-qiita.png`|<img src="assets/icons/brand-qiita.png" height="24px">|
|`brand-twitter.png`|<img src="assets/icons/brand-twitter.png" height="24px">|
|`brand-youtube.png`|<img src="assets/icons/brand-youtube.png" height="24px">|
|`brand-zenn.png`|<img src="assets/icons/brand-zenn.png" height="24px">|

### Styles

#### Global font family

日本語向けのものに変更してあります。フォントは以下の通りです。

```scss
:root {
  --sys-font-family: Helvetica, "Sawarabi Gothic", Meiryo, "メイリオ", "Hiragino Kaku Gothic ProN", "ヒラギノ角ゴ ProN", YuGothic, "游ゴシック", Arial, sans-serif;
}
```

## Contribution

コミットメッセージには過去のログを参考に適切そうなPrefixを付け、独自実装した機能についてはREADMEに概要を記載してください。