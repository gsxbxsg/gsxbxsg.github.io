---
title: 高数速成复习 附录：公式速查表
published: 2026-10-04
description: 把 01～15 篇的必背公式和关键结论按章节整理在一页，适合考前最后一周快速过一遍。每节末尾附原文链接，忘了推导时回去看。
tags: [高等数学, 考研数学一, 公式, 速查表]
category: 高数速成复习
series: 高数速成复习
seriesOrder: 16
---

这一篇是整个系列的公式汇总，**只列公式和结论，不讲推导**。建议用法：

1. 考前最后一周，每天从头到尾过一遍；
2. 看到哪一条觉得陌生，点节末的链接回到原文，看例题；
3. 做真题时把这一页开在旁边，养成“先想用哪个公式”的习惯。

标 **(数一)** 的内容只有数学一考。

## 一、函数、极限与连续

### 1. 重要极限

$$
\lim_{x\to0}\frac{\sin x}{x}=1,\qquad\lim_{x\to0}(1+x)^{\frac1x}=e,\qquad\lim_{x\to\infty}\left(1+\frac1x\right)^x=e.
$$

$1^\infty$ 型：$\lim u^v=e^{\lim v(u-1)}$（$u\to1$，$v\to\infty$）。

### 2. 等价无穷小（$x\to0$）

| 等价于 $x$ | 其他 |
| --- | --- |
| $\sin x$、$\tan x$、$\arcsin x$、$\arctan x$ | $1-\cos x\sim\dfrac12x^2$ |
| $\ln(1+x)$、$e^x-1$ | $(1+x)^\alpha-1\sim\alpha x$ |
| | $a^x-1\sim x\ln a$ |
| | $x-\sin x\sim\dfrac16x^3$，$\tan x-x\sim\dfrac13x^3$ |
| | $x-\ln(1+x)\sim\dfrac12x^2$，$\tan x-\sin x\sim\dfrac12x^3$ |

**加减中不能随意替换**，乘除中可以。

### 3. 常用麦克劳林公式

$$
e^x=1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+o(x^3),\qquad\ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}+o(x^3),
$$

$$
\sin x=x-\frac{x^3}{6}+o(x^3),\qquad\cos x=1-\frac{x^2}{2}+\frac{x^4}{24}+o(x^4),
$$

$$
\tan x=x+\frac{x^3}{3}+o(x^3),\qquad\arctan x=x-\frac{x^3}{3}+o(x^3),\qquad(1+x)^\alpha=1+\alpha x+\frac{\alpha(\alpha-1)}{2}x^2+o(x^2).
$$

### 4. 无穷大的比较（$x\to+\infty$）

$$
\ln^\alpha x\ll x^\beta\ll a^x\ll x^x\qquad(\alpha,\beta>0,\ a>1).
$$

数列：$\ln n\ll n^\beta\ll a^n\ll n!\ll n^n$。

### 5. 数列极限

- **单调有界准则**：单调有界数列必有极限。递推数列 $x_{n+1}=f(x_n)$ 先证有界、再证单调，最后在递推式两边取极限。
- **夹逼准则**：$y_n\le x_n\le z_n$，$y_n,z_n\to A$，则 $x_n\to A$。
- $\displaystyle\lim_{n\to\infty}\sqrt[n]{a}=1\ (a>0)$，$\displaystyle\lim_{n\to\infty}\sqrt[n]{n}=1$。

### 6. 间断点

| 类型 | 条件 |
| --- | --- |
| 可去 | 左右极限存在且相等，但不等于函数值（或无定义） |
| 跳跃 | 左右极限存在但不相等 |
| 无穷 | 至少一侧极限为 $\infty$ |
| 振荡 | 极限振荡不存在，如 $\sin\dfrac1x$ 在 $x=0$ |

前两种是第一类，后两种是第二类。

### 7. 闭区间上连续函数的性质

最值定理、有界性定理、介值定理、**零点定理**（$f(a)f(b)<0\Rightarrow$ 存在 $\xi\in(a,b)$，$f(\xi)=0$）。

详见 [01 函数、极限与连续](/posts/gaoshu-01-limit/)。

## 二、导数与微分

### 1. 导数定义

$$
f'(x_0)=\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}.
$$

可导 $\iff$ 左右导数存在且相等；可导 $\Rightarrow$ 连续；一元函数**可导 $\iff$ 可微**。

### 2. 基本求导公式

| 函数 | 导数 | 函数 | 导数 |
| --- | --- | --- | --- |
| $x^\mu$ | $\mu x^{\mu-1}$ | $\sin x$ | $\cos x$ |
| $a^x$ | $a^x\ln a$ | $\cos x$ | $-\sin x$ |
| $e^x$ | $e^x$ | $\tan x$ | $\sec^2x$ |
| $\log_ax$ | $\dfrac{1}{x\ln a}$ | $\cot x$ | $-\csc^2x$ |
| $\ln x$ | $\dfrac1x$ | $\sec x$ | $\sec x\tan x$ |
| $\arcsin x$ | $\dfrac{1}{\sqrt{1-x^2}}$ | $\csc x$ | $-\csc x\cot x$ |
| $\arccos x$ | $-\dfrac{1}{\sqrt{1-x^2}}$ | $\arctan x$ | $\dfrac{1}{1+x^2}$ |
| $\ln\left(x+\sqrt{x^2\pm a^2}\right)$ | $\dfrac{1}{\sqrt{x^2\pm a^2}}$ | $\operatorname{arccot}x$ | $-\dfrac{1}{1+x^2}$ |

