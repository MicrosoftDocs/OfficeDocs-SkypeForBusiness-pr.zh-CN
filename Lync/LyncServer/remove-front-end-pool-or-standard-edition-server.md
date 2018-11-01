---
title: 删除前端池或 Standard Edition 服务器
TOCTitle: 删除前端池或 Standard Edition 服务器
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49888490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除前端池或 Standard Edition 服务器

 

_**上一次修改主题：** 2012-10-04_

本主题指导您完成删除 前端池或 Standard Edition 前端服务器的过程。在删除 前端池时，作为池删除过程的一部分，将会删除属于该池的每个 前端服务器。在删除 Standard Edition 前端服务器时，必须从 拓扑生成器中删除 SQL 存储定义。

## 删除前端服务器池

1.  打开 拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  展开“Enterprise Edition 前端池”，展开“前端池”，右键单击要删除的 前端池，然后单击“删除”。

4.  发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

## 删除 Standard Edition 前端服务器

1.  打开 拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  展开“Standard Edition 前端服务器”，右键单击要删除的 前端服务器，然后单击“删除”。

4.  展开“SQL 存储”，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击“删除”。
    
    > [!IMPORTANT]
    > 必须从 Standard Edition 前端服务器中删除并置的 SQL Server 数据库的定义。


5.  发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

