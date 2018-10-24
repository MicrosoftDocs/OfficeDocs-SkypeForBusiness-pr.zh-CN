---
title: 还原文件存储
TOCTitle: 还原文件存储
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202180(v=OCS.15)
ms:contentKeyID: 52061068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原文件存储

 

_**上一次修改主题：** 2013-02-18_

Standard Edition 的文件存储通常位于 Standard Edition Server 上。Enterprise Edition 的文件存储通常位于文件服务器或群集上。以下过程介绍如何还原文件存储。

## 还原文件存储

1.  如果文件存储发生故障，请将相应的文件存储从 $Backup\\ 复制到文件服务器或 Standard Edition Server 上的文件存储位置，然后共享该文件夹。
    
    > [!IMPORTANT]
    > 还原的文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。


2.  如果需要，为文件存储设置访问控制列表 (ACL)。在命令行中键入：
    
        Enable-CsTopology
    
    > [!NOTE]  
	> 仅当您在还原过程中没有运行拓扑生成器时，才需要执行此步骤。
    

