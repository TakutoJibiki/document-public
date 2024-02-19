[戻る](./README.md)
# ガウス関数のパラメータ表現
## 共分散行列の固有値分解
確率変数 $\bm{x}\in\mathcal{R}^n$ に対する共分散行列 $\Sigma\in\mathcal{R}^{n\times n}$ は次式で定義される．
$$
\begin{align}
\Sigma =&\; E\left[(\bm{x}-\bm{\mu})(\bm{x}-\bm{\mu})^T\right]\\
\bm{\mu}=&\; E[\bm{x}]
\end{align}
$$
ここで，$E[\:\cdot\:]$ は期待値をあらわす．$\Sigma$ は次のように直交化できる．
$$
\begin{align}
U^{-1}\Sigma U = \Lambda
\end{align}
$$
ここで，$U\in\mathcal{R}^{n\times n}$ は $\Sigma$ の固有ベクトルを並べた行列であり，$\Sigma$ が対称行列のため $U$ は対角行列である※1．また，$\Lambda\in\mathcal{R^{n\times n}}$ は $\Sigma$ の固有値を並べた対角行列である．式$(3)$は次のように変形できる（固有値分解）※2．
$$
\begin{equation}
\Sigma = U\Lambda U^T
\end{equation}
$$

## ガウス関数の幾何学
$n$ 次のガウス関数は次式で与えられる．
$$
\begin{equation}
G(\bm{x})=\frac{1}{\sqrt{(2\pi)^n \det{\Sigma}}}\exp{\left\{-\frac{1}{2}(\bm{x}-\bm{\mu})^T\Sigma^{-1}(\bm{x}-\bm{\mu})\right\}}
\end{equation}
$$
ガウス関数の等高線は指数部を定数と置くことで次式のように与えられる．
$$
\begin{equation}
\bm{y}^T\Sigma^{-1}\bm{y} = \rm{const.}
\end{equation}
$$
ここで，$\bm{y} = \bm{x}-\bm{\mu}$ としている．式$(4)$は次のように変形できる※3．
$$
\begin{align}
\Sigma =&\; U\Lambda U^T \notag \\
=&\; U\Lambda^{1/2} \left(U\Lambda^{1/2}\right)^T \notag \\
=&\; CC^T
\end{align}
$$
ここで，$C = U\Lambda^{1/2}$ と置いている．式$(6)$において $\bm{y}=C\bm{z}$とおくと次のようになる．
$$
\begin{align}
\bm{y}^T\Sigma^{-1}\bm{y} =&\; (C\bm{z})^T\left(CC^T\right)^{-1}C\bm{z} \notag \\
=&\; \bm{z}^TC^T\left(C^T\right)^{-1}C^{-1}C\bm{z} \notag \\
=&\; \bm{z}^T\bm{z} = \rm{const.}
\end{align}
$$
式$(8)$は $\bm{z}=(z_1, z_2, ...)^T$ に関する円（$n$ 次元球面）の方程式にほかならない．$\bm{x}$ と $\bm{z}$ の関係は次のようにあらわされる．
$$
\begin{equation}
\bm{x} = \bm{y} + \bm{\mu} = C\bm{z} + \bm{\mu} = U\Lambda^{1/2}\bm{z}+\bm{\mu}
\end{equation}
$$
ここで，$U$ が直交行列，$\Lambda$ が対角行列，$\bm{\mu} \in \mathcal{R^{n}}$ が実数ベクトルであることから，$(5)$のガウス関数の等高線は円を拡大縮小，回転，平行移動した形，つまり楕円となる※4．

## 形状パラメータによるガウス関数の表現
式$(9)$より，$n=2, \bm{x}=(x, y)^T$ のときのガウス関数の $\bm{\mu}$ と $\Sigma$ は，次のようにあらわすことができる．
$$
\begin{align}
\bm{\mu} =&\; (\mu_x, \mu_y)^T \\
\Sigma =&\; U\Lambda U^T \\
U =&\; \left(
    \begin{matrix}
        \cos{\theta} & -\sin{\theta} \\
        \sin{\theta} & \cos{\theta}
    \end{matrix}
\right) \\
\Lambda =&\; \left(
    \begin{matrix}
        s_x^2 & 0 \\
        0 & s_y^2
    \end{matrix}
\right) \\
\end{align}
$$
ここで，$(\mu_x, \mu_y)$ はガウス関数の中心座標，$(s_x, s_y)$ は半径，$\theta$ は回転角である．

***

※1　$\left((\bm{x}-\bm{\mu})(\bm{x}-\bm{\mu})^T\right)^T = (\bm{x}-\bm{\mu})(\bm{x}-\bm{\mu})^T$ であることから $\Sigma$ は対称行列である．<br>
※2　直交行列の性質 $A^{-1} = A^T$ を使用した．<br>
※3　$A=\rm{diag}(a_1, a_2, ...)$ に対して $A^{1/2}=\rm{diag}(\sqrt{a_1}, \sqrt{a_2}, ...)$ と定義する．<br>
※4　式$(6)$において $\bm{y} = U\bm{y}'$ と置くことで楕円の方程式を導出できる．