---
title: 删除业务服务器中 Skype 的 PIN 策略
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要： 业务服务器 Skype 删除用户的电话拨入式会议 PIN。
ms.openlocfilehash: d8b8a901e15e0b301dcce149b3f55a27f8298af6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893263"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>删除业务服务器中 Skype 的 PIN 策略
 
**摘要：** 删除业务服务器 Skype 用户的电话拨入式会议 PIN。
  
按照以下步骤删除个人标识号 (PIN) 策略。
  
> [!NOTE]
> 无法删除全局 PIN 策略。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>删除业务 Server Control Panel 中 Skype 的 PIN 策略

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”**** 页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“**确定**”。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

您可以使用 Windows PowerShell 和 Remove-cspinpolicy cmdlet 删除 PIN 策略。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-remove-a-specific-pin-policy"></a>删除特定 PIN 策略

- 以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>删除适用于站点范围的所有 PIN 策略

- 以下命令删除在站点作用域配置的所有 PIN 策略：
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>删除允许使用通用模式的所有 PIN 策略

- 以下命令删除允许使用通用模式的所有 PIN 策略：G
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

有关详细信息，请参阅[Remove-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  

