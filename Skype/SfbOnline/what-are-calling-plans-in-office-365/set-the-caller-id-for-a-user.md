---
title: 为用户设置来电显示
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Office 365 中的电话系统提供一个默认的来电显示，这是用户的已分配电话号码。 你可以为用户更改或阻止来电显示（也称为主叫号码）。 您可以了解有关如何使用您的组织中的呼叫者 ID，转如何可以呼叫者 ID 是您组织中使用的详细信息。
ms.openlocfilehash: 6b224addfcbc18ec3faad27e8369996647b51b03
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958188"
---
# <a name="set-the-caller-id-for-a-user"></a>为用户设置来电显示
Office 365 中的电话系统提供一个默认的来电显示，这是用户的已分配电话号码。 你可以为用户更改或阻止来电显示（也称为主叫号码）。 您可以了解有关如何使用您的组织中的呼叫者 ID，转[如何可以呼叫者 ID 是您组织中使用](how-can-caller-id-be-used-in-your-organization.md)的详细信息。
  
> [!TIP]
> 不能阻止当前在 Skype for Business Online 中的传入呼叫。 
  
你可以更改以下设置：
  
> [!NOTE]
> [!注释] 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。
  
- **更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。
    
    > [!NOTE]
    > [!注释] 如果要使用  _Service_ 参数，必须指定有效的服务号码。
  
- **阻止其出站呼叫者 ID**您可以阻止发送用户的传出 PSTN 呼叫传出的呼叫者 ID。 执行此操作将阻止其电话号码显示在被呼叫者的电话上。
    
- **阻止其传入的呼叫者 ID**您可以阻止用户接收任何传入 PSTN 呼叫的呼叫者 ID。
    
> [!IMPORTANT]
> [!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。 
  
默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。
  
要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>设置你的来电显示策略设置

> [!NOTE]
> 对于所有的呼叫者 ID 设置 Skype 中的业务 Online，您必须使用 Windows PowerShell 和您**不能使用****业务管理中心的 Skype**。 
  
### <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. 若要验证您运行版本 3.0 或更高：**开始菜单** > **Windows PowerShell**。
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. 从 **开始菜单** > **Windows PowerShell** 。
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>查看你组织中的所有来电显示策略设置

- 若要查看您的组织中的所有呼叫者 ID 策略设置，请运行：

  ```
  Get-CsCallingLineIdentity |fl
  ```
有关[获取 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)，请参阅更多示例和详细信息。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>为你的组织创建新的来电显示策略


- 若要创建新的呼叫者 ID 策略将呼叫者 ID 设置为匿名，请运行：
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 在所有情况下，在"服务号码"字段不应包含初始"+"。

  用于[新建 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)，请参阅更多示例和详细信息。
    
- 若要向 Amos 大理石应用您创建的新策略，请运行：
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。
    
如果您已经创建策略，可以使用[集 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet 可以更改现有的策略，并将[授予 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 将设置应用于您的用户。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>对其进行设置以阻止传入来电显示

- 若要阻止的传入呼叫者 ID，请运行：
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  有关[设置 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)，请参阅更多示例和详细信息。
    
- 若要向您的组织中的用户应用您创建的策略设置，请运行：
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。
    
### <a name="remove-a-caller-id-policy"></a>删除来电显示策略

要删除组织的策略，请运行：
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
要删除用户的策略，请运行：
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由） ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[更多关于呼叫线路 ID 和主叫方名称的信息](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
