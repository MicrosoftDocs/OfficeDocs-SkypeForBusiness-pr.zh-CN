---
title: 为你的组织设置客户端策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
ms.openlocfilehash: 14d023598a27c676fd4249e97e6454b8110ee958
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297715"
---
# <a name="set-up-client-policies-for-your-organization"></a>为你的组织设置客户端策略

客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
  
客户端策略设置可以在创建策略时配置, 也可以使用**set-csclientpolicy** cmdlet 修改现有策略的设置。
  
## <a name="set-your-client-policies"></a>设置你的客户端策略

> [!NOTE]
> 对于 Skype for Business Online 中的所有客户端策略设置, 必须使用 Windows PowerShell, 并且**不能使用** **Skype for business 管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   如果需要有关启动 Windows PowerShell 的详细信息, 请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>禁用表情符和状态通知并阻止保存 Im

- 若要为这些设置创建新的策略, 请运行:
    
> 
>   ```
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的详细信息, 请参阅。
    
- 若要为你的组织中的所有用户授予你创建的新策略, 请运行:
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的详细信息, 请参阅。
    
如果你已创建策略, 你可以使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 对现有策略进行更改, 然后使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用到你的用户。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>启用要在即时消息中可单击的 URL 或超链接

- 若要为这些设置创建新的策略, 请运行:
    
> 
>   ```
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的详细信息, 请参阅。
    
- 若要为你的组织中的所有用户授予你创建的新策略, 请运行:
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的详细信息, 请参阅。
    
如果你已创建策略, 你可以使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 对现有策略进行更改, 然后使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用到你的用户。
  
### <a name="prevent-showing-recent-contacts"></a>禁止显示最近的联系人

- 若要为这些设置创建新的策略, 请运行:
  > 
  > ```
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的详细信息, 请参阅。
    
- 若要将您创建的新策略授予 Amos 大理石, 请运行:
  > 
  > ```
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  有关[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的详细信息, 请参阅。
    
  如果你已创建策略, 你可以使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 对现有策略进行更改, 然后使用[set-csclientpolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 将设置应用到你的用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 
