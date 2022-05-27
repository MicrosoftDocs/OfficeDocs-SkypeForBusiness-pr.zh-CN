---
title: 启用和禁用媒体旁路
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用本文中的过程通过使用Skype for Business Server 控制面板启用或禁用媒体旁路。
ms.openlocfilehash: 38ec29c6e4b51a4c6898b13c4de0172f55947907
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675334"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在 Skype for Business Server 中启用和禁用媒体旁路

使用本文中的过程通过使用Skype for Business Server 控制面板启用或禁用媒体旁路。

## <a name="enable-network-media-bypass"></a>启用网络媒体旁路 

媒体旁路设置在Skype for Business Server部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅 [“媒体旁路计划](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)”。

可以从Skype for Business Server 控制面板启用和配置媒体旁路。


### <a name="to-enable-and-configure-media-bypass"></a>启用和配置媒体旁路

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **“网络配置**”，然后单击 **“全局**”。

4.  在“全局”页上，单击“全局”配置。 始终只有一个配置，并且始终命名为全局。

5.  在 **“编辑”** 菜单上，单击 **“查看详细信息**”。

6.  在 **“编辑全局设置”** 页上，单击 **“启用媒体旁路** ”复选框。

7.  选择下列选项之一：
    
      - **始终绕过**   选择此选项可尝试在所有调用上绕过媒体。 如果启用了调用允许控制 (CAC) ，则此选项将不可用。 如果未启用 CAC，请在以下情况下选择此选项：
        
          - 无需带宽控制。
        
          - 无需使用细粒度配置来确定何时应发生旁路。
        
          - 网关和客户端之间有完全连接。
    
      - **使用站点和区域配置**   如果启用 CAC，则默认情况下会选择此选项，并且无法更改。 选择此选项后，将使用网络配置站点和区域来确定何时可以绕过媒体。 如果选择此选项，可以选择为未映射的站点启用旁路。 仅当有一个或多个大型站点与没有带宽约束的同一区域相关联时，才单击“ **启用非映射站点的旁路** ”复选框 (，例如，大型中心站点) ，并且你还有一些分支站点与具有带宽约束的同一区域相关联。 为非映射站点启用旁路时，配置会简化，因为只指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。 如果启用了 CAC，建议不要选中 **非映射站点的“启用旁路** ”复选框。

8.  单击 **“提交** ”以保存所做的更改。


## <a name="disable-network-media-bypass"></a>禁用网络媒体旁路

媒体旁路设置在Skype for Business Server部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅 [“媒体旁路计划](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)”。 可以从Skype for Business Server 控制面板禁用媒体旁路。 


### <a name="to-disable-media-bypass"></a>禁用媒体旁路

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **“网络配置**”，然后单击 **“全局**”。

4.  在“全局”页上，单击“全局”配置。 始终只有一个配置，并且始终命名为全局。

5.  在 **“编辑”** 菜单上，单击 **“查看详细信息**”。

6.  在 **“编辑全局设置”** 页上，清除 **“启用媒体旁路** ”复选框。

7.  单击 **“提交** ”以保存所做的更改。

  
