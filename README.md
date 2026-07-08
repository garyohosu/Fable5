# Fable5

Claude Fable 5 を使って `opus-fable-workflow` スキルを開発したときの制作リポジトリです。

## このリポジトリの目的

- **opus-fable-workflow スキルの開発と制作記録の保管**
  - Fable 5が使えない環境でも、Opus 4.8でFable 5に近い品質の作業を行うための「作業手順スキル」を開発した
  - 開発過程の判断や気づきは `dream.md` に時系列で記録している
- モデルの性能を偽装するものではなく、タスク分解・前提確認・自己レビューという手順の工夫で品質を底上げする方針で作られている

## 構成

```
Fable5/
├── README.md                  … このファイル
├── dream.md                   … 開発中の作業記録（Dreamingタイム）
└── opus-fable-workflow/       … スキル本体（制作アーカイブ）
    ├── SKILL.md               … スキル定義（発動条件・作業手順・テンプレート集）
    ├── README.md              … スキルの概要・使い方
    └── examples/              … 用途別テンプレートと記入例
        ├── claude-code.md         … Claude Code作業用
        ├── writing.md             … 文章・記事作成用
        ├── technical-research.md  … 技術調査用
        ├── code-review.md         … コードレビュー用
        ├── email.md               … メール作成用
        └── trigger-check.md       … 発動確認用テストプロンプト集
```

## スキルの正本について

このリポジトリの `opus-fable-workflow/` は**制作時のアーカイブ**です。
運用中の正本は skills リポジトリで管理しています。

- 正本：[garyohosu/skills](https://github.com/garyohosu/skills) の `opus-fable-workflow/`
- 配布先：`~/.claude/skills/`（skills リポジトリの `sync-claude-skills.bat` でミラー同期）

スキルを修正する場合は skills リポジトリ側を編集してください。
ここを編集しても `~/.claude/skills` には反映されません。

## 使い方

1. skills リポジトリの `sync-claude-skills.bat` を実行してスキルを `~/.claude/skills/` に配置する
2. Claude Code で重要な作業を依頼するときに、次のように言うと発動する
   - 「Fable 5がないので、Opus 4.8で丁寧にやって」
   - 「Fable-likeモードでレビューして」
   - 「重要なレビューです。しっかり見て」
3. 定型で依頼したい場合は `opus-fable-workflow/examples/` のテンプレートをコピーして使う
4. 発動精度を確かめたい場合は `opus-fable-workflow/examples/trigger-check.md` のプロンプト集を使う

## dream.md について

グローバル CLAUDE.md の運用ルール「Dreamingタイム」に従い、作業完了ごとに
「今回やったこと／気づいたこと／改善点／次に試すとよさそうなこと」を追記した作業日誌です。
個人リポジトリのため Git 管理に含めています。

## 注意

このスキルは Opus 4.8 を Fable 5 と同等にするものではありません。
Fable 5 向きの重要作業を、Opus 4.8 でも安定して処理しやすくするための作業手順スキルです。
