---
title: 启用呼叫允许控制
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
description: " 在将呼叫允许控制 (CAC) 网络后，必须启用 CAC 才能强制实施带宽限制。"
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816502"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 上启用呼叫允许控制

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。 配置 CAC 网络后，必须启用 CAC 以强制实施带宽限制。 可以使用 Skype for Business Server 控制面板来这样做。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>从 Skype for Business Server 控制面板启用 CAC

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**

4.  在“全局”页上，单击“全局”配置。
   
    > [!NOTE]  
    > 只能为任何 Skype for Business Server 部署配置一个网络，因此列表中绝不会存在多个网络配置。 无法重命名“全局”配置。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑全局设置”页上，选中“启用呼叫允许控制”复选框，然后单击“提交”。

单击“提交”时，运行配置测试。此时将关闭“编辑全局设置”对话框，并返回到“全局”页。如果在网络配置中发现任何阻止其正常工作的错误或不一致问题（例如，如果每个区域未通过区域间路由连接到其他每个区域），则会收到警告。

如果更改网络配置，则可通过打开“全局”配置并单击“提交”再次运行验证检查。无需先禁用 CAC：保留此复选框的选中状态，并单击“提交”。在未对配置进行任何更改的情况下可随时执行此操作。

## <a name="see-also"></a>另请参阅

[规划呼叫允许控制](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[部署呼叫允许控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
