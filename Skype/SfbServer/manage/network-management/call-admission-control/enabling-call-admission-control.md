---
title: 启用呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 配置呼叫许可控制 (CAC) 网络后, 必须启用 CAC 才能强制实施带宽限制。"
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279548"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 上启用呼叫允许控制

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。 配置 CAC 网络后, 必须启用 CAC 才能强制实施带宽限制。 您可以使用 Skype for Business 服务器控制面板执行此操作。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>从 "Skype for Business 服务器" 控制面板启用 CAC

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。

4.  在 "**全局**" 页面上, 单击 "**全局**配置"。
   
    > [!NOTE]  
    > 仅可为任何 Skype for Business Server 部署配置一个网络, 因此列表中永远不会有多个网络配置。 不能重命名全局配置。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑全局设置**" 页面上, 选中 "**启用呼叫许可控制**" 复选框, 然后单击 "**提交**"。

单击 "**提交**" 时, 将运行配置测试。 "**编辑全局设置**" 对话框将关闭, 返回到**全局**页。 如果你的网络配置中发现了任何错误或不一致 (例如, 如果每个区域未通过 interregion 路由连接到其他每个区域), 你将收到警告。

如果你对网络配置进行了更改, 则可以通过打开全局配置并单击 "**提交**" 来再次运行验证检查。 无需首先禁用 CAC: 选中复选框, 然后单击 "**提交**"。 您可以随时执行此操作, 而无需进行任何配置更改。

## <a name="see-also"></a>另请参阅

[规划呼叫允许控制](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[部署呼叫允许控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
