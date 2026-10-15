# Release運用

## 権限と変更の分離

コード変更とRelease作業は別です。SemVer上の推奨Versionは判断・報告できますが、ユーザーからReleaseまたはVersion更新の明示指示がない限り、Package version、CHANGELOGのRelease version、tag、GitHub Release、Release asset、VPM index、SHA256を変更しません。Version更新だけの指示を配布公開までの許可と解釈せず、指示された範囲を実行します。文書だけの変更では原則Versionを上げません。

## 公開の流れ

```text
Package sourceと検証
↓
package.json version確定
↓
CHANGELOG
↓
Git tag / GitHub Release
↓
VPM用Release asset ZIP
↓
実ZIPからSHA256計算
↓
vpm-repository/index.json更新
```

配布の実体はGitHub Release assetです。index.jsonはその実体をVCC / ALCOMへ公開するカタログであり、Release assetより先にURL / hashを確定しません。

## 照合する情報

1. 確定source、package.json、CHANGELOG、tag / ReleaseのVersionを照合します。
2. 現行運用ではVPM用ZIPを手動作成し、GitHub Releaseへ手動添付します。明示指示なしにZIP生成処理、GitHub Actions、release workflowを追加しません。
3. ZIP直下にpackage.jsonとPackage内容があることを確認します。リポジトリ名やPackagesによる1段深い構造を作りません。必要なUnity .metaを保持し、.git / .github / Library / Temp / ProjectSettings等を除外します。
4. 実際に添付されたZIPのmetadataと内容を確認し、その実ZIPのバイト列からSHA256を計算します。
5. Release asset直リンク、Version、Package名、依存、実hashをindexへ反映し、追加・取得経路を確認します。assetが未存在なら推測のURL / hashを確定値にしません。

Package metadataの正本は各package.json、配布実体はRelease asset、公開カタログはindexです。[Source of Truth](ECOSYSTEM_ARCHITECTURE.md)を参照してください。

## ZIPの区別と公開済みVersion

GitHub自動生成のSource code ZIPはtagのsource archiveであり、VPM用Release asset ZIPとは別物です。VPMのPackage URLには`releases/download/vX.Y.Z/<package-id>-vX.Y.Z.zip`形式の手動添付assetを使い、`archive/refs/tags/*.zip`を使いません。

公開済みVersionのRelease assetを差し替えることを標準運用にしません。修正は新Versionとして公開し、新assetとhashを作ります。過去の欠落情報・不整合を見つけても推測で埋めず、実体と履歴を確認して報告し、変更は明示された範囲で行います。
