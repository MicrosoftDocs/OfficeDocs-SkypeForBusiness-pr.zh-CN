---
title: 启用和禁用媒体旁路
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中过程以启用或禁用媒体旁路使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: f595ab5380575f34c0a470cb58c82459841ee4d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222756"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>启用和禁用媒体旁路 Skype 中的业务服务器

使用本文中过程以启用或禁用媒体旁路使用 Skype 业务 Server Control Panel。

## <a name="enable-network-media-bypass"></a>启用网络媒体绕过 

媒体绕过设置跨业务服务器部署 Skype 全局适用。 媒体绕过允许绕过中介服务器的呼叫。 有关详细信息何时使用媒体绕过，请参阅[Plan for 媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。

您可以启用和配置媒体绕过从 Skype 业务 Server Control Panel。


### <a name="to-enable-and-configure-media-bypass"></a>启用和配置媒体绕过

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**全局**。

4.  在**全局**页上，单击**全局**配置。 始终没有只有一个配置，并且其始终名为 Global。

5.  在**编辑**菜单上，单击**查看详细信息**。

6.  在**编辑全局设置**页上，单击**启用媒体绕过**复选框。

7.  选择以下选项之一：
    
      - **始终绕过**   选择此选项可尝试媒体绕过所有呼叫。 如果已启用呼叫允许控制 (CAC)，则此选项将不可用。 如果未启用 CAC，请在下列情况下选择此选项：
        
          - 没有需要带宽控制。
        
          - 没有需要精确的配置以确定何时发生旁路。
        
          - 没有网关与客户端之间的完全连接。
    
      - **使用站点和区域配置**   如果 CAC 处于启用状态，默认情况下选中此选项，并不能更改。 选中此选项后，将使用网络配置站点和区域，以确定何时可能发生媒体绕过。 如果选择此选项，您可以选择启用绕过的未映射的网站。 单击**启用非映射站点的绕过**复选框，只有您已在一个或多个大站点与同一区域关联的没有带宽限制 （例如，大型中央站点），并且您还可以与关联某些分支站点具有带宽限制的相同区域。 当您启用时为非映射站点绕过，请配置简化，因为指定仅与的分支站点相关联的子网，而无需指定的所有子网与所有网站关联。 我们建议您执行选择**启用非映射站点的绕过**复选框，如果已启用 CAC。

8.  单击**提交**以保存所做的更改。


## <a name="disable-network-media-bypass"></a>禁用网络媒体绕过

媒体绕过设置跨业务服务器部署 Skype 全局适用。 媒体绕过允许绕过中介服务器的呼叫。 有关详细信息何时使用媒体绕过，请参阅[Plan for 媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。 您可以禁用从 Skype 的媒体绕过业务 Server Control Panel。 


### <a name="to-disable-media-bypass"></a>若要禁用媒体旁路

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**全局**。

4.  在**全局**页上，单击**全局**配置。 始终没有只有一个配置，并且其始终名为 Global。

5.  在**编辑**菜单上，单击**查看详细信息**。

6.  在**编辑全局设置**页上，清除**启用媒体绕过**复选框。

7.  单击**提交**以保存所做的更改。

  