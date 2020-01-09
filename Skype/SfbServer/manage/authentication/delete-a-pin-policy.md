---
title: 在 Skype for Business 服务器中删除 PIN 策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要：删除用户的 Skype for business 服务器的电话拨入式会议 PIN。
ms.openlocfilehash: cfdb14ad8107c8d3450e6d50245831f723ca1153
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992319"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>在 Skype for Business 服务器中删除 PIN 策略
 
**摘要：** 删除用户的 Skype for business 服务器的电话拨入式会议 PIN。
  
按照以下步骤删除个人标识号 (PIN) 策略。
  
> [!NOTE]
> 无法删除全局 PIN 策略。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器控制面板" 中删除 PIN 策略

1.  从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”**** 页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“**确定**”。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

你可以使用 Windows PowerShell 和 CsPinPolicy cmdlet 删除 PIN 策略。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
### <a name="to-remove-a-specific-pin-policy"></a>删除特定 PIN 策略

- 以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>删除适用于站点范围的所有 PIN 策略

- 以下命令删除在站点作用域配置的所有 PIN 策略：
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>删除允许使用通用模式的所有 PIN 策略

- 以下命令删除允许使用通用模式的所有 PIN 策略：G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

有关详细信息，请参阅[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
  

