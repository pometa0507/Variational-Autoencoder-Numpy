# Variational-Autoencoder-Numpy
Variational Autoencoder(VAE) on MNIST in Numpy

# Lisense
This software is released under the MIT License, see license.txt.

# Introduction

The Variational Autoencoder (VAE) is one of the generative models.

This VAE is implemented using Numpy without using a deep learning framework.

# Python Library
To run the code, the following software is required.

Python 3.x
NumPy
Matplotlib
(cupy)
Cupy is optional. With Cupy, matrix operations can be done efficiently using the GPU.

# Usage

This notebook that can run in Google Colab, so it's ready to go.


# VAEの概要
From here, writing in Japanese.

Variational Autoencoder(VAE)は生成モデルのひとつです。

Variational Autoencoder(VAE)をディープラーニングのフレームワークを使わずにNumpyを使って実装しました。
<br>
Google Colabで実行できるノートブックですので、すぐにお試し動作できます。


<br>
MNIST手書き文字の生成例（上段がオリジナル画像、下段が生成画像）

![Gen_Images](https://github.com/pometa0507/Variational-Autoencoder-Numpy/blob/master/plots/Gen_Images.png)



# ネットワーク構成

VAEはEncoderで入力データを潜在変数zに圧縮し、decoderで潜在変数zからデータを生成します。
<br>
MNISTの手書き数字を生成するシンプルなモデルを構築しています。
<br>
![VAE_Model](https://github.com/pometa0507/Variational-Autoencoder-Numpy/blob/master/plots/VAE_Model.png)


<br>

# 損失関数

VAEの損失が関数は下記の2つの損失の和となります。
<br>
（詳細の理論は割愛しますが、変分下限に負をかけたものを損失関数としています。）
1) 入力データと生成データの負の対数尤度であるReconstruction Error（復元誤差）
2) 潜在変数zの分布の標準正規分布とのKLダイバージェンス

![Total_Loss](https://github.com/pometa0507/Variational-Autoencoder-Numpy/blob/master/plots/Total_Loss.png)

<br>
それぞれの損失関数の計算グラフで誤差逆伝播した勾配は下記となります。
<br>
EncoderとDecoderはこの勾配を逆伝播させることで求めています。

<br>

![ReconstructionError](https://github.com/pometa0507/Variational-Autoencoder-Numpy/blob/master/plots/ReconstructionError.png)

<br>

![DKL](https://github.com/pometa0507/Variational-Autoencoder-Numpy/blob/master/plots/DKL.png)
