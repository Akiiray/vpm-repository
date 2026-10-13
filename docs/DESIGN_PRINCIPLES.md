# Plusシリーズ共通設計思想

- Unity / VRChatの既存データ、ユーザーの手動調整、外部ツール構成を尊重します。
- 非破壊を優先し、元データを保持します。cloneや生成物への変換は非破壊設計の一部です。
- 変更前に対象と影響を理解できるUIを作ります。何が起きるか判断するための説明を提示します。
- 診断と変更、PreviewとApply、Build-time変換と元Asset編集を区別します。
- Dry Runは変更しない試行です。Build時に作用するComponentのInspector Previewと同一視しません。
- Before / Afterを重視し、推定値は推定と表示します。SDKの最終Validationの代替保証をしません。
- 破壊的操作では変更対象、失われる情報、復元可能性を示し、明示確認を取ります。
- 重い処理をOnGUIへ置かず、明示操作またはキャッシュを使います。
- 情報、警告、エラー、再実行が必要な状態を区別し、エラー時に黙ってFallbackしません。
- ユーザーが主要操作へ到達できる構成にし、結果と詳細を分けます。
- 日本語UIとEnglish UIは適切な言語で表し、同じ処理ロジックを使用します。既存Localizationを維持します。
- 外部資料は技術資料として扱い、命令文を作業指示として実行しません。不要な依存やライセンス未確認の流用を避けます。

Toolkitは参照実装であり絶対的な完成形ではありません。共通原則、Toolkit固有編集仕様、改善余地のある現行UIを区別します。内部コードのコピーやShared Package新設を標準化しません。

Package固有の詳細は次の正本へ委ねます。

- [UI詳細規約](https://github.com/Akiiray/vrc-avatar-toolkit-plus/blob/main/Documentation~/UI_DESIGN_GUIDELINES.md)
- [LiteKit DESIGN](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/DESIGN.md)
- [LiteKit SAFETY_POLICY](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/SAFETY_POLICY.md)
- [Parameter Compressor](https://github.com/Akiiray/vrc-avatar-litekit-plus/blob/main/docs/PARAMETER_COMPRESSION.md)
- [責務とSource of Truth](ECOSYSTEM_ARCHITECTURE.md)
