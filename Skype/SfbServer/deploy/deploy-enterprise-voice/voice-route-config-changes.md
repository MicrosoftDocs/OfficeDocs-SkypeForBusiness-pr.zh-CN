---
title: 发布挂起的 Skype for Business 中的语音路由配置更改
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要： 了解如何查看、 发布或取消语音路由配置更改中 Skype 业务服务器使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: fa31026627aa70d3c33412a0b6454e3a87cefd8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886586"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>发布挂起的 Skype for Business 中的语音路由配置更改
 
**摘要：** 了解如何查看、 发布或取消语音路由配置更改中 Skype 业务服务器使用 Skype 业务 Server Control Panel。
  
在“语音路由”**** 组的页面中对任何配置设置做出更改后，执行此过程以查看、发布或取消待处理的更改。
  
> [!IMPORTANT]
> 确保每次只有一个用户修改语音路由配置设置。 
  
> [!NOTE]
> 必须通过运行“全部提交”**** 命令，同时发布所有待处理的更改。不能选择性地发布待处理的更改。发布待处理的更改前，运行“查看未提交的更改”**** 命令并取消任何不希望发布的配置更改。
  
> [!NOTE]
> 如果在提交待处理更改前离开“语音路由”**** 组中的页面，所有待处理更改都将丢失。 但是，可以将当前配置（包括所有待处理的更改）导出至语音配置文件，然后导入并发布已更新的配置。 有关详细信息，请参阅[导出或导入语音路由配置文件中的业务的 Skype](voice-route-configuration-import-export.md)。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>查看、发布或取消语音路由配置更改

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 在“语音路由”**** 组的每个页面中，对设置做出所需的配置更改。
    
5. 要在不发布更改的情况下查看待处理的更改，请从“提交”**** 菜单中选择“查看未提交的更改”****。
    
6. 如果要取消任何待处理的更改，请执行下列操作之一：
    
   - 从“提交”**** 菜单中选择“取消所有未提交的更改”****。
    
   - 导航到包含要取消的待处理更改的“语音路由”**** 页的选项卡，选择包含待处理更改的项目，单击“提交”****，然后单击“取消选择的更改”****。
    
7. 查看所有待处理的更改并取消其中不希望发布的更改后，单击“提交”****，然后单击“全部提交”****。
    
8. 在“未提交的语音配置设置”**** 对话框（其中显示所有待处理更改的列表）中，单击“确定”****。 
    
    Skype 的业务 Server Control Panel 提交更改，出现**成功发布语音路由配置**邮件。
    

