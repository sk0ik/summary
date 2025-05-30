# 研究概要

- [はじめに](#はじめに)
- [スカラービーム](#スカラービーム)
- [ベクトルビーム](#ベクトルビーム)
- [空間光変調素子](#空間光変調素子)
- [実験光学系](#実験光学系)
- [目標](#目標)
- [なぜこうなるのか](#なぜこうなるのか)
- [収差補正](#収差補正)
- [課題](#課題)
- [展望](#展望)

## はじめに

自分は光の分野のベクトルビームというものについて研究しています.特に空間光変調素子:SLM(Spatial Light Modulator)という光学素子を用いてベクトルビームを高精度で生成する研究をしています.

光は波としての性質も持ちますが以下のように電場と磁場が直交して振動しながら伝播していきます.

</br>

<div align="center">

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/crop_resize_EMwave.gif)|
|:---:|
| 光の伝播の様子 |

</div>

</br>

※以下では電場について考えていきます.上図のように電場と磁場は直交しているので磁場を考えるときは直交成分を考えれば良いです.

高校の物理でも波の運動としてばねや振り子を考えており振幅と周波数という2つの自由度がありましたが光も同様に自由度を持ち

- 振幅
- 位相
- 時間周波数(単位時間当たりの波の数)
- 空間周波数(単位長さ当たりの波の数)
- 振動方向

のような自由度があります.自分はこの中でも光の振動方向を考える **偏光** という分野について研究をしています.例えば上記で挙げた自由度は以下のような光を考えることに対応しています.

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/Ewave_normal.gif) | ![GIF2](https://github.com/sk0ik/vector_beam/blob/main/Ewave_amp.gif) | ![GIF3](https://github.com/sk0ik/vector_beam/blob/main/Ewave_phase.gif) | ![GI43](https://github.com/sk0ik/vector_beam/blob/main/Ewave_freq.gif) |
|:---:|:---:|:---:|:---:|
| 元の電場 | 振幅が大きくなったもの | 位相が進んだもの | (時間もしくは空間)周波数が大きくなったもの |

</br>

高校の物理ではばねや振り子の運動を1次元上で考えており振動方向は考えていませんでした.振動方向を考えることによって

- レーザー加工
- 光トラッピング
- スピントロニクス

などの分野に応用されています.

以下では振動方向を考える際,以下のような方向から光を見るとします.

<p align="center">
<img src="https://github.com/sk0ik/vector_beam/blob/main/polarization_direction.png" alt="サンプル画像" width="600">
</p>

+z方向に伝播している光を+z方向から観測します.振動方向という幾何学的な話なので見る方向を指定しないと状態が変わってしまうためです.

## スカラービーム

一般的に用いられるビーム(ここではスカラービームと呼びます.)は断面内で偏光状態が一様です.例えば直線偏光や円偏光はスカラービームです.直線偏光はなんとなく想像しやすいですが円偏光はどうでしょうか？円偏光は光の振動方向が時間的に(もしくは伝播距離的に)変化しているものを指します.以下にスカラービームの例を示します.

※光は紙面裏から表に向かって進んでおりその断面での電場の振動の様子を描画しています.

</br>

<div align="center">

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/+0.gif) | ![GIF2](https://github.com/sk0ik/vector_beam/blob/main/+90.gif) |
|:---:|:---:|
| +0度偏光 | +90度偏光 |

</br>

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/+45.gif) | ![GIF2](https://github.com/sk0ik/vector_beam/blob/main/+135.gif) |
|:---:|:---:|
| +45度偏光 | -45度偏光 |

</br>

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/lcp.gif) | ![GIF2](https://github.com/sk0ik/vector_beam/blob/main/rcp.gif) |
|:---:|:---:|
| 左回り円偏光 | 右回り円度偏光 |

</div>

</br>

振動の様子はすべて異なりますが断面内ではすべて一様に振動していることが分かります.

## ベクトルビーム

次にベクトルビームの例を示します.同様に光は紙面裏から表に向かって進んでいます.

</br>

<div align="center">

| ![GIF1](https://github.com/sk0ik/vector_beam/blob/main/radial.gif) | ![GIF2](https://github.com/sk0ik/vector_beam/blob/main/azimuthal.gif) |
|:---:|:---:|
| ラジアル偏光ビーム | アジマス偏光ビーム |

</div>

</br>

上図のようにベクトルビームは電場の振動方向が位置によって異なります.また,上図に示したラジアル偏光やアジマス偏光と呼ばれるベクトルビームは断面内で軸対称になっています.これを軸対称ベクトルビームと言います.もちろん,軸対称でなくても不一様な偏光分布であればベクトルビームに分類されます.

## 空間光変調素子

私の研究ではベクトルビームを生成する際に空間光変調素子:Spatial Light Modulator(SLM)を用いています.

以下にSLMの概念図を示します.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/slm.png" alt="サンプル画像" width="700">
</p>

私はLiquid Crystal On Silicon Spatial Light Modulator(LCOS-SLM)というSLMを使用しています.

[SLM-250]([https://www.santec.com/jp/products/components/slm/slm-250/](https://www.santec.com/jp/products/components/slm/))

左図はその断面図で右図が私が実際に使用しているものです.このディスプレイのようなもの(横15mm,縦10mm)に光を当てて光の位相を変調します.このディスプレイは1920x1200ピクセルの液晶分子から構成されており,その一つ一つを電圧をかけることによって液晶分子の傾きを変えることができます.液晶が傾くと光が液晶内を通る距離が長くなり光の速度が遅くなります.つまり,傾けていない時と比べて光の位相は遅れます.先ほどのベクトルビームは光の偏光状態を空間的に制御するものですのでこのような原理からSLMを用いてベクトルビームを生成することができます.電圧をどこにどれだけの量をかけるのかを決めるのは右図にある白黒の模様です.これはホログラム,特に計算機ホログラムと呼ばれています.黒が0rad,白が2πradに対応しており,この間を1024諧調で変化させることができます.上図のホログラムは0-1023の整数値がらせん状に並べられています.

## 実験光学系

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/setup1.png" alt="サンプル画像" width="700">
</p>

上記の光学系でベクトルビームを生成することができます.1台のSLMを左右に分割し,右側をSLM1,左側をSLM2としています.また, $\theta_1,\theta_2,\theta_3$ をそれぞれHWP2,QWP1,QWP2を回す角度とし, $\theta_1=\frac{\pi}{8},\theta_2=\frac{\pi}{4},\theta_3=-\frac{\pi}{4}$ の時,ジョーンズベクトルは

$$
E _ {out}=e^{i(\delta_1+\frac{\pi}{2})}
\begin{bmatrix}
1 \newline
-i
\end{bmatrix}+e^{i\delta_2}
\begin{bmatrix}
1 \newline
i
\end{bmatrix}
$$

となります. $\delta_1,\delta_2$ はそれぞれSLM1,2によって付与された位相項です.

さらに, $\varphi$ を方位角とし,SLMに

$$
\delta _ 1=\varphi-\frac{\pi}{2},\delta _ 2=-\varphi
$$

というホログラム

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/radial_hologram.png" alt="サンプル画像" width="700">
</p>

を表示すれば

$$
E _ {out}=
\begin{bmatrix}
\cos{\varphi} \newline
\sin{\varphi}
\end{bmatrix}
$$

というジョーンズベクトルが得られます.これはラジアル偏光ビームと呼ばれています.自分の研究では主にこのラジアル偏光ビームについて考えていきます.

## 目標

ラジアル偏光ビームをシミュレーションによって生成した結果を示します.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/radial_sim.png" alt="サンプル画像" width="700">
</p>

上段の左右はそれぞれ左回り円偏光,右回り円偏光の初期振幅,初期位相を表しており下段はそれらをフーリエ変換したものを足し合わせた結果です.矢印はそのビームの偏光状態を表しています.つまり下段の一番左は全光強度,真ん中は+90°に振動する光の光強度を表しています.

実験でこのようなビームを作ることが目標です.

実際に実験で生成してみると

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/radial_experiment.png" alt="サンプル画像" width="700">
</p>

のような結果となります.明らかに違うことがわかります.全体的に像がぼやけており偏光状態も特に+45°,-45°の成分が全く一致していないことがわかります.

## なぜこうなるのか

シミュレーションや実験では変調された光をレンズによってフーリエ変換することでラジアル偏光ビームを生成しています.フーリエ変換ですので位相状態が重要であることは予想できます.そこでSLMによって変調される前のビームの位相を測定します.シミュレーションではこの位相がフラット,つまり場所によって位相差が生じていないと想定しています.測定する光学系を以下に示します.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/setup2.png" alt="サンプル画像" width="700">
</p>

SH sensor(シャックハルトマンセンサー)によって位相を測定しています.ビームの位相を表すのはゼルニケ多項式を用いるのが一般的です.測定した位相をゼルニケ多項式の重ね合わせで表した時の各係数を棒グラフにしたものを以下に示します.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/zer_bar.png" alt="サンプル画像" width="600">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/zer_table.png" alt="サンプル画像" width="300">
</p>

左図は各ゼルニケ多項式の係数,右図はそれらの多項式がどのような数式かを表しています.一般にはこの余計な位相は収差と呼ばれています.

ここで今考えているのはビームの形状ですので1番のピストン,2,3番のティルト,5番の球面収差は考えなくて良いです.そのように考えると4,6番の収差の影響が強いことがわかります.この収差は非点収差(astigmatism)と呼ばれており
その名の通り光が1点に集まらないという悪影響を及ぼします.

## 収差補正

これを踏まえてシミュレーション上でこの非点収差を加えた時にラジアル偏光ビームを生成した結果を示します.

<p align="center">
<img src="https://github.com/sk0ik/vector_beam/blob/main/zer_radial_simulatioh.png" alt="サンプル画像" width="700">
</p>

これは実験で得られた結果と似ていることがわかります.つまりこの非点収差をなくすことができれば光強度と偏光状態を改善できることが予想されます.それを踏まえて実験した結果を以下に示します.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/zer_radial_experiment.png" alt="サンプル画像" width="700">
</p>

収差補正をしない場合と比べて光強度や偏光状態が改善できていることがわかります.

## 課題

偏光状態はかなり理想的なものになりましたが,光強度には偏りがあります.特に+0°偏光成分では左右でかなり光強度に違いがあることがわかるかと思います.これは非点収差以外の収差によるものだと考えられます.例えば非点収差以外の収差が加わることで以下のような悪影響を及ぼします.

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/zer_table2.png" alt="サンプル画像" width="300">
</p>

<div style="display: flex; justify-content: center; align-items: flex-start; gap: 20px;">
  
  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/normal.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>なし</figcaption>
  </figure>
  
  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/4.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>4</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/6.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>6</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/7.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>7</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/8.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>8</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/9.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>9</figcaption>
  </figure>
  
</div>


<div style="display: flex; justify-content: center; align-items: flex-start; gap: 20px;">

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/10.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>10</figcaption>
  </figure>
  
  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/11.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>11</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/12.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>12</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/14.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>14</figcaption>
  </figure>

  <figure style="margin: 0; text-align: center;">
    <img src="https://github.com/sk0ik/vector_beam/blob/main/15.bmp?raw=true" alt="サンプル画像" width="100">
    <figcaption>15</figcaption>
  </figure>

  今回補正したのは上図でいう4,6番です.
  
</div>

## 展望

今回使用している光学系ではSLMに対してビームが斜めに入射していたり,SLM1,2間が回折しながら伝播しています.これらがどのような影響を調べることが今後の展望です.

追記:2025年05/22に新たな光学系を組みました.右図はSLM付近での光学系の実際の写真です.(ビームスプリッターを4回通るので光は1/16になってしまいます...)

<p align="center">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/setup3.png" alt="サンプル画像" width="500">
<img src="https://github.com/sk0ik/Vector_Beam/blob/main/real_setup3.png" alt="サンプル画像" width="300">
</p>

これはSLMに垂直にビームが入射しており,かつ,SLM1,2間も4f光学系により結像関係にあるので回折伝播もしていないです.よってこの状況を基準にし,回折はさせずに斜めに入射させたり,垂直に入射させるが回折は起こる,のような状況での実験を行いたいと考えています.
