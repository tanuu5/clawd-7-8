# Clawd 7/8

変拍子の曲に合わせてノーツを叩く、ブラウザ向けのリズムゲームです。4レーンのハイウェイは Three.js で描画し、画面の横では Clawd が拍に合わせて踊ります。

**▶ プレイ：** https://tanuu5.github.io/clawd-7-8/

## 遊び方

| 操作 | 内容 |
| --- | --- |
| `D` `F` `J` `K`（または `←` `↓` `↑` `→`） | 各レーンを叩く |
| タップ | レーンを直接タッチ（複数の指で同時に押せます） |
| `Space` / `Enter` | スタート・リトライ |
| `Esc` | 一時停止・再開 |

- 難易度は EASY / NORMAL / HARD の3つ。判定は PERFECT / GREAT / GOOD / MISS の4段階で、満点は 1,000,000 点です。
- ランクは S〜D。自己ベストはブラウザ（localStorage）に保存されます。
- Bluetooth イヤホンなどで音が遅れて聞こえるときは、タイトル画面の「音の遅延補正」を＋側へ動かしてください。

## 楽曲「Seven Claws」

音源ファイルは使っていません。Web Audio API で、プレイ中にその場で合成しています。

- 拍子：7/8（2+2+3）→ 10/8（3+3+2+2）→ 13/8（3+3+3+2+2）
- テンポ：♪ = 300（8分音符 0.2 秒）、D ドリアン、約80秒
- 構成：INTRO → THEME → BRIDGE → HOOK → THEME II → BREAK → HOOK II → CODA
- 譜面は曲のイベント（キック、スネア、メロディ、アルペジオ）から自動で作っています。

## 技術構成

- `index.html` 1ファイルだけで動きます。ビルドは不要です。
- [Three.js r128](https://threejs.org/)（cdnjs から読み込み）
- Web Audio API（シンセ、ドラム、リバーブ、ディレイ、先読みスケジューラ）
- 奥のトンネルは、今の拍子と同じ数の角を持つ多角形で表示しています（7/8 なら7角形）。

ローカルで遊ぶときは `index.html` をブラウザで開くだけです。ブラウザの自動再生の制限があるため、音はスタートボタンを押してから鳴ります。

## クレジット

- **制作：Claude（Anthropic）**。モデルは Claude Opus 5.5 で、Claude Code を使って作りました。
- **Clawd について：** Clawd は Anthropic の Claude Code マスコットです。このリポジトリの SVG 版 Clawd は、公式アセットではなく二次創作（ファンアート）です。Clawd の名称とキャラクターの権利は Anthropic に帰属します。

## ライセンス

コード（HTML / CSS / JavaScript）は [MIT License](LICENSE) で公開しています。Clawd のキャラクターは MIT License の対象外です。上の「クレジット」を参照してください。
