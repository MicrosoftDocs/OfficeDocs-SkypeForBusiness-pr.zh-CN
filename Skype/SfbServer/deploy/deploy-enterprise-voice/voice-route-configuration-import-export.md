---
title: 导出或导入语音路由配置文件Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要：了解如何使用"Skype for Business Server控制面板在 Skype for Business Server中导出或导入语音路由配置文件。
ms.openlocfilehash: da58e9c57ff0c71704d81eb7e79c8a53f62624e0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418185"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>导出或导入语音路由配置文件Skype for Business
 
**摘要：** 了解如何使用"控制面板"在 Skype for Business Server 中导出或导入Skype for Business Server配置文件。
  
如果要保存语音路由配置而不发布它，请按照以下步骤保存和检索语音路由配置的快照。 
  
导入语音路由配置文件 (.vcfg) ，但同时在服务器上对语音路由配置进行了更改时，Skype for Business Server 控制面板中的"语音路由"组的页面将指示语音路由有未提交的更改。 这些未提交的更改是两种需要调节的配置之间的差异。
  
如果对组内任何页面上的设置进行了任何未提交的更改，更改将保存在导出的语音配置文件 (.vcfg) 。 这样，您可以在发布更改之前，在多个会话期间进行语音路由配置更改。 
  
### <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击“语音路由”。
    
4. 在“操作”菜单上，单击“导出配置”。
    
5. 指定位置和文件名，然后单击“保存”。
    
### <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击“语音路由”。
    
4. 在“操作”菜单上，单击“导入配置”。
    
5. 找到要导入的配置文件，然后单击“打开”。
    
6. 单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]
    > 任何时候导入语音配置文件，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation。
  

