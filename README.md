# Neoxtral
Neoxtralは、GPT-NeoXとMixtralを組み合わせたMixture of Expertsモデルです。

Mixtral Attentionを廃し、GPT-NeoX Attentionを取り入れたアーキテクチャです。

Mistral Attentionに比べて多少パラメータ効率が向上しています。

## その他関連コード
マルチノード学習コードとpt拡張子のモデルファイルをpytorch model形式に変換するコードは後日公開予定です。

## 実験
1台のA100 80GBを使った学習実験では、18億パラメータを持つ8x350Mのモデルをglobal batch sizeを4に設定して実行したところ、49766MiBのVRAMを使用しました。

参考として、同パラメータのMixtralの学習では4 global batch sizeで約60000MiBを使用しました。
