---
title: 在 Skype for Business 中导出或导入语音路由配置文件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要：了解如何使用 Skype for Business Server 控制面板在 Skype for Business Server 中导出或导入语音路由配置文件。
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830352"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>在 Skype for Business 中导出或导入语音路由配置文件
 
**摘要：** 了解如何使用 Skype for Business Server 控制面板在 Skype for Business Server 中导出或导入语音路由配置文件。
  
如果要保存语音路由配置而不发布它，请按照以下步骤保存和检索语音路由配置的快照。 
  
导入语音路由配置文件 (.vcfg) ，但同时在服务器上对语音路由配置进行了更改时，Skype for Business Server 控制面板中语音路由组的页面将指示存在未提交的语音路由更改。 这些未提交的更改是两种需要调节的配置之间的差异。
  
如果对组内任何页面上的设置进行了任何未提交的更改，这些更改将保存在导出的语音配置文件 (.vcfg) 。 这样，您可以在发布更改之前，在多个会话期间进行语音路由配置更改。 
  
### <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“语音路由”。
    
4. 在“操作”菜单上，单击“导出配置”。
    
5. 指定位置和文件名，然后单击“保存”。
    
### <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“语音路由”。
    
4. 在“操作”菜单上，单击“导入配置”。
    
5. 找到要导入的配置文件，然后单击“打开”。
    
6. 单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]
    > 任何时候导入语音配置文件，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作文档中的"在 [Skype for Business 中](voice-route-config-changes.md) 发布对语音路由配置的挂起更改"。
  

