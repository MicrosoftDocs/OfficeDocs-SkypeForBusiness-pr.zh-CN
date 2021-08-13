---
title: 在语音路由配置中发布待处理Skype for Business
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要：了解如何使用"Skype for Business Server控制面板"查看、发布或取消Skype for Business Server路由配置更改。
ms.openlocfilehash: 9c9cfd1cfdf1cf58f58cfcbf77abb54f9068609414a3b141b4fb643abcf4ac83
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338690"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>在语音路由配置中发布待处理Skype for Business
 
**摘要：** 了解如何使用控制面板查看、发布或取消 Skype for Business Server 中的语音Skype for Business Server配置更改。
  
在“语音路由”组的页面中对任何配置设置做出更改后，执行此过程以查看、发布或取消待处理的更改。
  
> [!IMPORTANT]
> 确保每次只有一个用户修改语音路由配置设置。 
  
> [!NOTE]
> 必须通过运行“全部提交”命令，同时发布所有待处理的更改。不能选择性地发布待处理的更改。发布待处理的更改前，运行“查看未提交的更改”命令并取消任何不希望发布的配置更改。
  
> [!NOTE]
> 如果在提交待处理更改前离开“语音路由”组中的页面，所有待处理更改都将丢失。 但是，可以将当前配置（包括所有待处理的更改）导出至语音配置文件，然后导入并发布已更新的配置。 有关详细信息，请参阅导出[或导入语音路由配置文件Skype for Business。](voice-route-configuration-import-export.md) 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>查看、发布或取消语音路由配置更改

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击“语音路由”。
    
4. 在“语音路由”组的每个页面中，对设置做出所需的配置更改。
    
5. 要在不发布更改的情况下查看待处理的更改，请从“提交”菜单中选择“查看未提交的更改”。
    
6. 如果要取消任何待处理的更改，请执行下列操作之一：
    
   - 从“提交”菜单中选择“取消所有未提交的更改”。
    
   - 导航到包含要取消的待处理更改的“语音路由”页的选项卡，选择包含待处理更改的项目，单击“提交”，然后单击“取消选择的更改”。
    
7. 查看所有待处理的更改并取消其中不希望发布的更改后，单击“提交”，然后单击“全部提交”。
    
8. 在“未提交的语音配置设置”对话框（其中显示所有待处理更改的列表）中，单击“确定”。 
    
    当Skype for Business Server提交更改后，将显示"**已成功发布的语音路由配置"** 消息。
    

