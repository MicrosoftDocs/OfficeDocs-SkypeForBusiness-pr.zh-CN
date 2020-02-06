---
title: 查看 Skype for Business 服务器中的 PIN 策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要：查看 Skype for business 服务器的用户 PIN 策略信息。
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818694"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>查看 Skype for Business 服务器中的 PIN 策略信息
 
**摘要：** 查看 Skype for business 服务器的用户的 PIN 策略信息。
  
你可以使用 "**固定策略**" 选项卡查看使用 IP 电话连接到 Skype for business 的用户的个人识别码（PIN）身份验证。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中查看有关 PIN 策略的信息

1.  从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”**** 页上，单击某个策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 PIN 策略

你还可以使用 Windows PowerShell 和 CsPinPolicy cmdlet 查看 PIN 策略。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
### <a name="to-view-pin-policies"></a>查看 PIN 策略

若要查看有关所有 PIN 策略的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：
    
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

有关详细信息，请参阅[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中创建新的 PIN 策略](create-a-new-pin-policy.md)
