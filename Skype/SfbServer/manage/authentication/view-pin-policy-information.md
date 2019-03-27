---
title: 业务服务器 Skype 中查看 PIN 策略信息
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要： 查看用户 PIN 策略信息的 Skype 业务服务器。
ms.openlocfilehash: 5fdd042f01c325bfffedbfa32fa14d9e667ef7be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888921"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>业务服务器 Skype 中查看 PIN 策略信息
 
**摘要：** 查看用户 PIN 策略信息的 Skype 业务服务器。
  
您可以使用视图个人识别号 (PIN) 身份验证的用户连接到业务与 IP 电话的 Skype **PIN 策略**选项卡。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>以查看 PIN 策略的信息中 Skype 业务 Server Control Panel

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”**** 页上，单击某个策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 PIN 策略

您还可以使用 Windows PowerShell 和 Get-cspinpolicy cmdlet 查看 PIN 策略。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-view-pin-policies"></a>查看 PIN 策略

若要查看有关所有 PIN 策略的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:
    
  ```
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

有关详细信息，请参阅[Get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[为 Business Server Skype 创建新的 PIN 策略](create-a-new-pin-policy.md)
