---
title: Lync Server 2013：工作流创建方案概述
TOCTitle: 工作流创建方案概述
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204646(v=OCS.15)
ms:contentKeyID: 49311873
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的工作流创建方案概述

 

_**上一次修改主题：** 2012-10-17_

创建工作流时，可以采用两种方案：

  - **管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。

  - **管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。
    
    > [!NOTE]  
	> 如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。
    

