# Poincaré不等式证明

- Conversation ID: `6909f24e-bedc-832b-ac02-958fed15feab`

## Question

f(x)\in C^{1} [0,1]。f(0)=0,f(1) = 0。
请证明：\int_{0}^{1} (f(x))^2dx \le \frac{1}{\pi^2} \int_{0}^{1} (f'(x))^2dx

## Answer

这是区间 $[0,1]$ 上的 Poincaré（或 Wirtinger）不等式。给出两种常见且干净的证明：傅里叶正弦展开法与变分（Rayleigh 商）法。

方法一（正弦傅里叶展开）
由于 $f\in C^1[0,1]$ 且 $f(0)=f(1)=0$，可以在正交标准化基函数

```math
\varphi_n(x)=\sqrt{2}\sin(n\pi x)\quad(n=1,2,\dots)
```

上展开（在 $L^2$ 意义下收敛）：

```math
f(x)=\sum_{n=1}^\infty \alpha_n\varphi_n(x),
\qquad \alpha_n=\int_0^1 f(x)\varphi_n(x)\,dx.
```

由 Parseval 恒等式，

```math
\int_0^1 f(x)^2\,dx=\sum_{n=1}^\infty \alpha_n^2.
```

对导数，有 $\varphi_n'(x)=\sqrt{2}\,n\pi\cos(n\pi x)$，因此

```math
\int_0^1 (f'(x))^2\,dx=\sum_{n=1}^\infty \alpha_n^2 (n\pi)^2.
```

因为对所有 $n\ge1$ 有 $(n\pi)^2\ge\pi^2$，所以

```math
\sum_{n=1}^\infty \alpha_n^2
\le\frac{1}{\pi^2}\sum_{n=1}^\infty \alpha_n^2 (n\pi)^2.
```

即

```math
\int_0^1 f(x)^2\,dx \le \frac{1}{\pi^2}\int_0^1 (f'(x))^2\,dx.
```

当且仅当只有 $n=1$ 项非零（即 $f(x)=C\sin(\pi x)$）时等号成立。

方法二（变分 / 最小特征值）
考虑 Rayleigh 商

```math
R[f]=\frac{\int_0^1 (f')^2}{\int_0^1 f^2},
```

在 $f(0)=f(1)=0$ 的空间中，R[f] 的最小值等于边值问题

```math
-y''=\lambda y,\quad y(0)=y(1)=0
```

的最小特征值。该特征值为 $\lambda_1=\pi^2$，对应特征函数 $\sin(\pi x)$。因此对任意满足边界条件的非零 $f$ 有

```math
\frac{\int_0^1 (f')^2}{\int_0^1 f^2}\ge\pi^2,
```

即

```math
\int_0^1 f^2 \le \frac{1}{\pi^2}\int_0^1 (f')^2.
```

两种方法所得结论相同，并且等号在 $f(x)=C\sin(\pi x)$ 时取得。证毕。

