# postgraduate

## 介绍
2023硕士毕业论文

## 编译方式
xelatex
bibtex
xelatex
xelatex

## 模板说明

- 参考文献使用gbt7714-2015。gbt7714参考文档在终端输入`texdoc gbt7714`或者使用everything搜索gbt7714.pdf。如果需要修改参考文献格式，主要修改gbt7714-numerical.bst中的`load.config`函数。
- 所有代标号的章节标题今年都不再居中加粗，如果修改成其他格式，在format.tex文件修改`\ctexset`部分。
- 目录属于chapter级别的标题，如果需要单独修改目录标题格式，需要设置ctexset的局部样式。本模版使用方式为：
    ```tex
    \begingroup
    \ctexset{chapter={format=\xiaosanhao\bfseries\centering\songti\linespread{1.5}}}
    \tableofcontents%%%%目录
    \listoffigures%%%%插图目录
    % \listoftables%%%%表格目录
    \endgroup
    ```
    更多内容请查看ctex官方文档:`texdoc ctex`

- 针对个别段落之间段间距过大，在format.tex中加入`\raggedbottom`即可，但不清楚会不会出现其他问题，如果出现，使用默认的`\flushbottom`
- 带章节编号的图片标题格式为`图几-几`，若想在`\ref`图片时格式统一，需要把label标签放在figure标签里面，且在caption标签后面(这样一定是对的)
- 针对参考文献及其之后的标题在目录中无法正确跳转，需要在c.tex中加入
    ```tex
    \clearpage
    \phantomsection
    ```
    且加在`\addcontentsline`之前
