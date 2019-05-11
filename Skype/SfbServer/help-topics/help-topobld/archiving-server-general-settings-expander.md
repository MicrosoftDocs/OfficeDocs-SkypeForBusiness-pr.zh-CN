---
title: 存档服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 在拓扑生成器中，可以通过右键单击控制台树中的“存档服务器”，再单击工具栏中的“操作”，或单击“操作”窗格中的任务，然后单击“编辑属性”并更改以下任意选项来编辑各个存档服务器的属性：
ms.openlocfilehash: 89fc3fd914f9430893a411a6b5a39cce2998a841
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915780"
---
# <a name="archiving-server-general-settings-expander"></a>存档服务器常规设置扩展器
 
在拓扑生成器中，可以通过右键单击控制台树中的“存档服务器”，再单击工具栏中的“**操作**”，或单击“操作”窗格中的任务，然后单击“**编辑属性**”并更改以下任意选项来编辑各个存档服务器的属性：
  
- **FQDN**，更改要部署为存档服务器的服务器的完全限定域名 (FQDN)。
    
- **SQL 存储**，更改要用于存档 SQL Server 数据库的 SQL Server 实例。如果更改存档服务器的 SQL Server 数据库，则必须重新启动存档服务器以确保更改生效。
    
- **文件共享**，更改要用于存档文件存储的文件夹。如果更改存档服务器的文件共享，则必须重新启动存档服务器以确保更改生效。此外，还必须将以前的会议文件移动到新的文件存储文件夹以避免丢失已存档的会议文件。
    
> [!NOTE]
> 若要更改与存档服务器关联的池，请为当前与存档服务器关联的单个前端池节点或 Survivable Branch Appliance 节点选择“**编辑属性**”选项。
  
> [!NOTE]
> 如果之前将存档服务器添加到拓扑生成器中的拓扑，则存档节点包含存档服务器。可以编辑列表中所有存档服务器的属性。但是，无法存档即时消息或 Web 会议（消息传递），除非另外为存档服务器设置了服务。 
  

