---
title: 启用呼叫允许控制
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 配置呼叫允许控制 (CAC) 网络后，您必须启用 CAC 来强制实施的带宽限制。"
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897641"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 上启用呼叫允许控制

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。 配置 CAC 网络后，您必须启用 CAC 来强制实施的带宽限制。 您可以使用业务 Server Control Panel 的 Skype 执行此操作。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>启用业务 Server Control Panel 从 Skype 的 CAC

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**全局**。

4.  在**全局**页上，单击**全局**配置。
   
    > [!NOTE]  
    > 可以为任何 Skype 对于业务服务器部署，配置只有一个网络，以便不会在列表中的多个网络配置。 无法重命名全局配置。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑全局设置**页上，选择**启用呼叫允许控制**复选框，然后单击**提交**。

单击**提交**，当您将运行测试的配置。 将关闭**编辑全局设置**对话框中，返回到**全局**页。 如果您将会阻止其正常工作 （例如，如果未连接到其他每个区域间路由通过每个区域） 的网络配置中发现的任何错误或不一致情况，您将收到一条警告。

如果您对您的网络配置更改，您可以通过打开全局配置并单击**提交**运行再次验证检查。 不需要先禁用 CAC： 保留检查复选框，然后单击**提交**。 您可以这样做任何时候不进行任何配置更改。

## <a name="see-also"></a>另请参阅

[规划呼叫允许控制](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[部署呼叫允许控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[删除 CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
