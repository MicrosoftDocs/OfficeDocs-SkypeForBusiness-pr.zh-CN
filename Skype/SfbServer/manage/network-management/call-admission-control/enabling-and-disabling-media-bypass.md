---
title: 启用和禁用媒体绕过
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中的步骤, 通过使用 Skype for Business 服务器控制面板启用或禁用媒体旁路。
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279583"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在 Skype for Business Server 中启用和禁用媒体旁路

使用本文中的步骤, 通过使用 Skype for Business 服务器控制面板启用或禁用媒体旁路。

## <a name="enable-network-media-bypass"></a>启用网络媒体旁路 

媒体绕过设置跨 Skype for Business 服务器部署全局应用。 媒体绕过允许呼叫绕过中介服务器。 有关何时使用 "媒体绕过" 的详细信息, 请参阅[规划媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。

您可以从 Skype for Business 服务器控制面板启用和配置 "绕过媒体"。


### <a name="to-enable-and-configure-media-bypass"></a>启用和配置绕过媒体

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。

4.  在 "**全局**" 页面上, 单击 "**全局**配置"。 始终只有一种配置, 它始终名为 Global。

5.  在 "**编辑**" 菜单上, 单击 "**查看详细信息**"。

6.  在 "**编辑全局设置**" 页面上, 单击 "**启用绕过媒体**" 复选框。

7.  选择下列选项之一:
    
      - **"始终绕过**   " 选择此选项可在所有呼叫中尝试媒体绕过。 如果启用了 "呼叫许可控制 (CAC)", 此选项将不可用。 如果未启用 CAC, 请在以下情况下选择此选项:
        
          - 无需带宽控制。
        
          - 不需要精确的配置来确定何时应发生绕过。
        
          - 网关和客户端之间存在完全连接。
    
      - **使用网站和区域配置**   如果启用了 CAC, 则默认情况下此选项处于选中状态, 并且不能更改。 选中此选项时, 将使用网络配置网站和区域确定何时可能使用媒体绕过。 如果选择此选项, 则可以选择对未映射的网站启用 "绕过"。 仅当您有一个或多个大型网站与不具有带宽约束的同一区域 (例如, 大型中央网站) 相关联, 并且您还具有与之关联的一些分支网站时, 单击 "**为非映射网站启用旁路**" 复选框。具有带宽限制的同一区域。 为非映射网站启用 "绕过" 时, 将简化配置, 因为你只需指定与分支网站相关联的子网, 而无需指定与所有网站相关联的所有子网。 如果启用了 CAC, 我们建议您不要选中 "为**未映射的网站启用旁路**" 复选框。

8.  单击 "**提交**" 保存所做的更改。


## <a name="disable-network-media-bypass"></a>禁用网络媒体旁路

媒体绕过设置跨 Skype for Business 服务器部署全局应用。 媒体绕过允许呼叫绕过中介服务器。 有关何时使用 "媒体绕过" 的详细信息, 请参阅[规划媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。 您可以从 Skype for Business 服务器控制面板禁用 "媒体绕过"。 


### <a name="to-disable-media-bypass"></a>禁用媒体绕过

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。

4.  在 "**全局**" 页面上, 单击 "**全局**配置"。 始终只有一种配置, 它始终名为 Global。

5.  在 "**编辑**" 菜单上, 单击 "**查看详细信息**"。

6.  在 "**编辑全局设置**" 页面上, 清除 "**启用绕过媒体**" 复选框。

7.  单击 "**提交**" 保存所做的更改。

  
