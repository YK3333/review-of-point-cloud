# review-of-point-cloud
### [Toc]
* **1. Introduction**
  Instrument
  
  Laser scanning, photography

* **2. Data processing**

  * Registration

  * Segmentation and clustering
  * Fitting method
  * Object detection and classification
  
* **3. Dimension quality assessment**

  Dimension and position of prefabricated elements

* **4. Structural damage assessment**

  * global and local deformation
    
  * crack

    directly on points cloud

    combined with image

  * spalling

    such surface quality
  
* **5. Structural performance assessment**
  * FE model generation
  * Model updating (parameters such as modulus and passion ratio) and validation
  * Structural nonlinear analysis
  
* **6. Combination with BIM**
  * life-circle documentation
  * visualization
  
* **7. Conclusions**
  In this work
  
* **Acknowledgments**

* **References**

---
### [papers]
:arrow_forward: 1. segmentation (base processing)

* [__`beam bridge`__] [Detection of Structural Components in Point Clouds of Existing RC Bridges](https://kdocs.cn/l/si4nXfaLdY47) :star:
	--> 主要是根据梁桥的结合特点，分割主梁，桥墩，墩帽等桥梁部件点云  {slicing method}
  
* [__`arch bridge`__] [Automated processing of large point clouds for structural health monitoring of masonry arch bridges](https://kdocs.cn/l/sdMQMWY2tSdw)
	--> 分割混凝土拱桥的点云

:arrow_forward:  2. dimensional quality assessment (DQA)

* [__`rebar|concrete cover`__] [Automated dimensional quality assessment for formwork and rebar of reinforced concrete components using 3D point cloud data](https://kdocs.cn/l/sfr2Gi37urGF)
	--> 在浇筑混凝土前，评估钢筋位置 {a noise removal algorithm|PCA|RANSAC}

* [__`dimensional and surface quality`__] [A framework for dimensional and surface quality assessment of precast concrete elements using BIM and 3D laser scanning](https://kdocs.cn/l/strjem8y7vN3)
	--> 提到激光扫描的参数优化
  
* [__`dimension of panels`__] [Automated dimensional quality assessment of precast concrete panels using terrestrial laser scanning](https://kdocs.cn/l/ssGVs4Sw0Xns)
	--> 这篇文章是比较正常的流程：_Data pre-processing_ --> _Edge and corner extraction_ -->  _Compensation for edge dimension loss_ --> _Dimension estimation and quality assessment_

	文章还提出一个边缘点提取的算法，即 **Vector-Sum Algorithm**
	讨论激光扫描的三个参数问题：<span style="color:green;">Scan distance  Angular resolution Incident angle</span>

* [__`组合结构装配关系`__]
  
* [__`脚手架安全性`__]

:arrow_forward:  3. finite element model (FEM) 

* [__`voxel-based`__] [From Laser Scanning to Finite Element Analysis of Complex Buildings by Using a Semi-Automatic Procedure](https://kdocs.cn/l/samrAcuI4TZk)
	--> 该方法主要是一个**切片(Slice Generation)以及对每一个切片体素化(FEM Generation)**的过程。可直接生成有限元模型，本文还对FEM进行了**模态分析**，验证模型的有效性。
* [__`two/three dimensional voxel-based mesh`__] [Automated Structural Modelling of Bridges from Laser Scanning](https://kdocs.cn/l/stwxqkotQchm)
	--> [2D 截面网格拉伸] [3D 区分 boundary/interal/exteral voxels]

:arrow_forward:  4. inspection
* crack
	* [__`图像在点云中显示`__] [Concrete crack assessment using digital image processing and 3D scene reconstruction](https://kdocs.cn/l/sm1RhNMyNpso)
		--> 基于多视角的三维重建，2D到3D的投影过程，有利于在BIM中形象展示，更主要的是投影与重建是的较大区域的裂缝可连接起来，同时克服传统 2D image 对拍摄角度的垂直要求，该方法有很好的的应用前景。
	* [__`神经网络 NET`__]
	* [__`法向量变化以及RGB信息`__] [Laser-based structural sensing and surface damage detection](https://kdocs.cn/l/srbBv5jSkRbP)  :star::star::star:
		--> 该方法主要根据**裂缝区域处点云的法向量变化较大而且颜色[灰度]较暗**，通过这两个阈值分割裂缝，我感觉方法更依赖于颜色，但是法向量变化对于**混凝土剥落，坑洞**等有较好的区别性。
  
	* [__`image-based`__] [Development of Image Processing for Crack Detection on Concrete Structures through Terrestrial Laser Scanning Associated with the Octree Structure](https://kdocs.cn/l/seXtLmlA5sSW)
		--> 本文的方法很基础，就是使用Oc-tree将点云体素化并转化为2D的图片，然后基于成熟的 image processing 来检测裂缝。但是该方法仅限于识别裂缝，对于裂缝长度宽的的量化文章未做.。际上，点云到图像丢失信息较大，量化极不准确。
  
	* [__`UAV`__] []
		--> 

* deformation

* structure

	* [__`masonry arch 结合雷达`__] [Structural assessment of masonry arch bridges by combination of non-destructive testing techniques and three-dimensional numerical modelling: Application to Vilanova bridge](https://kdocs.cn/l/spLH6WURi0kL)  :star::star:
		--> laser scan 获取表面几何信息，ground penetrating radar survey获取隐藏的几何信息，对拱桥做了很详细的检查和分析
	* [__`masonry arch 拱脚位移`__] [Mapping deformations and inferring movements of masonry arch bridges using point cloud data](https://kdocs.cn/l/som0epENnA4d)
		--> 本文主要是根据拱脚位移等几何运动学建立拱桥变形的点云形状的数据库，然后那实际桥梁的点云与数据库做对比，探索可能的变形机制，进行确定拱脚位移量。详细==待补充==

* material
	* [__`材料识别`__] [Automatic classification of common building materials from 3D terrestrial laser scan data]()
		--> using one-class support vector machine (OC-SVM) method and support vector data description (SVDD) method with assistance of features such as **material reflectance**, **colour** and **surface roughness** to classify material by point clouds

* 灾后分析
	* [__`地震`__] [Applications of laser scanning to structures in laboratory tests and field surveys](https://kdocs.cn/l/saI80eKIWDtx)
		--> 这篇文章主要讲述了LS在实验变形监测以及灾后变形评估方面的应用，实验变形监测方法中规中矩，但是在**建筑物位移以及扭转**的评估方面，所用方法较好，主要通过不同水平截面的关键点计算偏移向量，值得借鉴。
	* [__`地震`__] [A laser scanning-based method for fast estimation of seismic-induced building deformations]()
		--> ==待补充==

      

:arrow_forward: 5. BIM
* [__`digital twin`__] [Digital twinning of existing reinforced concrete bridges from labelled point clusters](https://kdocs.cn/l/srTYdTxHwknD) (*.IFC)
	--> 从 labelled point clusters 开始，重点放在 fitting step，提出 slicing-based object fitting method 来生成孪生数字几何模型，并提出 cloud-to-cloud distance-based metrics 来评估结果的准确性

* gbxml

---

* In practical circumstances
* In all of the above studies

