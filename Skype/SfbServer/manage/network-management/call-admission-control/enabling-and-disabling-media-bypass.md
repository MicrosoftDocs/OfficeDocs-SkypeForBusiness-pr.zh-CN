---
title: 启用和禁用媒体旁路
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用本文中的过程通过 Skype for Business Server 控制面板启用或禁用媒体旁路。
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816492"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在 Skype for Business Server 中启用和禁用媒体旁路

使用本文中的过程通过 Skype for Business Server 控制面板启用或禁用媒体旁路。

## <a name="enable-network-media-bypass"></a>启用网络媒体旁路 

媒体旁路设置在 Skype for Business Server 部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅["规划媒体旁路"。](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

你可以从 Skype for Business Server 控制面板启用和配置媒体旁路。


### <a name="to-enable-and-configure-media-bypass"></a>启用和配置媒体旁路

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**

4.  在“全局”页上，单击“全局”配置。 始终只有一个配置，并且始终命名为 Global。

5.  在"**编辑"** 菜单上，单击 **"查看详细信息"。**

6.  在 **"编辑全局设置** "页上，单击 **"启用媒体旁路"** 复选框。

7.  选择下列选项之一：
    
      - **始终绕过**   选择此选项可尝试在所有呼叫上绕过媒体。 如果启用了呼叫允许控制或 CAC (，此选项) 不可用。 如果未启用 CAC，请在以下情况下选择此选项：
        
          - 不需要带宽控制。
        
          - 无需进行精细配置来确定何时应发生旁路。
        
          - 网关和客户端之间具有完全连接。
    
      - **使用站点和地区配置**   如果启用 CAC，则此选项默认为选中状态，且无法更改。 选择此选项后，网络配置站点和地区将用于确定何时可以绕过媒体。 如果选择此选项，可以选择为未映射的网站启用旁路。 只有当有一个或多个大型站点与没有带宽限制的同一区域（例如，大型中央站点 () ）关联，并且某些分支站点与具有带宽限制的同一区域关联时，才单击"为非映射站点启用绕过"复选框。 为非映射站点启用绕过时，配置会简化，因为您仅指定与分支站点关联的子网，无需指定所有与所有站点关联的子网。 如果启用了 CAC，则建议您不要选中"启用非映射站点绕过"复选框。

8.  单击 **"** 提交"保存更改。


## <a name="disable-network-media-bypass"></a>禁用网络媒体旁路

媒体旁路设置在 Skype for Business Server 部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅["规划媒体旁路"。](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) 可以从 Skype for Business Server 控制面板禁用媒体旁路。 


### <a name="to-disable-media-bypass"></a>禁用媒体旁路

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**

4.  在“全局”页上，单击“全局”配置。 始终只有一个配置，并且始终命名为 Global。

5.  在"**编辑"** 菜单上，单击 **"查看详细信息"。**

6.  在" **编辑全局设置** "页上，清除 **"启用媒体旁路"** 复选框。

7.  单击 **"** 提交"保存更改。

  
