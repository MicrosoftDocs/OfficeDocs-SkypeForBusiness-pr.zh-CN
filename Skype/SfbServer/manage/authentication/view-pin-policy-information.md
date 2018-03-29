---
title: 在 Skype for Business Server 2015 中查看 PIN 策略信息
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要： 查看用户的 PIN 策略信息的 Skype 业务服务器 2015年。
ms.openlocfilehash: 3b62dae5cbd29c4622e30c6369a498eb48e126c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看 PIN 策略信息
 
**摘要：**查看用户的 PIN 策略信息的 Skype 业务服务器 2015年。
  
您可以使用视图个人标识号码 (PIN) 身份验证的用户连接到与 IP 电话业务的 Skype **PIN 策略**选项卡。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>在 Skype 业务服务器控件面板查看 PIN 策略信息

1.  从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”****页上，单击某个策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>查看通过使用 Windows PowerShell Cmdlet 的 PIN 策略

您还可以查看通过使用 Windows PowerShell 和 Get CsPinPolicy cmdlet 的 PIN 策略。 从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-view-pin-policies"></a>查看 PIN 策略

要查看所有 PIN 策略有关的信息，请键入下面的命令在 Skype 的业务服务器管理外壳程序，然后按 enter 键：
    
  ```
  Get-CsPinPolicy
  ```

这将返回与以下类似的信息：

  ```
  Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
  ```

有关详细信息，请参阅有关[获取 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 为业务服务器 2015年中创建的新 PIN 策略](create-a-new-pin-policy.md)

