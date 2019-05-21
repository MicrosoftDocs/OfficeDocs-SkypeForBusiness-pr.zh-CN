---
title: 在 Skype for Business 中导出或导入语音路线配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '摘要: 了解如何使用 Skype for business Server 控制面板导出或导入 Skype for Business 服务器中的语音路由配置文件。'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300878"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>在 Skype for Business 中导出或导入语音路线配置文件
 
**摘要:** 了解如何使用 Skype for business Server 控制面板导出或导入 Skype for Business 服务器中的 "语音路由配置" 文件。
  
如果要在未发布语音路由配置的情况下保存该配置，请按照以下步骤保存和检索语音路由配置的快照。 
  
当您导入一个语音路由配置文件 (vcfg), 但同时在服务器上对语音路由配置进行了更改时, Skype for Business Server 控制面板中的 "**语音路由**" 组中的页面将显示有未提交的语音路由更改。 这些未提交的更改是两种需要调节的配置之间的差异。
  
如果你对组内任何页面上的设置进行了任何未提交的更改, 则所做的更改将保存在导出的语音配置文件 (vcfg) 中。 这使你可以在发布更改之前在多个会话期间进行语音路由配置更改。 
  
### <a name="to-export-a-voice-routing-configuration"></a>导出语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”**** 菜单上，单击“导出配置”****。
    
5. 指定位置和文件名，然后单击“保存”****。
    
### <a name="to-import-a-voice-routing-configuration"></a>导入语音路由配置

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“操作”**** 菜单上，单击“导入配置”****。
    
5. 找到要导入的配置文件，然后单击“打开”****。
    
6. 单击“提交”****，然后单击“全部提交”****。
    
    > [!NOTE]
    > 任何时候导入语音配置文件，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。
  

