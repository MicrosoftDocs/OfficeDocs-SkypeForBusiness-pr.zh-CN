---
title: 在 Skype for Business Server 中删除 PIN 策略
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
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要：删除用户的 Skype for Business Server 电话拨入式会议 PIN。
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096788"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>在 Skype for Business Server 中删除 PIN 策略
 
**摘要：** 删除用户的 Skype for Business Server 电话拨入式会议 PIN。
  
按照以下步骤删除个人标识号 (PIN) 策略。
  
> [!NOTE]
> 无法删除全局 PIN 策略。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>在 Skype for Business Server 控制面板中删除 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”，然后单击“删除”。
    
6. 单击“确定”。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 删除WINDOWS POWERSHELL PIN 策略

可以使用 cmdlet 和 Windows PowerShell 删除Remove-CsPinPolicy策略。 可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中是相同的。
  
### <a name="to-remove-a-specific-pin-policy"></a>删除特定 PIN 策略

- 以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>删除应用于站点范围的所有 PIN 策略

- 以下命令删除在站点作用域配置的所有 PIN 策略：
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>删除允许使用通用模式的所有 PIN 策略

- 以下命令删除允许使用通用模式的所有 PIN 策略：G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

有关详细信息，请参阅 [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。
