$$
\frac{1}{4\pi\varepsilon_0 R}(\frac{q_1+q_3}{\sqrt{2}}+\frac{q_2}{2})
$$
$$
\frac{qQ}{4\pi\varepsilon_0}(\frac{1}{R}-\frac{1}{r_2})
$$
以点o为坐标原点,竖直向上方向为x轴正向建立空间直角坐标系
把侧面参数化可得
$$
\vec{r}=(l\sin \frac{\theta}{2}\cos\alpha,l\sin\frac{\theta}{2}\sin\alpha,-l\cos\frac{\theta}{2}),0\le \alpha\lt2\pi,\frac{R_1}{\sin\frac{\theta}{2}}\le l\lt\frac{R_2}{\sin\frac{\theta}{2}}
$$
则点o处电势为
$$
\int_{\frac{R_1}{\sin\frac{\theta}{2}}}^{\frac{R_2}{\sin\frac{\theta}{2}}}\int_0^{2\pi} \frac{\sigma\cos\frac{\theta}{2}}{4\pi\varepsilon_0l}\lvert \vec{r}_{\alpha}\times \vec{r}_{l}\rvert \mathrm{d}\alpha\mathrm{d}l
$$

化简后可得o点处电势为
$$
\int_{\frac{R_1}{\sin\frac{\theta}{2}}}^{\frac{R_2}{\sin\frac{\theta}{2}}}\int_0^{2\pi} \frac{\sigma\sin\frac{\theta}{2}\cos\frac{\theta}{2}}{4\pi\varepsilon_0} \mathrm{d}\alpha\mathrm{d}l=\frac{\cos\frac{\theta}{2}(R_2-R_1)}{2\varepsilon_0}
$$

在带点球体内距圆心a处电场强度为
$$
\frac{aQ}{ 4\pi\varepsilon_0R^3}
$$
沿径向
$$
E_{kmin}=-qU_{ro}=q(U_o-U_r)=q\int_0^R\frac{aQ}{ 4\pi\varepsilon_0R^3}\mathrm{d}a=\frac{qQ}{8\pi\varepsilon_0R}
$$

原电容器储能为 $$
\frac{1}{2}CU^2=\frac{Q^2}{2C}
$$
其中Q为极板所带电量,因为电源充电后断开,所以极板所带电量不变
极板间距离增大至n倍后电容器电容值变为原先的1/n倍,储能变为原先的n倍,因此外力所做功为原电容器储能的n-1倍,即 $$
\frac{n-1}{2}CU^2
$$

设单位长度的内柱表面带的电荷为$\lambda$,则内外柱之间距轴线r处的电场强度为
$$
\frac{\lambda}{2\pi\varepsilon r}
$$
因此当达到所能承受的最大电压时内柱处的电场强度为$E_0$
两极板间电压为 $$
\int^{r_外}_{r_内}\frac{\lambda}{2\pi\varepsilon r}dr=\frac{\lambda}{2\pi\varepsilon}\ln\frac{r_外}{r_内}=r_内E_0\ln\frac{r_外}{r_内}
$$
$$
(r_内E_0\ln\frac{r_外}{r_内})'=0时
$$
$$r_内=\frac{r_外}{e}$$
所以最高电压为 $$
\frac{200\times2kV}{e}
\approx147kV$$