---
title: 导出或导入语音路由配置中的文件 Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要： 了解如何导出或为业务服务器导入语音路由配置文件中 Skype，使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: 5cf9021a1cc18daf90fc719723962959142ad92e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886787"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>导出或导入语音路由配置中的文件 Skype for Business
 
**摘要：** 了解如何导出或为业务服务器导入语音路由配置文件中 Skype，使用 Skype 业务 Server Control Panel。
  
如果要在未发布语音路由配置的情况下保存该配置，请按照以下步骤保存和检索语音路由配置的快照。 
  
当您导入语音路由配置文件 (.vcfg)，但语音路由配置的服务器上同时发生更改时，**语音路由**组中的业务 Server Control Panel Skype 中的页面将指示那里未提交的更改到语音路由。 这些未提交的更改是两种需要调节的配置之间的差异。
  
如果对组中的任何页面上的设置进行任何未提交的更改，更改将保存导出的语音配置文件 (.vcfg) 中。 这使您能够语音路由配置更改期间之前发布更改的多个会话。 
  
### <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”**** 菜单上，单击“导出配置”****。
    
5. 指定位置和文件名，然后单击“保存”****。
    
### <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”**** 菜单上，单击“导入配置”****。
    
5. 找到要导入的配置文件，然后单击“打开”****。
    
6. 单击“提交”****，然后单击“全部提交”****。
    
    > [!NOTE]
    > 任何时候导入语音配置文件，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。
  

