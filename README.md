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
	
	[Automated Structural Modelling of Bridges from Laser Scanning](https:///www.kdocs.cn/p/846588893527) 
	--> 建立桥梁的整体模型。先对点云进行分类，再根据桥梁不同构件的几何特点还原构件（1、提取主轴和横截面；2、对比数据库）。
  
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

* [__`无人机扫描建模`__] [Unmanned aerial vehicle inspection of the Placer river trail bridge through image-based 3D modelling.](https://www.kdocs.cn/p/846681125373)
	--> 讲了一个无人机扫描桥梁并建立三维模型实例

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
	* [__`神经网络 NET`__] [Semantic Metric 3D Reconstruction for Concrete Inspection](https://www.kdocs.cn/p/84658401319)
	[Multi-classifier for reinforced concrete bridge defects](https://www.kdocs.cn/p/84663112947)
		--> 建立数据集，对裂缝进行识别和分类。
	* [__`法向量变化以及RGB信息`__] [Laser-based structural sensing and surface damage detection](https://kdocs.cn/l/srbBv5jSkRbP)  :star::star::star:
		--> 该方法主要根据**裂缝区域处点云的法向量变化较大而且颜色[灰度]较暗**，通过这两个阈值分割裂缝，我感觉方法更依赖于颜色，但是法向量变化对于**混凝土剥落，坑洞**等有较好的区别性。
		
		[Image-Based Automated 3D Crack Detection for Post-disaster Building Assessment](https://www.kdocs.cn/p/84658394160)
		-->利用机器人来收集数据，建立模型。主要提出了一种裂缝检测方法（CDA，crack detection algorithm），该方法通过法线和轴线的差来定义裂缝，并验证了它的精度
  
	* [__`image-based`__] [Development of Image Processing for Crack Detection on Concrete Structures through Terrestrial Laser Scanning Associated with the Octree Structure](https://kdocs.cn/l/seXtLmlA5sSW)
		--> 本文的方法很基础，就是使用Oc-tree将点云体素化并转化为2D的图片，然后基于成熟的 image processing 来检测裂缝。但是该方法仅限于识别裂缝，对于裂缝长度宽的的量化文章未做.。际上，点云到图像丢失信息较大，量化极不准确。
		
		[A review on computer vision based defect detection and condition assessment of concrete and asphalt civil infrastructure.](https://www.kdocs.cn/p/84658751081)
		-->混凝土和沥青的基于计算机视觉的缺陷检测和状态评估技术的一个综述
		
		[Laser-based surface damage detection and quantification using predicted surface properties. ](https://www.kdocs.cn/p/84659523299)
		-->结合激光扫描和图像的最佳特征，介绍了一种自动有效的表面损伤检测方法
		
		[Crack detection limits in unit based masonry with terrestrial laser scanning](https://www.kdocs.cn/p/84659266691)
		-->用地面激光扫描仪检测到砌体结构的最小裂缝宽度


  
	* [__`UAV`__] []
		--> 

* deformation

        * [__`单独构件分析`__] [Damage Detection and Finite-Element Model Updating of Structural Components through Point Cloud Analysis](https://www.kdocs.cn/p/84658480774)
	        --> 对于简单构件，在构件上打不同的孔作为缺陷，检测了缺陷的大小并与实际值作了比较；Ansys里生成了fem，做了简单的应力分析比较；对点云的密度选择和fem的mesh大小做了了敏感性比较
		
		[3D FEM model development from 3D optical measurement technique applied to corroded steel bars](https://www.kdocs.cn/p/84659343276)
	        --> 对腐蚀钢筋进行扫描建模，分析其疲劳荷载下的应力。
		
	 * [__`构件挠度位移检测`__] [Deformation tracking in 3D point clouds via statistical sampling of direct cloud-to-cloud distances. ](https://www.kdocs.cn/p/84659638483)
	        --> 以一个小组件为例，利用点云进行变形检测
		
* structure

	* [__`masonry arch 结合雷达`__] [Structural assessment of masonry arch bridges by combination of non-destructive testing techniques and three-dimensional numerical modelling: Application to Vilanova bridge](https://kdocs.cn/l/spLH6WURi0kL)  :star::star:
		--> laser scan 获取表面几何信息，ground penetrating radar survey获取隐藏的几何信息，对拱桥做了很详细的检查和分析
		
		[Modelling and strength evaluation of masonry bridges using terrestrial photogrammetry and finite element.](https://www.kdocs.cn/p/84659727289)
		-->研究石拱桥的极限行为。用了地面摄影测量法和探地雷达进行整体和全面的测量
		
	* [__`masonry arch 拱脚位移`__] [Mapping deformations and inferring movements of masonry arch bridges using point cloud data](https://kdocs.cn/l/som0epENnA4d)
		--> 本文主要是根据拱脚位移等几何运动学建立拱桥变形的点云形状的数据库，然后那实际桥梁的点云与数据库做对比，探索可能的变形机制，进行确定拱脚位移量。详细==待补充==
		
	* [__`历史遗迹分析`__] [Semi-automated creation of accurate FEM meshes of heritage masonry walls from point cloud data](https://www.kdocs.cn/p/84658653060)
		--> 对遗迹的砖石结构进行建模，从点云数据中半自动提取墙的几何形状，再使用摄影测量法将裂缝信息纳入模型。对比了传统线框模型和复杂模型（本实验提出模型）的建模精确度。
		
		 [Failure analysis of a Portuguese cultural heritage masterpiece: Bonet building in Sintra](https://www.kdocs.cn/p/84659008362)
		--> 激光扫描结果-在BIM 建模-对模型进行简化，划分几何体-有限元静态、动态分析，两种方法结果对比
		
		[Cloud-to-BIM-to-FEM: Structural simulation with accurate historic BIM from laser scans.](https://www.kdocs.cn/p/84658796144)
		--> 把建筑在先转为BIM中模型，再生成FEM进行计算
		
		
* material
	* [__`材料识别`__] [Automatic classification of common building materials from 3D terrestrial laser scan data]()
		--> using one-class support vector machine (OC-SVM) method and support vector data description (SVDD) method with assistance of features such as **material reflectance**, **colour** and **surface roughness** to classify material by point clouds

* 灾后分析
	* [__`地震`__] [Applications of laser scanning to structures in laboratory tests and field surveys](https://kdocs.cn/l/saI80eKIWDtx)
		--> 这篇文章主要讲述了LS在实验变形监测以及灾后变形评估方面的应用，实验变形监测方法中规中矩，但是在**建筑物位移以及扭转**的评估方面，所用方法较好，主要通过不同水平截面的关键点计算偏移向量，值得借鉴。
		
		[Preparation of synthetic as-damaged models for post-earthquake BIM reconstruction research.](https://www.kdocs.cn/p/84659887357)
		--> 提出了一种用于编译此类数据集的计算方法，包括受损建筑物的BIM建模和合成扫描生成
		
		[Towards generation of as-damaged BIM models using laser-scanning and as-built BIM: First estimate of as-damaged locations of reinforced concrete frame members in masonry infill structures.](https://www.kdocs.cn/p/84659897506)
		--> 对于已损坏的建筑结构，生成其最初位置的最佳猜测
		
	* [__`地震`__] [A laser scanning-based method for fast estimation of seismic-induced building deformations]()
		--> ==待补充==

      

:arrow_forward: 5. BIM
* [__`digital twin`__] [Digital twinning of existing reinforced concrete bridges from labelled point clusters](https://kdocs.cn/l/srTYdTxHwknD) (*.IFC)
	--> 从 labelled point clusters 开始，重点放在 fitting step，提出 slicing-based object fitting method 来生成孪生数字几何模型，并提出 cloud-to-cloud distance-based metrics 来评估结果的准确性

* [__`信息传递相关`__] [Integrating RC Bridge Defect Information into BIM Models](https://www.kdocs.cn/p/84663675308) 
	--> 损伤结检测定义，损伤信息集成（首先，从现有的分析中提取需要进行桥梁评估的缺陷和特性的类型；第二，作者对缺陷实体，它们的特性和它们之间的关系进行了建模；第三，将它们映射到合适的IFC实体）

* gbxml

---

* In practical circumstances
* In all of the above studies

