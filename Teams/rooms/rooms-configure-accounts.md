---
title: 配置 Microsoft Teams 会议室的帐户
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 阅读本主题，了解如何在 Exchange 和 Skype for Business 中配置 Microsoft Teams 会议室的帐户。
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117470"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>配置 Microsoft Teams 会议室的帐户
 
阅读本主题，了解 Microsoft Teams 会议室及其如何与 Exchange 和 Skype for Business 集成。
  
本主题介绍了如何在 Microsoft Exchange 和 Skype for Business 中创建 Microsoft Teams 会议室使用的帐户。 配置 Microsoft Teams 会议室控制台 中介绍了 [Microsoft Teams 会议室设备的部署说明](console.md)。 你的基础结构很可能属于以下配置之一：
  
- 联机部署：组织的环境完全部署在 Microsoft 365 或 Office 365 上。 有关详细信息，请参阅使用 [Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室](with-office-365.md)。
    
- 本地部署：组织有它所控制的服务器，其中托管 Active Directory、Exchange 和 Skype for Business Server。 有关详细信息，请参阅使用 [Skype for Business Server 部署 Microsoft Teams 会议室](with-skype-for-business-server-2015.md)
    
- 混合部署：组织混合了一些服务，其中一些托管在本地，一些通过 Microsoft 365 或 Office 365 联机托管。 使用 Microsoft Teams 会议室时，支持以下混合方案：
    
  - 将 Exchange Online 与本地 Skype for Business Server 相连接。 有关详细信息，请参阅使用 Exchange Online 部署[Microsoft Teams 会议室 (混合) 。 ](with-exchange-online.md)
    
  - 使用 Microsoft Teams 或 Skype for Business Online 在本地交换。 有关详细信息，请参阅使用本地 Exchange 部署[Microsoft Teams 会议室 (混合) 。 ](with-exchange-on-premises.md)
    
你所拥有的配置类型将影响设备设置的准备方式。
  
需要在 Active Directory、Exchange 和 Skype for Business 中为 Microsoft Teams 会议室分配"设备帐户"。 该帐户用于访问其会议日历并建立 Microsoft Teams 或 Skype for Business 连接。 用户可通过使用此帐户安排会议来预订此帐户。 Microsoft Teams 会议室将能够加入该会议，并为与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有设备帐户，这些功能都不起作用。 
  
每个设备帐户对于单个 Microsoft Teams 会议室设备都是唯一的，并且需要进行一些设置：
  
- 必须正确配置设备帐户。
    
- 必须将基础结构配置为允许 Microsoft Teams 会议室验证设备帐户并访问相应的 Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 

在混合环境中，用于 Microsoft Teams 会议室的帐户必须在 Azure Active Directory (AAD) Sync 中启用密码同步，因为 Microsoft Teams 会议室身份验证需要 Microsoft 365 或 Office 365 身份验证。 设置帐户时，请确保帐户的 SIP 地址与 AAD 中的 UPN (用户主体名称) 匹配。 
  
可以将设备帐户视为用户识别为会议室或会议空间帐户的资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 为了最有效地使用 Microsoft Teams 会议室，请对分配给每个聊天室的设备帐户执行相同的操作。
  
如果已针对要安装 Microsoft Teams 会议室的会议空间设置了资源邮箱帐户，可以将该资源帐户更改为设备帐户。 完成后，只需将设备帐户添加到 Microsoft Teams 会议室设备。 请参阅下面提供的设备帐户设置示例。
  
通过附加配置，可以如使用 [Azure Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室管理、使用 Azure Monitor 部署 Microsoft Teams 会议室管理和使用 Azure Monitor 管理 Microsoft [Teams](azure-monitor-deploy.md)会议室设备中所述，使用 Microsoft Azure Monitor 进行 [远程管理](azure-monitor-manage.md)。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示设备帐户使用 Microsoft Teams 会议室的最低配置。 你的设备帐户可能需要进一步设置。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)   <br/> |通过启用 Exchange 邮箱的帐户，设备帐户能够接收和发送邮件和会议请求，以及显示 Microsoft Teams 会议室设备上的会议日历。 Microsoft Teams 会议室邮箱必须是会议室邮箱。  <br/> |
|Skype for Business 已启用  <br/> |必须启用 Skype for Business 才能使用各种会议功能，例如视频呼叫、即时消息和屏幕共享。 支持 Skype for Business Online 和 Skype for Business Server。  <br/> |
|已启用密码  <br/> |设备帐户必须使用密码启用，否则无法使用 Exchange 或 Skype for Business Server 进行身份验证。  <br/> |
   
## <a name="advanced-configuration"></a>高级配置

尽管基本配置的属性允许在简单环境中设置设备帐户，但环境可能对目录帐户有其他限制，必须满足这些限制，Microsoft Teams 会议室才能成功使用设备帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |Exchange 和 Skype for Business Server 可能需要证书。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置设备帐户的最简单方法是使用远程客户端配置Windows PowerShell。 Microsoft [ 提供了SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此脚本可帮助创建新的设备帐户或验证现有资源帐户，以帮助将其转换为兼容的 Microsoft Teams 会议室设备帐户。
  
如果您希望使用 Microsoft 365 或 Office 365 UI Windows PowerShell cmdlet，可以手动执行某些步骤。 请参阅 [使用 Microsoft 365 或 Office 365 创建设备帐户](/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)