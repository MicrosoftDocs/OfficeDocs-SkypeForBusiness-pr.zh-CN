---
title: "Lync Server 2013: 将 Lync Server 2013 Standard Edition 部署到现有 2013 Enterprise 中"
TOCTitle: 将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398112(v=OCS.15)
ms:contentKeyID: 49311878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中

 

_**上一次修改主题：** 2012-10-01_

在现有 Enterprise Edition 部署中部署 Standard Edition Server 与部署其他服务器角色类似。可以将 Standard Edition Server 部署至其他站点，允许该站点中的用户驻留在 Standard Edition Server 中，而不是跨广域网 (WAN) 驻留在 前端池中。 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 文档中的其他章节定义了在该站点上安装新站点和服务器的过程。

**定义新站点**

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在控制台树中，右键单击“Lync Server 2013”，然后单击“新建中央站点”。

3.  在“标识站点”页上，命名站点并选填说明。

4.  按照相应的过程定义站点拓扑的其余部分。有关详细信息，请参阅 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

5.  发布更新的拓扑。有关详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

6.  设置和安装 Standard Edition Server。
    
    > [!CAUTION]
    > 如果部署了仅具有一台 Standard Edition Server 的环境，则您应该已通过使用“准备第一个 Standard Edition Server”链接在 Lync Server 部署向导中开始安装流程，以在新的 Standard Edition Server 中安装初始数据库文件。在现有 Lync Server 2013 部署中安装 Standard Edition Server 时，<strong>请勿</strong>采用此过程。

