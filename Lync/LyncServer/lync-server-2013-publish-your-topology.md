---
title: Lync Server 2013：发布拓扑
TOCTitle: 发布拓扑
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412935(v=OCS.15)
ms:contentKeyID: 49314117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中发布拓扑

 

_**上一次修改主题：** 2012-09-08_

每次使用 拓扑生成器生成拓扑时，必须将拓扑发布到 中央管理存储中的数据库，以便该数据可用于部署 Lync Server 2013。请使用以下过程发布拓扑。

## 发布拓扑

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在 拓扑生成器的控制台树中，右键单击“Lync 2013”，然后单击“发布拓扑”。

3.  在向导的“欢迎”页上，单击“下一步”。

4.  在“拓扑生成器找到 CMS 存储”页上，单击“下一步”。

5.  在“创建其他数据库”页上，单击“下一步”。

6.  当状态指示成功创建数据库时，执行以下操作：
    
      - 要查看日志，请单击“查看日志”。
    
      - 要关闭向导，请单击“完成”。
        
    > [!IMPORTANT]  
    > 如果这是 边缘服务器或 边缘池的新安装，则必须从现有 前端服务器、 前端池或 Standard Edition Server 导出 边缘服务器配置。若要导出该配置，请参阅 <a href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装</a>。在通过 Lync Server 部署向导安装和部署 边缘服务器的过程中，您将从外部媒体或网络共享中导入配置文件。
    > 在 边缘服务器可运行且已通过内部部署复制本地配置管理存储数据库后，将发布针对 Lync Server 2013 配置的后续更新，并会将这些更新复制到 边缘服务器。

