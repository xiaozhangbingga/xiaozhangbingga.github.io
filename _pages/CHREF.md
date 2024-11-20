---
layout: single
permalink: /CHREF/
# title: "Wide Single Layout Page"
classes: wide
# excerpt: "A page with `classes: wide` set to expand the main content's width."
# tags: 
#  - sample post
#  - readability
#  - test
---

# **An Automatic Framework Recognizing the Relationships of Cultural Heritage**
[https://doi.org/10.1109/ACCESS.2024.3500584](https://doi.org/10.1109/ACCESS.2024.3500584)

[Zizhan Zhang](/), Zijun Zhou, Yingchun Cao

### **ABSTRACT**: 
The field of cultural heritage has developed over a long period, accumulating a wealth of research findings. Researchers are now focusing on systematic relationships and taxonomic studies of heritage, exploring the underlying cultural information embedded within.Inspired by the fields of machine learning and biology, we propose a research approach that combines data processing with unsupervised algorithms ("Feature Sparsity Module + N"), which can be utilized to unveil the systematic relationships of cultural heritage study subjects.We construct the **C**ultural **H**eritage **R**elationship **E**valuation **F**ramework (**CHREF**), framework using the structure of "FSM + PCA + HCA", which offers a workflow characterized by interpretability, visualization capabilities, and automation. The framework utilizes the FSM module to transform the research subjects into matrices, employing PCA and HCA to obtain intuitive charts and reliable data results with minimal manual intervention. Additionally, we provide experiments and a user study on traditional Chinese brick kilns to validate the effectiveness and universality of the proposed framework.The "FSM + N" methodology and CHREF can provide tools for various stages of work in cultural heritage, making significant contributions to the digital development and database construction in the field of cultural heritage.
### **KEYWORDS**:
Cultural heritage, Machine learning, Interdisciplinary Research, Embedding, One-hot encoding, Principal component analysis, Hierarchical clustering analysis, Traditional Chinese Kilns

![Graphical Abstract](/assets/images/CHREF/Graphical Abstract.jpg)
*Graphical Abstract*

# **自动识别文化遗产系统关系的框架**
[张子湛](/), 周梓骏, 曹迎春

### **摘要**:
文化遗产领域经过漫长的发展, 积累了丰富的研究成果. 当前, 研究者开始聚焦于遗产的系统性关系与分类研究, 探索其中蕴含的深层文化信息. 受机器学习和生物学领域的启发, 我们提出了一种结合数据处理与无监督算法的研究方法 (“FSM + N”) , 旨在揭示文化遗产研究对象的系统性关系. 我们构建了一个文化遗产关系评估框架 (Cultural Heritage Relationship Evaluation Framework, 简称 CHREF) , 其结构基于“FSM + PCA + HCA”, 并提供了具有可解释性,可视化能力和自动化特点的工作流程. 该框架通过 FSM 模块将研究对象转化为矩阵, 并利用 PCA 和 HCA 获取直观图表和可靠的数据结果, 同时将人工干预降至最低. 此外, 我们以中国传统砖窑为例, 进行实验和用户研究, 以验证所提框架的有效性与普适性. “FSM + N”方法论与 CHREF 框架可为文化遗产研究中的各个阶段提供工具, 对文化遗产的数字化发展及数据库建设具有重要贡献.
### **关键词**:
文化遗产, 机器学习, 交叉学科, 嵌入, 独热编码, 主成分分析, 层次聚类分析, 中国传统砖瓦窑



论文受到了机器学习和生物学领域研究方法的启发, 提出一个研究思路 (简称“FSM + N”). 这个研究思路就是使用独热编码来记录文化遗产中的无序的离散的类型数据, 我们编写了一个 FSM 模块来完成这个功能, 经过模块处理后的数据可以有意义的记录研究对象形态特征的差异, 模块可以和不同的算法组合实现不同的研究目标. 本篇论文提供了一个 CHREF 框架实现聚类分析, 选择 PCA 和 HCA 两种解释度很高的算法与 FSM 搭建框架. 

![Type2Vec](/assets/images/CHREF/type2vec.jpg)
*离散的信息都被投影到高维空间, 不同类型之间的距离值是相同的. 针对某些样本缺失的特征, 也做了处理(其实就是检测到 0 值就给类型值都加一哈哈哈), 保证有无特征的距离值与不同形态类型的距离值一致.*

解决了数据处理的问题就可以开始构建框架了, 我们选择了 PCA 做降维和可视化 HCA 做聚类分析. 我们还测试了 t-SNE, UMAP, DBSCAN, AP 这些算法, 性能相比 PCA 和 HCA 有少量的提升, 但超参数多了许多, 操作难度提升了许多, 这不利与框架的自动化. 

![MainFramework](/assets/images/CHREF/main_framework.jpg)
*框架的思路就是使用 FSM 处理数据, 使用 PCA 的 SVD 方法做降维和可视化, 最后使用 HCA 对降维后的数据做聚类分析, 整个框架的输出结果是一些图表, 可视化效果好.*

本论文提供了一个关于中国砖瓦窑的实验, 用来验证我们提出的框架. 我们从考古报告中收集了 55 座信息较为完备的砖窑作为样本, 选取了砖窑的 28 个特征点作为样本信息. 砖窑的年代从先商到明代, 根据考古学的观点有许多的分类方法, 我们更多的关注形态对砖窑系统关系的影响与基于形态的砖窑系统关系.

![PCAImportance](/assets/images/CHREF/pca_importance.jpg)
*使用右奇异向量矩阵与奇异值矩阵计算每个特征点在每个主成分上的荷载值, 高荷载值代表该特征在该主成分上的影响较大(方差大). 根据图表可以看到比较重要的特征点是 19(排烟系统类型), 1(砖窑的构筑方式), 6(火塘的竖直位置), 7(火塘的水平位置), 8(火塘大小).*

![PCAPeriod](/assets/images/CHREF/pca_period.jpg)
*这张图是第一主成分和第二主成分的散点图, 按照朝代标注了散点的颜色. 我们使用高斯分布拟合了每个朝代的密度极值点, 按照朝代发展相连. 可以看出砖窑发展中每次大变化发生在哪一个主成分的维度, 结合特征荷载可以看到变化是基于何种特征点的发展.*

![HCADendrogram](/assets/images/CHREF/hca_dendrogram.jpg)
*PCA 降维后我的取用前 20 个主成分维度的数据, 解释度 90.625%, 凝聚后获得了树状图. 设置阈值为 6, 获得了 8 个支系, 结果与年代散点图和特征荷载图表现的砖窑发展特征高度相符.*

---
到这论文的主要内容就讲完了, 我们的技术能力有限, 只是想分享一个生产数据的方式和分析的基本思路. 论文还有详细的内容, 可以点击[这里](https://doi.org/10.1109/ACCESS.2024.3500584)查看. 最后, 希望文化遗产领域的开源数据可以越来越多, 哈哈哈.
