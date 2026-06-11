## VCC / ALCOM への追加

以下をクリックするとリポジトリを追加できます。

https://akiiray.github.io/vpm-repository/addrepos.html

手動追加用 URL:

https://akiiray.github.io/vpm-repository/index.json

# VRC Avatar Toolkit Plus

VRC Avatar Toolkit Plus は、VRChat アバター制作・改変作業を効率化するための Unity Editor 拡張ツール集です。
複数アバターや Prefab に対する一括処理や、セットアップ・保守・デバッグ作業を支援します。

## 主な機能

### Avatar Setup

よく利用されるアバター向けツールやギミックの導入を、個別または一括で行えます。

対応する対象例:

* Avatar Optimizer (AAO)
* Avatar Compressor (LAC)
* RBS Sleep System Ver.2
* 赤夜式 撫で音ギミック
* LightLimitChanger
* 可愛いポーズ
* 可愛いポーズ（8bit・足の高さなし）

Hierarchy 上のアバターだけでなく、Prefab やフォルダ内の Prefab を対象とした一括セットアップにも対応しています。

### Material Copy

アバターで使用されている Material を安全に複製し、Renderer の参照をまとめて差し替えられます。

* Material の一括複製
* Prefab 用 Material の複製・差し替え
* Prefab ごとの Material 分離
* 任意の Material への置き換え

### Debug & Analysis

アバターや Prefab の解析を支援する各種デバッグツールを搭載しています。

* 導入済みコンポーネントや依存関係の確認
* コンポーネント情報やパラメーターの調査
* Prefab・Hierarchy の解析レポート生成
* 開発・トラブルシューティング支援

### Dynamics Utilities

VRChat Dynamics 関連コンポーネントの重複検出・整理をサポートします。

対応コンポーネント:

* VRCPhysBone
* VRCPhysBoneCollider
* VRCContactReceiver
* VRCContactSender

### Texture Utilities

アバターで使用されているテクスチャを検出し、Streaming Mipmaps の設定を効率的に有効化できます。

---

## 前提ツール・対応パッケージ

本ツールの一部機能は、以下の外部ツールやパッケージと連携します。

* Avatar Optimizer (AAO)
* Avatar Compressor (LAC)
* Modular Avatar
* RBS Sleep System Ver.2
* 赤夜式 撫で音ギミック
* LightLimitChanger
* 可愛いポーズ

これらのパッケージがインストールされている場合、導入支援や状態確認などの機能を利用できます。

詳細な使い方や各機能の説明については、本パッケージ内のドキュメントおよびプロジェクト README を参照してください。
