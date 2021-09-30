---
title: 在邮件中删除 PIN Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要：删除用户的电话拨入式会议 PIN Skype for Business Server。
ms.openlocfilehash: 7f2616c847787001f9b661704ef77f7c8dc08cec
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014356"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>在邮件中删除 PIN Skype for Business Server
 
**摘要：** 删除用户的电话拨入式会议 PIN Skype for Business Server。
  
按照以下步骤删除个人标识号 (PIN) 策略。
  
> [!NOTE]
> 无法删除全局 PIN 策略。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>在控制面板中删除 PIN Skype for Business Server

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”，然后单击“删除”。
    
6. 单击“确定”。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 删除WINDOWS POWERSHELL PIN 策略

可以使用 cmdlet 和 Windows PowerShell cmdlet Remove-CsPinPolicy PIN 策略。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在Skype for Business Server。
  
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
