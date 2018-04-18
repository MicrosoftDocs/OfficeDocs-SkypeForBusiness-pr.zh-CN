---
title: 块点对点文件传输
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 在 Skype 的在线业务，必须能够控制点对点 (P2P) 文件传输作为会议的现有策略设置的一部分。 但是，这样，或阻止文件传输它们传输文件，同一组织中的用户或另一个组织中的联合用户的用户。 按照下面的步骤中，您可以阻止联盟的组织或伙伴的 P2P 文件传输。
ms.openlocfilehash: e73a2baa8368d3ed1c20a79e8f78010749c05fb2
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="block-point-to-point-file-transfers"></a>块点对点文件传输

在 Skype 的在线业务，必须能够控制点对点 (P2P) 文件传输作为会议的现有策略设置的一部分。 但是，这样，或阻止文件传输它们传输文件，同一组织中的用户或另一个组织中的联合用户的用户。 按照下面的步骤中，您可以阻止联盟的组织或伙伴的 P2P 文件传输。
  
 非常常见的情况是当您想要允许使用 P2P 文件传输，但阻止文件传输与联盟伙伴的内部用户。 这种情况下，您将需要为此：
  
- 为会议策略分配到您组织中的用户启用了 P2P 文件传输 (_EnableP2PFileTransfer_设置为_True_)。
    
- 创建全局外部用户通信策略设置来阻止外部 P2P 文件传输 （_EnableP2PFileTransfer_设置为_False_），并将其分配给您的组织中的用户。 
    
您可以了解有关这些设置的详细信息[在此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。
  
如果尝试将文件发送给用户已在应用策略联盟的用户向组织外，他们将收到**传输失败**的错误。 并且，如果用户尝试发送文件时，用户将接收**文件传输已关闭**的错误。
  
若要使此项工作，用户必须使用 2016年点用 Skype 的受支持的版本支持的业务应用程序。 以下的最小版本的 Skype 业务 2016年单击以运行客户机是必需的：
  
|**类型**|**发行日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|当前通道的第一版  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |1611 (Build 7571.2006) 版本  <br/> |
|当前通道  <br/> |2016 年 12/6  <br/> |16.0.7571.2072  <br/> |1611 (Build 7571.2072) 版本  <br/> |
|延迟的通道  <br/> |于 2017 2/22 年  <br/> |16.0.7369.2118  <br/> |1609 (Build 7369.2118) 版本  <br/> |
   
> [!CAUTION]
> 为业务窗口应用程序或 Mac 客户端使用 Skype 的较早版本的用户将仍能够传输文件。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在**Windows PowerShell**窗口中键入_获取主机_检查版本。
    
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

  如果希望在启动 Windows PowerShell 的详细信息，请参阅[连接到一个 Windows PowerShell 窗口中的所有 Office 365 提供服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>禁用您的组织的 P2P 文件传输

默认情况下， _EnableP2PFileTransfer_是在组织的全局策略上启用的。 它被创建时，您的用户分配_BposSAllModality_策略。
  
若要允许为您组织但块的外部文件传输到另一个组织内的 P2P 传输，只需在全局级别更改它。 为此，请运行：
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>禁用用户的 P2P 文件传输

您可以将此应用到用户通过创建新的策略，并授予该用户。 为此，请运行： 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 