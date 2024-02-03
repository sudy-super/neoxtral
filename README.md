# Neoxtral
Neoxtralは、GPT-NeoXとMixtralを組み合わせたMixture of Expertsモデルです。

パラメータ効率の悪いMixtral Attention (q_proj, k_proj, v_proj, o_projとAttention関連の重みが4種類も存在) を廃し、GPT-NeoXのアーキテクチャを取り入れることで推論・学習双方におけるVRAMの使用量を削減しました。

## その他関連コード
マルチノード学習コードとpt拡張子のモデルファイルをpytorch model形式に変換するコードはすでぃーが保有しています。

## 実験
1台のA100 80GBを使った学習実験では、18億パラメータを持つ8x350Mのモデルをglobal batch sizeを4に設定して実行したところ、49766MBのVRAMを使用しました。

参考として、同パラメータのMixtralの学習ではglobal batch sizeが2で約60000MBを使用しました。
