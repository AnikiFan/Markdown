# <center>作业 HW* 试验报告</center>
<!--
自动标题配置文件目录:"C:\Users\15800\.crossnote\style.less"(以我的电脑为例)
将文件内容改为
/* Please visit the URL below for more information: */
/*   https://shd101wyy.github.io/markdown-preview-enhanced/#/customize-css */
body{
    counter-reset: hbody;
}
h1{
    counter-reset: h1;
}
h2{
    counter-reset: h2;
}
h3{
    counter-reset: h3;
}
h4{
    counter-reset: h4;
}
h5{
    counter-reset: h5;
}
// h1::before{
    // counter-increment: hbody;
    // content: counter(hbody)". ";
// }
h2::before{
    counter-increment: h1;
    content: counter(h1)". ";
}
h3::before{
    counter-increment: h2;
    content: counter(h1)"."counter(h2)". ";
}
h4::before{
    counter-increment: h3;
    content: counter(h1)"."counter(h2)"."counter(h3)". ";
}
h5::before{
    counter-increment: h4;
    content: counter(h1)"."counter(h2)"."counter(h3)"."counter(h4)". ";
}
h6::before{
    counter-increment: h5;
    content: counter(h1)"."counter(h2)"."counter(h3)"."counter(h4)"."counter(h5)". ";
}
.markdown-preview.markdown-preview {
  // modify your style here
  // eg: background-color: blue;
}
-->
<!--
实验报告格式要求按照模板（使用Markdown等也请保证报告内包含模板中的要素）
对字体大小、缩进、颜色等不做强制要求（但尽量代码部分和文字内容有一定区分，可参考vscode配色）
实验报告要求在文字简洁的同时将内容表示清楚
报告内不要大段贴代码，尽量控制在20页以内
-->
<center>姓名:范潇</center>  
<center>学号:2254298 </center>
<center>日期:202*年*月*日</center>

<!--
&emsp;&emsp;缩进这样写`&emsp;`可以缩进一个汉字
啊啊啊啊啊啊啊啊啊
代码这样写

```c
int main()
{
    cout<<"啊啊啊啊啊"<<endl;
}
```
-->

## 涉及数据结构和相关背景
<!--报告内不要大段贴代码，尽量控制在20页以内-->
## 试验内容

### ***
<!--题目名字-->

#### 问题描述
<!--简短地描述题目(可复制题目要求)-->
#### 基本要求
<!--简短地描述题目要求-->
#### 数据结构设计
<!--
图、描述均可
贴出数据结构定义代码（变量、结构体或类）并使用注释辅助说明
例:
// Definition for a binary tree node.
struct TreeNode {
    int data;           // 节点元素
    TreeNode *lchild;   // 左孩子节点指针
    TreeNode *rchild;   // 有孩子指针
    TreeNode(int x = 0, TreeNode *left = nullptr, TreeNode *right = nullptr);
    ~TreeNode();
};
-->
#### 功能说明
<!-- 
函数,类 

推荐使用代码+注释的形式，清晰描述函数功能、输入内容和输出/返回内容
不要直接贴函数实现代码，请选择关键代码/伪代码展示并用注释辅助说明
/**
 * @brief           二叉树指令构造
 * @param   order   构造指令列表
 * @param   index   当前节点序号
 * @return          子树根节点指针
 */
TreeNode *buildTreeDFS(const std::vector<int> &order, int &index) {
    if (子树为空) {
        返回空指针 // 返回空指针给父节点
}
// 构造以当前节点为根节点的子树并返回
    return new TreeNode(order[index ++], buildTreeDFS(order, index), buildTreeDFS(order, index));
}
-->

#### 调试分析
<!-- 
遇到的问题和解决方法

简要描述调试过程
可以使用图片辅助说明
 -->

#### 总结和体会
<!--可以说说做此题的收获、分析这道题目的难点和易错点（数据边界、对算法效率的要求等）-->

<!-- 题目二 -->

## 试验总结
