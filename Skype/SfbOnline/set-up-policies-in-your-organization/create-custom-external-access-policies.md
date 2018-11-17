---
title: 创建自定义外部访问策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype 业务 online 允许您创建其他外部访问策略。 与客户端或会议策略，其中可以有多个的组合，有三个可以代替大多数的方案的预定义的外部访问策略。
ms.openlocfilehash: a822e09875bbef1fcd1472ac988a32cadfaf5850
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561693"
---
# <a name="create-custom-external-access-policies"></a>创建自定义外部访问策略

Skype 业务 online 允许您创建其他外部访问策略。 与客户端或会议策略，其中可以有多个的组合，有三个可以代替大多数的方案的预定义的外部访问策略。 包括：
  
- 无联盟或 Skype 使用者访问 (_标记： NoFederationAndPIC_ )
    
- 仅联盟的访问 (_标记： FederationOnly_ )
    
- 联盟和使用者访问 (_FederationAndPICDefault_)
    
自定义外部策略允许您创建其他策略不包含上面的设置的。 已创建策略，您将需要设置所有必需的参数和更高版本无法更改它们。 创建新的自定义策略允许您控制功能，如 Skype 使用者访问或一个策略来禁用公共云音频/视频，这是使用预定义的设置未涵盖的内容。 自定义外部访问策略按照语法与客户端和移动性、 会议策略相同。 您可以了解这些设置的详细信息[此处](https://technet.microsoft.com/en-us/library/mt228132.aspx)。
  
若要使此项工作，用户必须使用 2016年是受支持的版本支持的业务应用程序的单击即点即用 Skype。 下面的最低版本的 Skype 业务 2016年单击即点即用客户端时，需要：
  
|**类型**|**发布日期**|**版本**|**生成**|
|:-----|:-----|:-----|:-----|
|第一版当前通道  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |版本 1611 （构建 7571.2006）  <br/> |
|当前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 （构建 7571.2072）  <br/> |
|延迟的通道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 （构建 7369.2118）  <br/> |
   
> [!CAUTION]
> 使用较早版本的 Skype 业务 Windows 应用程序或 Mac 客户端的用户仍可以传输文件。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
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

   如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Windows PowerShell 将计算机设置](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>创建自定义外部访问策略的用户

若要执行此操作，请运行：
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[阻止点对点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 