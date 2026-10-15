# VRC Avatar Plus Ecosystem

Toolkit PlusとLiteKit PlusをVCC / ALCOMへ配布するVPMリポジトリです。配布カタログとPlusシリーズの横断文書を管理します。

## VCC / ALCOMへの追加

[リポジトリ追加ページ](https://akiiray.github.io/vpm-repository/addrepos.html)を開いて追加してください。自動起動しない場合は次のURLを手動登録します。

```text
https://akiiray.github.io/vpm-repository/index.json
```

追加ページとカタログはToolkit Plus / LiteKit Plusの両Packageを扱います。

## Package

| Package | 役割・詳細 |
| --- | --- |
| [VRC Avatar Toolkit Plus](https://github.com/Akiiray/vrc-avatar-toolkit-plus) | 日常的なAvatar改変、セットアップ、保守、Material管理、Debug等。Plus UI / UXの参照実装 |
| [VRC Avatar LiteKit Plus](https://github.com/Akiiray/vrc-avatar-litekit-plus) | 診断、Performance Rank計画、Mobile対応支援、非破壊最適化。現行Build-time機能はParameter Compressor |

両者は姉妹プロジェクトで、互いをインストール必須にしません。機能詳細は各Package repositoryを参照してください。

## 横断文書

- [アーキテクチャ・責務・Source of Truth](docs/ECOSYSTEM_ARCHITECTURE.md)
- [共通設計思想](docs/DESIGN_PRINCIPLES.md)
- [Release運用](docs/RELEASE_POLICY.md)
- [このリポジトリの作業方針](AGENTS.md)

VPMの配布実体は各GitHub ReleaseのVPM用asset ZIPです。[index.json](index.json)はその公開カタログであり、Unity機能のソースはここへ置きません。
