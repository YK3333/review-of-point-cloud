# review-of-point-cloud
---
1. segmentation
    * [beam bridge](https://kdocs.cn/l/si4nXfaLdY47) :star:
    
      --> 主要是根据梁桥的结合特点，分割主梁，桥墩，墩帽等桥梁部件点云  {slicing}
    
    * [arch bridge](https://kdocs.cn/l/sdMQMWY2tSdw)
      
      --> 分割混凝土拱桥的点云
    
2. dimensional quality assessment (DQA)
    * [rebar space and concrete cover](https://kdocs.cn/l/sfr2Gi37urGF)
    
      --> 在浇筑混凝土前，评估钢筋位置 {a noise removal algorithm|PCA|RANSAC}
    
    * [dimensional and surface quality](https://kdocs.cn/l/strjem8y7vN3)
    
      --> 提到激光扫描的参数优化
    
3. finite element model (FEA)

4. inspection

    * crack

      * [图像在点云中显示](https://kdocs.cn/l/sm1RhNMyNpso)

        --> 基于多视角的三维重建，2D到3D的投影过程

      * [NET]

      * [法向量变化以及RGB信息](https://kdocs.cn/l/srbBv5jSkRbP)

    * structure

      * [masonry arch bridge 结合雷达](https://kdocs.cn/l/spLH6WURi0kL)

        --> laser scan 获取表面几何信息，ground penetrating radar survey获取隐藏的几何信息，对拱桥做了很详细的检查和分析

    * 灾后分析

      

5. BIM

    * [digital twin](https://kdocs.cn/l/srTYdTxHwknD) (*.IFC)
    
      --> 从 labelled point clusters 开始，重点放在 fitting step，提出 slicing-based object fitting method 来生成孪生数字几何模型，并提出 cloud-to-cloud distance-based metrics 来评估结果的准确性
    
    * gbxml