### 3. 求导法则

- **复合函数**：$\bigl(f(g(x))\bigr)'=f'(g(x))\cdot g'(x)$。
- **反函数**：$\dfrac{\mathrm dx}{\mathrm dy}=\dfrac{1}{\mathrm dy/\mathrm dx}$，$\dfrac{\mathrm d^2x}{\mathrm dy^2}=-\dfrac{y''}{(y')^3}$。
- **参数方程**：$\dfrac{\mathrm dy}{\mathrm dx}=\dfrac{y'(t)}{x'(t)}$，$\dfrac{\mathrm d^2y}{\mathrm dx^2}=\dfrac{y''x'-y'x''}{(x')^3}$。
- **隐函数**：两边对 $x$ 求导，$y$ 看成 $x$ 的函数。
- **对数求导法**：幂指函数 $u^v$、多个因子连乘除，先取对数。

### 4. 高阶导数

$$
(\sin x)^{(n)}=\sin\left(x+\frac{n\pi}{2}\right),\qquad(\cos x)^{(n)}=\cos\left(x+\frac{n\pi}{2}\right),
$$

$$
\left(\frac{1}{x+a}\right)^{(n)}=\frac{(-1)^nn!}{(x+a)^{n+1}},\qquad\bigl(\ln(1+x)\bigr)^{(n)}=\frac{(-1)^{n-1}(n-1)!}{(1+x)^n}.
$$

**莱布尼茨公式**：$(uv)^{(n)}=\displaystyle\sum_{k=0}^n\mathrm C_n^ku^{(k)}v^{(n-k)}$。

**用泰勒展开求 $f^{(n)}(0)$**：$x^n$ 的系数 $=\dfrac{f^{(n)}(0)}{n!}$。

详见 [02 导数与微分](/posts/gaoshu-02-derivative/)。

## 三、微分中值定理

| 定理 | 条件 | 结论 |
| --- | --- | --- |
| 费马 | $x_0$ 是极值点，$f$ 在 $x_0$ 可导 | $f'(x_0)=0$ |
| 罗尔 | $[a,b]$ 连续，$(a,b)$ 可导，$f(a)=f(b)$ | $\exists\xi$，$f'(\xi)=0$ |
| 拉格朗日 | $[a,b]$ 连续，$(a,b)$ 可导 | $f(b)-f(a)=f'(\xi)(b-a)$ |
| 柯西 | 同上，且 $g'\ne0$ | $\dfrac{f(b)-f(a)}{g(b)-g(a)}=\dfrac{f'(\xi)}{g'(\xi)}$ |

**泰勒公式**（拉格朗日余项）：

$$
f(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k+\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}.
$$

**常用辅助函数**：

| 要证的结论 | 辅助函数 |
| --- | --- |
| $f'(\xi)+\lambda f(\xi)=0$ | $F=e^{\lambda x}f(x)$ |
| $f'(\xi)+g'(\xi)f(\xi)=0$ | $F=e^{g(x)}f(x)$ |
| $\xi f'(\xi)+kf(\xi)=0$ | $F=x^kf(x)$ |
| $f'(\xi)g(\xi)+f(\xi)g'(\xi)=0$ | $F=f(x)g(x)$ |
| $f'(\xi)g(\xi)-f(\xi)g'(\xi)=0$ | $F=\dfrac{f(x)}{g(x)}$ |

**双中值**（$\xi,\eta$）：常用两次拉格朗日，或拉格朗日 + 柯西；要求 $\xi\ne\eta$ 时，先把区间分成两段。

详见 [03 微分中值定理](/posts/gaoshu-03-mvt/)。

## 四、导数的应用

### 1. 单调性与极值

- $f'>0$ 递增，$f'<0$ 递减。
- **第一充分条件**：$f'$ 在 $x_0$ 两侧变号。
- **第二充分条件**：$f'(x_0)=0$，$f''(x_0)>0$ 为极小，$f''(x_0)<0$ 为极大。

### 2. 凹凸性与拐点

- $f''>0$ **凹**（向上凹，像 $\cup$），$f''<0$ **凸**。（同济、考研约定；部分教材相反。）
- 拐点：$f''$ 在该点两侧变号。拐点是曲线上的**点** $(x_0,f(x_0))$。

### 3. 渐近线

| 类型 | 条件 |
| --- | --- |
| 水平 | $\lim\limits_{x\to\infty}f(x)=b$，渐近线 $y=b$ |
| 铅直 | $\lim\limits_{x\to x_0}f(x)=\infty$，渐近线 $x=x_0$ |
| 斜 | $k=\lim\limits_{x\to\infty}\dfrac{f(x)}{x}$，$b=\lim\limits_{x\to\infty}\bigl[f(x)-kx\bigr]$ |

$x\to+\infty$ 和 $x\to-\infty$ 要**分别**算。

### 4. 曲率

$$
K=\frac{\lvert y''\rvert}{(1+y'^2)^{3/2}},\qquad R=\frac1K.
$$

### 5. 不等式与方程根

- **证明不等式**：移项构造 $F(x)$，用单调性、最值或泰勒公式。
- **方程根的个数**：零点定理找存在性，单调性证唯一性；含参数时求 $f$ 的极值，看参数与极值的关系。

详见 [04 导数的应用](/posts/gaoshu-04-applications/)。

## 五、不定积分

### 1. 基本积分公式

| 被积函数 | 原函数 | 被积函数 | 原函数 |
| --- | --- | --- | --- |
| $x^\mu\ (\mu\ne-1)$ | $\dfrac{x^{\mu+1}}{\mu+1}$ | $\dfrac1x$ | $\ln\lvert x\rvert$ |
| $a^x$ | $\dfrac{a^x}{\ln a}$ | $\tan x$ | $-\ln\lvert\cos x\rvert$ |
| $\sec x$ | $\ln\lvert\sec x+\tan x\rvert$ | $\csc x$ | $\ln\lvert\csc x-\cot x\rvert$ |
| $\sec^2x$ | $\tan x$ | $\csc^2x$ | $-\cot x$ |
| $\dfrac{1}{a^2+x^2}$ | $\dfrac1a\arctan\dfrac xa$ | $\dfrac{1}{\sqrt{a^2-x^2}}$ | $\arcsin\dfrac xa$ |
| $\dfrac{1}{x^2-a^2}$ | $\dfrac{1}{2a}\ln\left\lvert\dfrac{x-a}{x+a}\right\rvert$ | $\dfrac{1}{\sqrt{x^2\pm a^2}}$ | $\ln\left\lvert x+\sqrt{x^2\pm a^2}\right\rvert$ |

所有结果都要 $+C$。

$$
\int\sqrt{a^2-x^2}\,\mathrm dx=\frac x2\sqrt{a^2-x^2}+\frac{a^2}{2}\arcsin\frac xa+C.
$$

### 2. 方法

- **第一换元（凑微分）**：$\displaystyle\int f(\varphi(x))\varphi'(x)\,\mathrm dx=\int f(u)\,\mathrm du$。
- **第二换元**：

| 被积函数含 | 代换 |
| --- | --- |
| $\sqrt{a^2-x^2}$ | $x=a\sin t$ |
| $\sqrt{a^2+x^2}$ | $x=a\tan t$ |
| $\sqrt{x^2-a^2}$ | $x=a\sec t$ |
| $\sqrt[n]{ax+b}$ | $t=\sqrt[n]{ax+b}$ |
| $e^x$ 的有理式 | $t=e^x$ |

- **分部积分**：$\displaystyle\int u\,\mathrm dv=uv-\int v\,\mathrm du$。选 $u$ 的优先级：**反（三角）> 对（数）> 幂 > 指（数）、三（角）**。
- **有理函数**：分母因式分解，拆成部分分式。
- **三角有理式**：万能代换 $t=\tan\dfrac x2$，$\sin x=\dfrac{2t}{1+t^2}$，$\cos x=\dfrac{1-t^2}{1+t^2}$，$\mathrm dx=\dfrac{2\,\mathrm dt}{1+t^2}$（万不得已再用）。

### 3. 原函数存在性

连续函数一定有原函数；**有第一类间断点**的函数**没有原函数**。

详见 [05 不定积分](/posts/gaoshu-05-indefinite/)。

## 六、定积分与反常积分

### 1. 变限积分求导

$$
\frac{\mathrm d}{\mathrm dx}\int_{\psi(x)}^{\varphi(x)}f(t)\,\mathrm dt=f(\varphi(x))\varphi'(x)-f(\psi(x))\psi'(x).
$$

被积函数含 $x$：先提出或换元。

### 2. 积分中值定理

$$
\int_a^bf(x)\,\mathrm dx=f(\xi)(b-a);\qquad\int_a^bf(x)g(x)\,\mathrm dx=f(\xi)\int_a^bg(x)\,\mathrm dx\ (g\text{ 不变号}).
$$

### 3. 计算技巧

$$
\int_{-a}^af(x)\,\mathrm dx=\int_0^a\bigl[f(x)+f(-x)\bigr]\mathrm dx,\qquad\int_a^{a+T}f(x)\,\mathrm dx=\int_0^Tf(x)\,\mathrm dx\ (\text{周期 }T).
$$

**华里士公式**：

$$
\int_0^{\frac\pi2}\sin^nx\,\mathrm dx=\int_0^{\frac\pi2}\cos^nx\,\mathrm dx=\begin{cases}\dfrac{(n-1)!!}{n!!}\cdot\dfrac\pi2,&n\text{ 偶}\\[2mm]\dfrac{(n-1)!!}{n!!},&n\text{ 奇}\end{cases}
$$

**区间再现**：

$$
\int_a^bf(x)\,\mathrm dx=\int_a^bf(a+b-x)\,\mathrm dx,\qquad\int_0^\pi xf(\sin x)\,\mathrm dx=\frac\pi2\int_0^\pi f(\sin x)\,\mathrm dx.
$$

**定积分定义求极限**：$\displaystyle\lim_{n\to\infty}\frac1n\sum_{k=1}^nf\left(\frac kn\right)=\int_0^1f(x)\,\mathrm dx$。

### 4. 反常积分

$$
\int_1^{+\infty}\frac{\mathrm dx}{x^p}\text{：}p>1\text{ 收敛};\qquad\int_0^1\frac{\mathrm dx}{x^p}\text{：}p<1\text{ 收敛}.
$$

$$
\Gamma(n+1)=n!,\qquad\Gamma\left(\frac12\right)=\sqrt\pi,\qquad\int_0^{+\infty}e^{-x^2}\,\mathrm dx=\frac{\sqrt\pi}{2}.
$$

**有多个反常点时拆开，每段都收敛才收敛。有瑕点时不能直接用牛顿-莱布尼茨公式。**

详见 [06 定积分与反常积分](/posts/gaoshu-06-definite/)。

## 七、定积分的应用

| 量 | 公式 |
| --- | --- |
| 面积（直角坐标） | $\displaystyle\int_a^b\bigl[f(x)-g(x)\bigr]\mathrm dx$ |
| 面积（参数方程） | $\left\lvert\displaystyle\int_{t_1}^{t_2}y(t)x'(t)\,\mathrm dt\right\rvert$ |
| 面积（极坐标） | $\dfrac12\displaystyle\int_\alpha^\beta r^2(\theta)\,\mathrm d\theta$ |
| 绕 $x$ 轴体积 | $\pi\displaystyle\int_a^bf^2(x)\,\mathrm dx$ |
| 绕 $y$ 轴体积（柱壳） | $2\pi\displaystyle\int_a^bx\lvert f(x)\rvert\,\mathrm dx$ |
| 平行截面体积 | $\displaystyle\int_a^bA(x)\,\mathrm dx$ |
| 弧长 | $\displaystyle\int\sqrt{1+y'^2}\,\mathrm dx$、$\displaystyle\int\sqrt{x'^2+y'^2}\,\mathrm dt$、$\displaystyle\int\sqrt{r^2+r'^2}\,\mathrm d\theta$ |
| 旋转曲面面积 (数一) | $2\pi\displaystyle\int_a^b\lvert f(x)\rvert\sqrt{1+f'^2(x)}\,\mathrm dx$ |
| 形心 | $\bar x=\dfrac1A\displaystyle\int_a^bxf(x)\,\mathrm dx$，$\bar y=\dfrac1A\displaystyle\int_a^b\dfrac12f^2(x)\,\mathrm dx$ |
| 平均值 | $\dfrac{1}{b-a}\displaystyle\int_a^bf(x)\,\mathrm dx$ |

**物理应用 (数一)**：做功 $\mathrm dW=\rho g\,\mathrm dV\cdot(\text{提升距离})$；水压力 $\mathrm dF=\rho g\cdot\text{深度}\cdot\text{宽度}\,\mathrm dx$；引力方向不同要分解。

**常见曲线**：摆线一拱面积 $3\pi a^2$、弧长 $8a$；心形线 $r=a(1+\cos\theta)$ 面积 $\dfrac32\pi a^2$、周长 $8a$。

详见 [07 定积分的应用](/posts/gaoshu-07-applications/)。

## 八、常微分方程

### 1. 一阶方程

| 类型 | 形式 | 解法 |
| --- | --- | --- |
| 可分离 | $y'=f(x)g(y)$ | $\displaystyle\int\frac{\mathrm dy}{g(y)}=\int f(x)\,\mathrm dx$ |
| 齐次 | $y'=\varphi\left(\dfrac yx\right)$ | $u=\dfrac yx$，$y'=u+xu'$ |
| 一阶线性 | $y'+P(x)y=Q(x)$ | 公式法（见下） |
| 伯努利 | $y'+Py=Qy^n$ | $z=y^{1-n}$ |
| 全微分 | $P\,\mathrm dx+Q\,\mathrm dy=0$，$P_y=Q_x$ | 凑微分，通解 $u(x,y)=C$ |

$$
y=e^{-\int P\,\mathrm dx}\left[\int Qe^{\int P\,\mathrm dx}\,\mathrm dx+C\right].
$$

关于 $y$ 解不动时，试试把 $x$ 看成 $y$ 的函数。

### 2. 可降阶方程

| 类型 | 代换 |
| --- | --- |
| $y''=f(x,y')$（不含 $y$） | $p=y'$，$y''=p'$ |
| $y''=f(y,y')$（不含 $x$） | $p=y'$，$y''=p\dfrac{\mathrm dp}{\mathrm dy}$ |

### 3. 二阶常系数线性方程

特征方程 $r^2+pr+q=0$：

| 特征根 | 齐次通解 |
| --- | --- |
| $r_1\ne r_2$（实） | $C_1e^{r_1x}+C_2e^{r_2x}$ |
| $r_1=r_2=r$ | $(C_1+C_2x)e^{rx}$ |
| $\alpha\pm\beta i$ | $e^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)$ |

**特解形式**：

| 右端 $f(x)$ | 设 $y^*$ | $k$ |
| --- | --- | --- |
| $P_m(x)e^{\lambda x}$ | $x^kQ_m(x)e^{\lambda x}$ | $\lambda$ 是特征根的重数（0、1、2） |
| $e^{\alpha x}\bigl[P_l\cos\beta x+P_n\sin\beta x\bigr]$ | $x^ke^{\alpha x}\bigl[R_m\cos\beta x+S_m\sin\beta x\bigr]$ | $\alpha+\beta i$ 是特征根取 1，否则取 0 |

**简便代入**：$y^*=ue^{\lambda x}$ 时，$u''+(2\lambda+p)u'+(\lambda^2+p\lambda+q)u=P_m(x)$。

### 4. 解的结构

- 非齐次通解 $=$ 齐次通解 $+$ 非齐次特解；
- **非齐次的两个解之差是齐次的解**；
- 叠加原理：右端相加，特解相加。

### 5. 欧拉方程 (数一)

$x^2y''+pxy'+qy=f(x)$：令 $x=e^t$，$xy'=Dy$，$x^2y''=D(D-1)y$。

**积分方程**：两边求导化成微分方程，从原方程中取 $x=$ 积分下限，得到初始条件。

详见 [08 常微分方程](/posts/gaoshu-08-ode/)。

## 九、向量代数与空间解析几何 (数一)

### 1. 向量运算

| 运算 | 公式 | 几何意义与判定 |
| --- | --- | --- |
| 点乘 | $\boldsymbol a\cdot\boldsymbol b=\lvert\boldsymbol a\rvert\lvert\boldsymbol b\rvert\cos\theta$ | $\boldsymbol a\perp\boldsymbol b\iff\boldsymbol a\cdot\boldsymbol b=0$ |
| 叉乘 | $\begin{vmatrix}\boldsymbol i&\boldsymbol j&\boldsymbol k\\a_x&a_y&a_z\\b_x&b_y&b_z\end{vmatrix}$ | 平行四边形面积；$\boldsymbol a\parallel\boldsymbol b\iff$ 坐标成比例 |
| 混合积 | $(\boldsymbol a\times\boldsymbol b)\cdot\boldsymbol c$ | 平行六面体体积；为 0 $\iff$ 共面 |

方向余弦：$\cos^2\alpha+\cos^2\beta+\cos^2\gamma=1$。

### 2. 平面与直线

- 平面点法式：$A(x-x_0)+B(y-y_0)+C(z-z_0)=0$，**一般式的系数就是法向量**。
- 直线对称式：$\dfrac{x-x_0}{m}=\dfrac{y-y_0}{n}=\dfrac{z-z_0}{p}$；一般式（两平面交线）方向向量 $\boldsymbol n_1\times\boldsymbol n_2$。
- 平面束：$(A_1x+B_1y+C_1z+D_1)+\lambda(A_2x+B_2y+C_2z+D_2)=0$。

### 3. 夹角与距离

$$
\text{面面、线线：}\cos\theta=\frac{\lvert\boldsymbol n_1\cdot\boldsymbol n_2\rvert}{\lvert\boldsymbol n_1\rvert\lvert\boldsymbol n_2\rvert};\qquad\text{线面：}\sin\varphi=\frac{\lvert\boldsymbol s\cdot\boldsymbol n\rvert}{\lvert\boldsymbol s\rvert\lvert\boldsymbol n\rvert}.
$$

$$
\text{点到平面：}d=\frac{\lvert Ax_0+By_0+Cz_0+D\rvert}{\sqrt{A^2+B^2+C^2}};\qquad\text{点到直线：}d=\frac{\left\lvert\overrightarrow{M_1M_0}\times\boldsymbol s\right\rvert}{\lvert\boldsymbol s\rvert}.
$$

线面平行 $\iff\boldsymbol s\cdot\boldsymbol n=0$；线面垂直 $\iff\boldsymbol s\parallel\boldsymbol n$。

### 4. 曲面

- **旋转曲面**：$yOz$ 面上 $f(y,z)=0$ 绕 $z$ 轴，得 $f\left(\pm\sqrt{x^2+y^2},z\right)=0$。**绕谁转，谁不变。**
- **柱面**：缺哪个变量，母线就平行于哪个轴。
- **投影**：消去 $z$ 得投影柱面，再与 $z=0$ 联立。
- 单叶双曲面（一个负号），双叶双曲面（两个负号），马鞍面 $z=x^2-y^2$。

详见 [09 向量代数与空间解析几何](/posts/gaoshu-09-vector/)。

## 十、多元函数微分学

### 1. 概念关系

$$
\text{偏导数连续}\Rightarrow\text{可微}\Rightarrow\begin{cases}\text{连续}\\\text{偏导数存在}\\\text{方向导数存在}\end{cases}
$$

反之都不成立；**连续与偏导数存在互不蕴含**。

**判断可微**：$\displaystyle\lim_{\rho\to0}\frac{\Delta z-f_x\Delta x-f_y\Delta y}{\rho}=0$。

**二重极限不存在**：找两条路径（$y=kx$、$y=kx^2$）极限不同。

### 2. 求导

- **复合函数**：连线相乘，分线相加；$f_1'$、$f_2'$ 求导时**继续用链式法则**。
- **隐函数**：$F(x,y,z)=0$，$z_x=-\dfrac{F_x}{F_z}$，$z_y=-\dfrac{F_y}{F_z}$。
- **全微分形式不变性**：$\mathrm dz=f_u\,\mathrm du+f_v\,\mathrm dv$。

### 3. 方向导数与梯度 (数一)

$$
\frac{\partial f}{\partial l}=\operatorname{grad}f\cdot\boldsymbol e_l=f_x\cos\alpha+f_y\cos\beta+f_z\cos\gamma.
$$

**$\boldsymbol e_l$ 必须是单位向量**。沿梯度方向方向导数最大，最大值 $\lvert\operatorname{grad}f\rvert$。

### 4. 几何应用 (数一)

- 曲面 $F=0$ 的法向量：$(F_x,F_y,F_z)$；$z=f(x,y)$ 的法向量：$(f_x,f_y,-1)$。
- 参数曲线的切向量：$(x',y',z')$；两曲面交线的切向量：$\boldsymbol n_1\times\boldsymbol n_2$。

### 5. 极值

- **无条件**：驻点处 $A=f_{xx}$，$B=f_{xy}$，$C=f_{yy}$。$AC-B^2>0$ 时有极值（$A>0$ 极小，$A<0$ 极大）；$<0$ 无极值；$=0$ 不能判断。
- **条件极值**：$L=f+\lambda\varphi$，令各偏导数为 0。
- **闭区域最值**：内部驻点 + 边界最值 + 比较。

详见 [10 多元函数微分学](/posts/gaoshu-10-multivariable/)。

## 十一、重积分

### 1. 二重积分

- **直角坐标**：外层限是常数，内层限是外层变量的函数。
- **极坐标**：$\mathrm d\sigma=r\,\mathrm dr\,\mathrm d\theta$。$x^2+y^2=2ax$ 即 $r=2a\cos\theta$，$\theta\in\left[-\dfrac\pi2,\dfrac\pi2\right]$。
- **交换次序**：内层积分求不出（$e^{-y^2}$、$\dfrac{\sin y}{y}$、$e^{x^2}$）时，画图重新定限。

### 2. 对称性

- 区域关于 $y$ 轴对称：$f$ 关于 $x$ 奇则积分为 0，偶则 2 倍。
- 区域关于 $y=x$ 对称：$\displaystyle\iint_Df(x,y)\,\mathrm d\sigma=\iint_Df(y,x)\,\mathrm d\sigma$。

### 3. 三重积分 (数一)

| 方法 | 体积元 | 适用 |
| --- | --- | --- |
| 投影法（先一后二） | $\mathrm dx\,\mathrm dy\,\mathrm dz$ | 上下曲面明确 |
| 截面法（先二后一） | — | 被积函数只含 $z$ |
| 柱坐标 | $r\,\mathrm dr\,\mathrm d\theta\,\mathrm dz$ | 含 $x^2+y^2$ |
| 球坐标 | $\rho^2\sin\varphi\,\mathrm d\rho\,\mathrm d\varphi\,\mathrm d\theta$ | 球、锥；$\varphi\in[0,\pi]$ |

锥面 $z=\sqrt{x^2+y^2}$ 即 $\varphi=\dfrac\pi4$；球面 $x^2+y^2+z^2=2Rz$ 即 $\rho=2R\cos\varphi$。

### 4. 应用

$$
\text{曲面面积：}S=\iint_{D_{xy}}\sqrt{1+z_x^2+z_y^2}\,\mathrm d\sigma;\qquad\text{质心：}\bar x=\frac{\iiint x\mu\,\mathrm dV}{\iiint\mu\,\mathrm dV};\qquad I_z=\iiint(x^2+y^2)\mu\,\mathrm dV.
$$

详见 [11 重积分](/posts/gaoshu-11-multiple-integral/)。

## 十二、曲线积分与格林公式 (数一)

### 1. 计算

$$
\int_Lf\,\mathrm ds=\int_\alpha^\beta f\sqrt{x'^2+y'^2}\,\mathrm dt\quad(\alpha<\beta);\qquad\int_LP\,\mathrm dx+Q\,\mathrm dy=\int_\alpha^\beta(Px'+Qy')\,\mathrm dt\quad(\alpha\text{ 对应起点}).
$$

两类联系：$\mathrm dx=\cos\alpha\,\mathrm ds$，$\mathrm dy=\cos\beta\,\mathrm ds$。

### 2. 格林公式

$$
\oint_LP\,\mathrm dx+Q\,\mathrm dy=\iint_D\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\mathrm d\sigma\qquad(L\text{ 正向，}D\text{ 内无奇点}).
$$

面积：$S=\dfrac12\displaystyle\oint_Lx\,\mathrm dy-y\,\mathrm dx$。

### 3. 路径无关

单连通区域内，$\dfrac{\partial Q}{\partial x}=\dfrac{\partial P}{\partial y}\iff$ 与路径无关 $\iff$ 闭曲线积分为 0 $\iff$ 存在原函数 $u$。

### 4. 方法选择

- 闭曲线、无奇点：格林公式；
- 不闭合：**补线**；
- 有奇点：**挖洞**，小曲线形状按分母选；
- $\dfrac{x\,\mathrm dy-y\,\mathrm dx}{x^2+y^2}$ 绕原点一周：$2\pi$。

详见 [12 曲线积分与格林公式](/posts/gaoshu-12-line-integral/)。

## 十三、曲面积分与高斯、斯托克斯公式 (数一)

### 1. 计算

$$
\iint_\Sigma f\,\mathrm dS=\iint_{D_{xy}}f(x,y,z(x,y))\sqrt{1+z_x^2+z_y^2}\,\mathrm dx\,\mathrm dy.
$$

$$
\iint_\Sigma R\,\mathrm dx\,\mathrm dy=\pm\iint_{D_{xy}}R(x,y,z(x,y))\,\mathrm dx\,\mathrm dy\quad(\text{上侧正，下侧负}).
$$

**合一投影**（上侧）：

$$
\iint_\Sigma P\,\mathrm dy\,\mathrm dz+Q\,\mathrm dz\,\mathrm dx+R\,\mathrm dx\,\mathrm dy=\iint_{D_{xy}}\bigl(-Pz_x-Qz_y+R\bigr)\mathrm dx\,\mathrm dy.
$$

两类联系：$\mathrm dy\,\mathrm dz=\cos\alpha\,\mathrm dS$，$\mathrm dz\,\mathrm dx=\cos\beta\,\mathrm dS$，$\mathrm dx\,\mathrm dy=\cos\gamma\,\mathrm dS$。

### 2. 高斯公式

$$
\oiint_\Sigma P\,\mathrm dy\,\mathrm dz+Q\,\mathrm dz\,\mathrm dx+R\,\mathrm dx\,\mathrm dy=\iiint_\Omega\left(P_x+Q_y+R_z\right)\mathrm dV\qquad(\text{外侧，内部无奇点}).
$$

不封闭：**补面**；有奇点：**挖小球**。

### 3. 斯托克斯公式

$$
\oint_\Gamma P\,\mathrm dx+Q\,\mathrm dy+R\,\mathrm dz=\iint_\Sigma\begin{vmatrix}\cos\alpha&\cos\beta&\cos\gamma\\\partial_x&\partial_y&\partial_z\\P&Q&R\end{vmatrix}\mathrm dS\qquad(\text{右手法则}).
$$

$\Sigma$ 一般取 $\Gamma$ 所在的平面。

### 4. 散度与旋度

$$
\operatorname{div}\boldsymbol A=P_x+Q_y+R_z,\qquad\operatorname{rot}\boldsymbol A=\bigl(R_y-Q_z,\ P_z-R_x,\ Q_x-P_y\bigr).
$$

**对称性**：第一类曲面积分与重积分相同；第二类曲面积分**规律相反**（关于 $z$ 为奇函数时 $\displaystyle\iint R\,\mathrm dx\,\mathrm dy$ 不为 0）。

详见 [13 曲面积分与高斯、斯托克斯公式](/posts/gaoshu-13-surface-integral/)。

## 十四、常数项级数

### 1. 基本结论

- 收敛 $\Rightarrow u_n\to0$；$u_n\not\to0\Rightarrow$ 发散。
- 收敛 + 收敛 = 收敛；收敛 + 发散 = 发散；发散 + 发散 = 不一定。
- 收敛级数加括号仍收敛；加括号后收敛，原级数不一定收敛。
- 绝对收敛 $\Rightarrow$ 收敛。

### 2. 基准级数

$$
\sum aq^n\text{：}\lvert q\rvert<1\text{ 收敛};\qquad\sum\frac{1}{n^p}\text{：}p>1\text{ 收敛};\qquad\sum\frac{1}{n\ln^pn}\text{：}p>1\text{ 收敛}.
$$

### 3. 正项级数判别法

| 方法 | 适用 |
| --- | --- |
| 比较（极限形式） | 等价无穷小化成 $\dfrac{1}{n^p}$，最常用 |
| 比值 $\displaystyle\lim\frac{u_{n+1}}{u_n}$ | 含 $n!$、$a^n$ |
| 根值 $\displaystyle\lim\sqrt[n]{u_n}$ | 含 $(\cdots)^n$ |
| 积分判别法 | $u_n=f(n)$，$f$ 单调递减 |

比值、根值 $=1$ 时失效。

### 4. 交错级数

**莱布尼茨**：$u_n$ 单调递减且 $u_n\to0\Rightarrow\sum(-1)^{n-1}u_n$ 收敛，余项 $\lvert r_n\rvert\le u_{n+1}$。

$\displaystyle\sum\frac{(-1)^n}{n^p}$：$p>1$ 绝对收敛，$0<p\le1$ 条件收敛。

### 5. 反例

$\dfrac1n$（$u_n\to0$ 但发散）、$\dfrac{(-1)^n}{n}$（条件收敛）、$\dfrac{(-1)^n}{\sqrt n}$（收敛但平方发散；等价不同敛散）。

**变号级数不能用等价无穷小**，要泰勒展开、拆项。

详见 [14 常数项级数](/posts/gaoshu-14-series/)。

## 十五、幂级数与傅里叶级数

### 1. 收敛半径

$$
R=\frac1\rho,\qquad\rho=\lim\left\lvert\frac{a_{n+1}}{a_n}\right\rvert\text{ 或 }\lim\sqrt[n]{\lvert a_n\rvert}.
$$

缺项时对整个通项用比值法；**端点单独判断**；条件收敛的点一定是端点。

### 2. 基本展开式

$$
\frac{1}{1-x}=\sum_{n=0}^\infty x^n\ (-1<x<1),\qquad\frac{1}{1+x}=\sum_{n=0}^\infty(-1)^nx^n\ (-1<x<1),
$$

$$
e^x=\sum_{n=0}^\infty\frac{x^n}{n!},\qquad\sin x=\sum_{n=0}^\infty\frac{(-1)^nx^{2n+1}}{(2n+1)!},\qquad\cos x=\sum_{n=0}^\infty\frac{(-1)^nx^{2n}}{(2n)!}\quad(x\in\mathbb R),
$$

$$
\ln(1+x)=\sum_{n=1}^\infty\frac{(-1)^{n-1}x^n}{n}\ (-1<x\le1),\qquad\arctan x=\sum_{n=0}^\infty\frac{(-1)^nx^{2n+1}}{2n+1}\ (-1\le x\le1).
$$

### 3. 求和模板

$$
\sum_{n=1}^\infty nx^{n-1}=\frac{1}{(1-x)^2},\qquad\sum_{n=1}^\infty nx^n=\frac{x}{(1-x)^2},\qquad\sum_{n=1}^\infty\frac{x^n}{n}=-\ln(1-x).
$$

$n$ 在分子**先积后导**，$n$ 在分母**先导后积**，含 $n!$ 凑 $e^x$。

### 4. 常用数项级数的和

$$
\sum_{n=1}^\infty\frac{(-1)^{n-1}}{n}=\ln2,\qquad\sum_{n=0}^\infty\frac{(-1)^n}{2n+1}=\frac\pi4,\qquad\sum_{n=1}^\infty\frac1{n^2}=\frac{\pi^2}{6},\qquad\sum_{n=0}^\infty\frac{1}{n!}=e.
$$

### 5. 傅里叶级数 (数一)

$$
a_n=\frac1\pi\int_{-\pi}^\pi f(x)\cos nx\,\mathrm dx,\qquad b_n=\frac1\pi\int_{-\pi}^\pi f(x)\sin nx\,\mathrm dx.
$$

周期 $2l$：$nx$ 换成 $\dfrac{n\pi x}{l}$，$\dfrac1\pi$ 换成 $\dfrac1l$。

- 奇函数只有 $b_n$（正弦级数，奇延拓）；偶函数只有 $a_n$（余弦级数，偶延拓）。
- **狄利克雷定理**：连续点 $S(x)=f(x)$；间断点 $S(x)=\dfrac{f(x^-)+f(x^+)}{2}$；端点 $S(\pm\pi)=\dfrac{f(-\pi^+)+f(\pi^-)}{2}$。

详见 [15 幂级数与傅里叶级数](/posts/gaoshu-15-power-fourier/)。

## 十六、考前最后提醒

> [!CAUTION] 每年都有人在这些地方丢分
> 1. 等价无穷小在**加减**中替换；
> 2. 洛必达之前没检查是不是 $\dfrac00$ 或 $\dfrac\infty\infty$；
> 3. 不定积分忘记 $+C$，换元积分忘记回代；
> 4. 定积分**换元不换限**；有瑕点直接用牛顿-莱布尼茨公式；
> 5. 二阶非齐次方程特解的 $k$ 取错；
> 6. 极坐标漏 $r$，球坐标漏 $\rho^2\sin\varphi$；
> 7. 方向导数没有把方向向量单位化；
> 8. 格林、高斯公式没检查**封闭、正向（外侧）、无奇点**；
> 9. 第二类曲面积分套用第一类的对称性；
> 10. 幂级数收敛域**漏判端点**，展开式**没写收敛域**。

> [!TIP] 做题顺序
> - 选择、填空控制在 **70～80 分钟**内，难题先跳过；
> - 解答题先写**能拿分的步骤**：公式、定理条件、关键变形都有步骤分；
> - 最后留 **10 分钟**检查计算，尤其是符号和积分上下限。

整个系列到这里就全部结束了。回到 [00 导读与复习路线](/posts/gaoshu-00-guide/) 可以看到完整目录和复习计划。祝考试顺利！
