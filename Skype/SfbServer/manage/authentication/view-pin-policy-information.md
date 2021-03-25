---
title: 在 Skype for Business Server 中查看 PIN 策略信息
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
description: 摘要：查看 Skype for Business Server 的用户 PIN 策略信息。
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119531"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>在 Skype for Business Server 中查看 PIN 策略信息
 
**摘要：** 查看 Skype for Business Server 的用户 PIN 策略信息。
  
可以使用 **"PIN** 策略"选项卡查看个人标识号 (PIN) IP 电话连接到 Skype for Business 的用户进行身份验证。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>在 Skype for Business Server 控制面板中查看有关 PIN 策略的信息

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在 **"PIN 策略"** 页上，单击某个策略，单击 **"编辑"，** 然后单击"显示 **详细信息"。**
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 cmdlet Windows PowerShell PIN 策略

您还可以使用 cmdlet 和 Windows PowerShell 查看 PIN Get-CsPinPolicy策略。 可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中是相同的。
  
### <a name="to-view-pin-policies"></a>查看 PIN 策略

若要查看有关所有 PIN 策略的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：
    
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

[在 Skype for Business Server 中创建新的 PIN 策略](create-a-new-pin-policy.md)