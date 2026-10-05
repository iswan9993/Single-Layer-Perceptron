#### Single Layer Perceptron

<p align="justify" style="text-indent:1.27cm">Single Layer Perceptron (SLP) terinspirasi oleh neuron biologis dan kemampuannya untuk memproses informasi. SLP didasarkan pada konsep neuron buatan, yang bertindak sebagai blok bangunan dasar jaringan saraf dan memproses input untuk menghasilkan output.</p>

<p align="center"><img src="/Image/SLP-1.png"></p>
<p>Cara kerja:</p>

<ol style="padding-left: 20px;">
  <li>Menerima sinyal input dari data eksternal. </li>
  <li>Setiap input dikalikan dengan bobot (weight) dan di tambahkan dengan bias.</li>
  <li>Hasil penjumlahan tersebut dimasukkan ke dalam fungsi aktivasi untuk menentukan nilai output akhir.</li>
</ol>
<p>Perhatikan alur SLP pada gambar berikut:</p>
<p align="center"><img src="/Image/SLP-2.png"></p>
<p align="justify">Untuk mendapatkan hasil dari Weighted Sum h(x,w,b) kita menggunakan persamaan
h(x,w,b) = w<sub>1</sub>x<sub>1</sub> + w<sub>2</sub>x<sub>2</sub>...w<sub>n</sub>x<sub>n</sub> + b , dimana b sebagai bias. h(x,w,b) = w<sup>T</sup>x + b, dan fungsi aktivasi yang digunakan adalah sigmoid, dengan persamaan $g(z)=\frac{1}{1 + \exp(-z)}$ , sehingga h(x,w,b) = g(w<sup>T</sup>x + b), kita dapat melakukan update bobot dengan persamaan w<sub>baru</sub> = w<sub>lama</sub> - μ∆w, dan update biasnya b<sub>baru</sub>= b<sub>lama</sub> - μ∆b, μ sebagai learning rate, dan untuk mencari ∆w kita menggunakan persamaan:
</p>
<p align="center">

$$
\begin{aligned}
\Delta w &= \frac{\partial}{\partial w_n}(h(x,w,b)-y)^2 \\
         &= 2(h(x,w,b)-y)\frac{\partial }{\partial w_n} h(x,w,b)\\
         &= 2(g(w^Tx+b)-y)\frac{\partial }{\partial w_n} g(w^Tx+b), \,\text{dimana} \,\frac{\partial }{\partial w_n} g(w^Tx+b) \, \text{diturunkan menjadi:} \\
         & \frac{\partial }{\partial w_n} g(w^Tx+b) = \frac{\partial g(w^Tx+b)}{\partial (w^Tx + b)} \frac{\partial (w^Tx + b)}{\partial w_n}\\
         &=[1-g(w^Tx+b)]g(w^Tx+b) \frac{\partial(w_nx_n + w_{n+1} x_{n+1}+b)}{\partial w_n}\\
         &=[1-g(w^Tx+b)]g(w^Tx+b)x_n\text{, sehingga persamaan lengkapnya menjadi}\\
         &\Delta w =2[g(w^Tx+b)-y][1-g(w^Tx+b)]g(w^Tx+b)x_n\\
         &\Delta b =2[g(w^Tx+b)-y][1-g(w^Tx+b)]g(w^Tx+b)\\
         & E= \sum_t (y_t - T_t)^2
\end{aligned}
$$

</p>

#### Hasil

<p style="text-indent:1.27cm" align="justify"> pada perhitungan ini saya menggunakan beberapa percobaan untuk dapat membuktikan keakuratan perhitungan manual algoritma SLP.</p>

##### 1. perhitungan Ms.Exel dengan Learning Rule Based

<p style="text-indent:1.27cm" align="justify">Perceptron learning rule itu adalah aturan atau cara yang dipakai perceptron untuk belajar dari data. Intinya, perceptron awalnya menebak output, lalu kalau tebakannya salah, bobotnya (weight) diperbaiki sedikit demi sedikit sampai tebakannya benar.pada percobaan ini saya menggunakan $w_1 =0.2, w_2=0.2,w_3=0.2, Threshold=75, \text{ dan } μ=0.005$, pada <a href="Code/Perceptron%20Learning%20Rule%20Based-SLP.csv">perceptron_learning_rule.csv</a>, $v=w_1x_1+w_2x_2+w_3x_3,\text{}$$Y'=1,$ IF $v >=\text{theshold}$  dan $Y'=0,$ IF $v <\text{theshold}.$ Sedangkan errornya adalah selisih antara $Y$dan $Y'.$</p>
<p></p>
<p></p>
<sub></sub>
<sup></sup>
