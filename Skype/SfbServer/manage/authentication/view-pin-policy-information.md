---
title: 在管理中查看 PIN 策略Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要：查看用户的 PIN 策略信息，了解Skype for Business Server。
ms.openlocfilehash: 385602c4395ec0a189bc25d8a1ab052a8bf1475b440fc34795d54110b4bcffc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286831"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>在管理中查看 PIN 策略Skype for Business Server
 
**摘要：** 查看用户的 PIN 策略信息，了解Skype for Business Server。
  
可以使用 **"PIN 策略**"选项卡查看个人标识号 (PIN) IP 电话Skype for Business IP 电话进行身份验证。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>在控制面板中查看有关 PIN Skype for Business Server的信息

1.  从 RTCUniversalServerAdmins 组 (或具有等效用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在 **"PIN 策略"** 页上，单击某个策略，单击 **"编辑"，** 然后单击"显示 **详细信息"。**
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 cmdlet Windows PowerShell PIN 策略

您还可以使用 cmdlet 和 Windows PowerShell cmdlet Get-CsPinPolicy PIN 策略。 此 cmdlet 可以从命令行管理程序Skype for Business Server远程会话运行Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程[PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在Skype for Business Server。
  
### <a name="to-view-pin-policies"></a>查看 PIN 策略

若要查看有关所有 PIN 策略的信息，请在命令行管理程序中Skype for Business Server以下命令，然后按 Enter：
    
  ```PowerShell
  Get-CsPinPolicy
  ```

这将返回与以下类似的信息：

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

有关详细信息，请参阅 [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[在"密码"中创建新的 PIN Skype for Business Server](create-a-new-pin-policy.md)