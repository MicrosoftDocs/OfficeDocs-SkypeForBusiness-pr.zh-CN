---
title: 阻止点到点文件传输
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 在业务 online Skype，您可以控制现有会议策略设置的一部分 (P2P) 点对点文件传输功能。 但是，这将允许或阻止文件传输他们用户属于同一组织中或从另一个组织的联合用户传输的文件的用户。 下面的下面的步骤，您可以阻止与联盟的组织或合作伙伴的 P2P 文件传输。
ms.openlocfilehash: 3ae7bce22a99858af36696e1fde41bb614f2c008
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858488"
---
# <a name="block-point-to-point-file-transfers"></a>阻止点到点文件传输

在业务 online Skype，您可以控制现有会议策略设置的一部分 (P2P) 点对点文件传输功能。 但是，这将允许或阻止文件传输他们用户属于同一组织中或从另一个组织的联合用户传输的文件的用户。 下面的下面的步骤，您可以阻止与联盟的组织或合作伙伴的 P2P 文件传输。
  
 要允许内部用户使用 P2P 文件传输，但与联盟伙伴的阻止文件传输时非常常见方案。 对于此方案，您将需要执行操作：
  
- 与启用 P2P 文件传输 (_EnableP2PFileTransfer_将设置为_True_) 的会议策略分配给您组织中的用户。
    
- 创建全局外部用户通信策略设置来阻止外部 P2P 文件传输 （_EnableP2PFileTransfer_设置为_False_），并将其分配给您的组织中的用户。 
    
您可以了解这些设置的详细信息[此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。
  
如果组织外部的联合的用户试图将文件发送给用户其中应用了策略，他们将收到**转接失败**错误。 并且，如果用户尝试发送文件，他们将收到**处于关闭状态文件传输**错误。
  
若要使此项工作，用户必须使用 2016年单击即点即用 Skype 是受支持的版本支持的业务应用程序。 下面的最低版本的 Skype 业务 2016年单击即点即用客户端时，需要：
  
|**类型**|**发布日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|第一版当前通道  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |版本 1611 （构建 7571.2006）  <br/> |
|当前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 （构建 7571.2072）  <br/> |
|延迟的通道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 （构建 7369.2118）  <br/> |
   
> [!CAUTION]
> 使用较早版本的 Skype 业务 Windows 应用程序或 Mac 客户端的用户仍可以传输文件。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. 若要验证正在运行的版本是 3.0 或更高：**开始菜单** > **Windows PowerShell**。
    
2. 通过在**Windows PowerShell**窗口中键入_Get 主机_检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. 从 **开始菜单** > **Windows PowerShell**。
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>禁用组织的 P2P 文件传输

默认情况下，对组织的全局策略启用_EnableP2PFileTransfer_ 。 当创建它时，您的用户分配给_BposSAllModality_策略。
  
若要允许您组织但阻止的外部文件传输到另一个组织内的 P2P 传输，只需在全局级别更改它。 为此，请运行：
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>禁用的用户的 P2P 文件传输

您可以应用于此用户通过创建新策略，并授予该用户。 为此，请运行： 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 