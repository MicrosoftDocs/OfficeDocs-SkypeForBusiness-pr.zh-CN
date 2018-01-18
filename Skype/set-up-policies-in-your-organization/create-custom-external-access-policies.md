---
title: "创建自定义的外部访问策略"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Skype 的在线业务允许您创建其他外部访问策略。 与不同的客户端或会议的策略，其中可以有多个组合，有三个预定义的外部访问策略，可以涵盖了大部分方案。"
ms.openlocfilehash: ffb08963d82af77f4d68c679b82bc8b8c44fa75f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="create-custom-external-access-policies"></a>创建自定义的外部访问策略

Skype 的在线业务允许您创建其他外部访问策略。 与不同的客户端或会议的策略，其中可以有多个组合，有三个预定义的外部访问策略，可以涵盖了大部分方案。 包括：
  
- 无联合或 Skype 使用者访问权限 (_标记： NoFederationAndPIC_ )
    
- 只有联合的访问 (_标记： FederationOnly_ )
    
- 联合和使用者访问 (_FederationAndPICDefault_)
    
自定义外部策略允许您创建其他不涉及上述设置的内容的策略。 当创建该策略时，您将需要设置所有必需的参数和以后无法更改它们。 创建新的自定义策略，可以控制功能，如 Skype 使用者的访问或策略来禁用公共云音频/视频，这是一些没有涉及使用预定义设置。 自定义外部访问策略，请按照与客户端、 移动性和会议策略相同的语法。 您可以了解有关这些设置的详细信息[在此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。
  
若要使此项工作，用户必须使用受支持的版本的 2016年点用 Skype 为支持它的业务应用程序。 以下的最小版本的 Skype 业务 2016年单击以运行客户机是必需的：
  
|**类型**|**发行日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|当前通道的第一版  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |1611 (Build 7571.2006) 版本  <br/> |
|当前通道  <br/> |2016 年 12/6  <br/> |16.0.7571.2072  <br/> |1611 (Build 7571.2072) 版本  <br/> |
|延迟的通道  <br/> |于 2017 2/22 年  <br/> |16.0.7369.2118  <br/> |1609 (Build 7369.2118) 版本  <br/> |
   
> [!CAUTION]
> 为业务窗口应用程序或 Mac 客户端使用 Skype 的较早版本的用户将仍能够传输文件。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. 若要验证正在运行版本 3.0 或更高: **「 开始 」 菜单** > **Windows PowerShell**。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. 从**「 开始 」 菜单** > **Windows PowerShell**。
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>创建用户自定义的外部访问策略

若要执行此操作，请运行：
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[块的点对点文件传输](block-point-to-point-file-transfers.md)

[设置您的组织的客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)
