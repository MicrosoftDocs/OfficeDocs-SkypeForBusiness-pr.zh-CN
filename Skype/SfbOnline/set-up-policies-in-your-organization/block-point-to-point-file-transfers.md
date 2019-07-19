---
title: 阻止点到点文件传输
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 在 Skype for Business Online 中, 你可以控制作为现有会议策略设置的一部分的点对点 (P2P) 文件传输。 但是, 这将允许或阻止用户将文件传输到同一组织中的用户或其他组织中的联盟用户。 按照以下步骤, 你可以阻止联盟组织或合作伙伴的 P2P 文件传输。
ms.openlocfilehash: 8e9f2bba654f2e44e4e7360f46730a6e1d2d9426
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792511"
---
# <a name="block-point-to-point-file-transfers"></a>阻止点到点文件传输

在 Skype for Business Online 中, 你可以控制作为现有会议策略设置的一部分的点对点 (P2P) 文件传输。 但是, 这将允许或阻止用户将文件传输到同一组织中的用户或其他组织中的联盟用户。 按照以下步骤, 你可以阻止联盟组织或合作伙伴的 P2P 文件传输。
  
 最常见的情况是, 您希望允许内部用户使用 P2P 文件传输, 但阻止与联盟伙伴进行的文件传输。 对于此方案, 你需要执行以下操作:
  
- 将已启用 P2P 文件传输的会议策略 (_EnableP2PFileTransfer_设置为_True_) 分配给组织中的用户。
    
- 创建全局外部用户通信策略集以阻止外部 P2P 文件传输 (_EnableP2PFileTransfer_设置为_False_), 并将其分配给组织中的用户。 
    
你可以在[此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)了解有关这些设置的详细信息。
  
如果组织外部的联盟用户尝试将文件发送到已应用策略的用户, 则它们将收到 "**传输失败**" 错误。 如果用户尝试发送文件, 他们将收到 "**已关闭文件传输**" 错误。
  
若要执行此操作, 用户必须使用支持版本的2016即点即用 Skype for business 应用 (支持它)。 需要以下最低版本的 Skype for Business 2016 即点即用客户端:
  
|**类型**|**发布日期**|**版本**|**版本号**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (内部版本 7571.2006)  <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (内部版本 7571.2072)  <br/> |
|延期频道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (内部版本 7369.2118)  <br/> |
   
> [!CAUTION]
> 使用旧版本的 Skype for Business Windows 应用或 Mac 客户端的用户仍能传输文件。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在**Windows PowerShell**窗口中键入_Get Host_检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。 出现提示时，请重启计算机。
    
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>为你的组织禁用 P2P 文件传输

默认情况下, 在组织的全局策略上启用_EnableP2PFileTransfer_ 。 创建后, 您的用户被分配了_BposSAllModality_策略。
  
若要允许组织内部的 P2P 传输, 但阻止外部文件传输到另一个组织, 只需在全局级别进行更改即可。 若要执行此操作, 请运行:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>为用户禁用 P2P 文件传输

你可以通过创建新策略并将其授予该用户来将其应用到用户。 若要执行此操作, 请运行: 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 365 管理中心, 例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 
