# 矩阵及其运算

## 矩阵简介

### 矩阵定义

`DEF`
m行n列的数表 $$
A=\begin{bmatrix}
a^{}_{11} &\dots &a^{}_{1n} \\
\vdots &^{}_{} &\vdots \\
a^{}_{m1} & \dots &a^{}_{mn} \\
\end{bmatrix}
$$
- 可以选用圆括号或者方括号来表示
- 可以选择在矩阵的右下角标注 $ m\times n $ 来表示矩阵的大小  
- $ a^{}_{ij}  $ 被称为元素或者(i,j)元
- 该矩阵可以简记为 $ A =(a^{}_{ij})_{m\times n} $

### 常见矩阵 

1. $ 1\times1 $矩阵： A=(a)
2. $ n\times n $矩阵: 可以记为 $ A_n $ ,被称为n阶方阵,其从左上角到右下角的对角线被称为(主)对角线,从左下角到右上角的对角线被称为副对角线.  **值得注意的是,对角线的说法只限于方阵中**
   1. 对角矩阵:除了位于主对角线的元素都为0的方阵被称为对角矩阵,可以记为 $ \Lambda_n $ 或者 $ diag(d_1, \dots,d_n) $
   2. 单位矩阵:对角线上的元素均为1的对角矩阵被称为单位矩阵,记为 $ E_n $ 
3. 三角矩阵:对角线一侧所有元素(不包括对角线)均为0的方阵被称为三角矩阵,如果左下角侧的元素均为0那么称为上三角矩阵,如果是右上角的元素均为0,那么就是下三角矩阵
4. 0矩阵:所有元素均为0的m行n列的矩阵可以记为 $ 0_{m\times n} $ 
5. 行(列)矩阵:只有1行的矩阵被称为行矩阵,只有1列的矩阵被称为列矩阵
6. 负矩阵:矩阵$ A =(a^{}_{ij})_{m\times n} $对应的负矩阵$ B =(-a^{}_{ij})_{m\times n} $,记为B=-a
7. 相等矩阵:若$ A =(a^{}_{ij})_{m\times n} $,$ B =(b^{}_{ij})_{m\times n} $,且 $  a^{}_{ij} =b^{}_{ij}  $ 那么称AB相等,记为A=b

### 运算

1. 加法:已知$ A =(a^{}_{ij})_{m\times n} $,$ B =(b^{}_{ij})_{m\times n} $,则 $ A+B=C=(c^{}_{ij} )^{}_{m\times n}=(a^{}_{ij} +b^{}_{ij} )^{}_{m\times n}  $ `RK`只有两个大小相等的矩阵才能进行加法运算
   1. 交换律:A+B=B+A
   2. 零元:A+0=A
   3. 负元:A+(-A)=0
   4. 减法:A-B=A+(-B)
   5. 移项:A+B=C+D $ \Rightarrow $ A+B-C=D 
2. 数乘: 已知$ A =(a^{}_{ij})_{m\times n} $,$ B =(b^{}_{ij})_{m\times n} ,k,l\in\R$则
   1. $ k\times A=(k\times a^{}_{ij} )_{m\times n} $ 
   2. 二次数乘:$ k\times(lA)=(k\times l)A $
   3.  $ (k+l)\times A=k\times A +l\times A $ 
   4. 特别地,$ 1\times A=A;0\times A=0;(-1)\times A=-A $ 
3. 乘法:已知$ A =(a^{}_{ij})_{m\times s} $,$ B =(b^{}_{ij})_{s\times n} $,则
$$
C=A\times B=(c^{}_{ij})^{}_{m\times n} 
$$
其中 $$
c^{}_{ij} =\displaystyle \sum^{s}_{k=1}a^{}_{ik}b^{}_{kj}
$$
`RK`注意乘法中各矩阵的大小 $ (m\times s) \times (s\times n)\Rightarrow m\times n$,这就意味着对于矩阵乘法来说,交换律不成立
`RK`$ A^2 $ 有意义 $ \Leftrightarrow $A为方阵  




