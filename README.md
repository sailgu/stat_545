# 抗体芯片阳性点探索

标签（空格分隔）： 抗体芯片 阳性点

## 瑞博奥抗体芯片
### 归一化方法
从瑞博奥公司官网的技术资料页面下载的文献都使用了采用内参点的方法进行归一化的，可能和他们的抗体芯片的点比较少有关,两篇文献如下
> #### [*Ionizing Radiation and Glioblastoma Exosomes*](http://www.sciencedirect.com/science/article/pii/S1936523313800034)
> ##### Human Chemokine and Cytokines Antibody Arrays
> Human chemokine or human cytokine V arrays (Ray Biotech, Inc) were used following the manufacturer's instructions. After developing, films were scanned and the images processed and quantified using ImageJ software (National Institutes of Health). **Intensity was normalized to internal positive controls for comparison**.
> #### [*Chemokine Signaling via the CXCR2 Receptor Reinforces Senescence*](http://www.sciencedirect.com/science/article/pii/S0092867408006193)
> ##### Antibody Array Analysis
> Pelleted exosomes were lysed as above. Glass protein arrays (human angiogenesis antibody array AAH-ANG-G1 and cytokine antibody array G series AAH-CYT-G6/7/8; RayBiotech, Norcross, GA) were used to detect protein levels in exosome samples. Assays were carried out according to the manufacturer’s recommendations (15 μg of exosome lysate per subarray). **Array values were standardized against the positive control within each subarray**. Samples were run as biologic replicates, and a 1.33-fold change or greater was used as a cutoff to explore significant targets (increased or decreased abundance), comparing radiation-derived exosomes to those derived from nonirradiated cells.

### 瑞博奥芯片特点
从瑞博奥芯片[**官方手册**](https://www.raybiotech.com/files/manual/Antibody-Array/QAH-CAA-X00.pdf)可知，他们的芯片有如下特点
1. 归一化，采用 两个`internal positive controls`点，及标准曲线(`standard curve`)可以获得样品的实际浓度。
2. 所有抗体点都是4个重复
3. 抗体芯片的点少，最多就1000个抗体。
4. 抗体都是结合蛋白都是已知的。
总结：瑞博奥没有阳性点，阴性点一说，数据方法不是很适合我们参考，但是他那里面实验部分很值得我们参考。例如里面讲了鬼影的产生原因，是由于芯片没干燥好。

## 常见芯片去噪点方法
### F-B>2B<sub>sd</sub>
公式含义，**F**为前景值，**B**为背景值， **B<sub>sd</sub>**这个一不小心容易理解为整张芯片背景值的标准差，实际上是个体点背景值的标准差，对应gpr文件的`B532 sd`一列。

### F-B>3×B×<em>CV<sub>b</sub></em>
找到一篇[文献](http://www.mcponline.org/content/4/6/773.short)专门讲抗体芯片归一化的，其中在**Data Analysis**部分讲了去除低于一定值的标准：
> An intensity threshold for each antibody spot was calculated by the formula 3×B×<em>CV<sub>b</sub></em> , where B is the median local background of each spot, and <em>CV<sub>b</sub></em> is the average coefficient of variation (S.D. divided by the average) of all the local backgrounds on the array. 




