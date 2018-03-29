---
title: 在 Skype for Business 2015 中导出或导入语音路由配置文件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要： 了解如何导出或导业务服务器 2015年通过 Skype 业务服务器控件面板中 Skype 语音路由选择的配置文件。
ms.openlocfilehash: 8b676ac6417c172402c231401ea9284fccbb8d97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a>在 Skype for Business 2015 中导出或导入语音路由配置文件
 
**摘要：**了解如何导出或导业务服务器 2015年通过 Skype 业务服务器控件面板中 Skype 语音路由选择的配置文件。
  
如果要在未发布语音路由配置的情况下保存该配置，请按照以下步骤保存和检索语音路由配置的快照。 
  
当您导入语音路由配置文件 (.vcfg)，但语音路由配置的服务器上同时发生更改时，Skype 业务服务器控制面板中的**语音路由**组中的页将指示存在未提交的更改，以语音路由。 这些未提交的更改是两种需要调节的配置之间的差异。
  
如果对组内的任何页面上的设置进行任何未提交的更改，所做的更改保存在导出的语音配置文件 (.vcfg)。 这使您能够在多个会话，才能发布更改路由配置更改的声音。 
  
### <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”****菜单上，单击“导出配置”****。
    
5. 指定位置和文件名，然后单击“保存”****。
    
### <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”****菜单上，单击“导入配置”****。
    
5. 找到要导入的配置文件，然后单击“打开”****。
    
6. 单击“提交”****，然后单击“全部提交”****。
    
    > [!NOTE]
    > 任何时候导入语音配置文件，都必须运行“全部提交”****命令以发布配置更改。 有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。
  

