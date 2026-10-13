# Plusシリーズ横断アーキテクチャ

## リポジトリの関係

```text
vrc-avatar-toolkit-plus
    └─ 日常的なAvatar改変・保守
       └─ UI / UX参照実装
vrc-avatar-litekit-plus
    └─ 診断・計画・非破壊最適化
       └─ Build-time transformation（現行はParameter Compressor）
各Package source → GitHub Releases
    └─ 各PackageのVPM用Release asset ZIP
vpm-repository
    └─ Release assetを参照するカタログをVCC / ALCOMへ公開
```

ToolkitとLiteKitは依存関係ではなく姉妹プロジェクトです。片方の導入にもう片方を必須にしません。共通UI原則を参照しても、内部実装や非破壊設計を機械的に移植しません。

| リポジトリ | 責務 |
| --- | --- |
| [Toolkit](https://github.com/Akiiray/vrc-avatar-toolkit-plus) | Avatar setup、導入支援、Material管理、Debug / Analysis、Dynamics保守、Texture utility。UI / UX参照実装 |
| [LiteKit](https://github.com/Akiiray/vrc-avatar-litekit-plus) | 診断、Rank解析、計画、Mobile対応支援、clone上の非破壊最適化。現行NDMF利用の主要機能はParameter Compressor |
| [VPM](https://github.com/Akiiray/vpm-repository) | index、追加ページ、Release asset URL / SHA256、横断文書、Packageへの導線 |

VPMにEditor / Runtime機能やPackageソースを置きません。共通化は設計規約から始め、継続的なコード重複が問題になった場合のみ共通ライブラリを検討します。

## Source of Truth

| 情報 | 正本 |
| --- | --- |
| Toolkit機能仕様 | [Toolkit repository](https://github.com/Akiiray/vrc-avatar-toolkit-plus) |
| Plus UI詳細設計 | [Toolkit UI design document](https://github.com/Akiiray/vrc-avatar-toolkit-plus/blob/main/Documentation~/UI_DESIGN_GUIDELINES.md) |
| LiteKit非破壊設計 | [DESIGN](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/DESIGN.md) / [SAFETY_POLICY](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/SAFETY_POLICY.md) |
| Parameter Compressor | [LiteKit PARAMETER_COMPRESSION](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/PARAMETER_COMPRESSION.md) |
| 開発中Package version / dependencies | 各Packageのpackage.json |
| Package変更履歴 | 各PackageのCHANGELOG |
| Release実体 | 各GitHub ReleaseのVPM用Release asset ZIP |
| VCC / ALCOM公開カタログ | [index.json](../index.json) |
| 横断アーキテクチャ | このECOSYSTEM_ARCHITECTURE |
| 共通設計思想 | [DESIGN_PRINCIPLES](DESIGN_PRINCIPLES.md) |
| Release運用 | [RELEASE_POLICY](RELEASE_POLICY.md) |

カタログ中のPackage metadataはRelease時の確定情報を照合して記載します。開発中sourceのVersionとカタログの公開Versionが常に一致するとは限りません。詳細仕様を複数文書に複製せず、正本へのリンクで接続します。矛盾時は現行コード・README・DESIGN・CHANGELOG・package.jsonを比較して報告します。

## 横断変更の範囲

LiteKit固有UIはLiteKit、共通UI原則はToolkitの詳細規約と必要なVPM概要、Release公開は各Package / Release asset / VPMカタログに影響します。依存変更はPackage metadataと該当文書、Release時にはカタログへ反映します。理由なく同じ変更を3リポジトリへコピーしません。
