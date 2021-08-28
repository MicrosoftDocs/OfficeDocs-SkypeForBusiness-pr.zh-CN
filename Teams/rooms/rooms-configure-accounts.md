---
title: 配置帐户Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 阅读本主题，了解如何在 Microsoft Teams 会议室 和 Exchange Skype for Business 中配置Skype for Business。
ms.openlocfilehash: 2c6a4e369c45bb624e40400339bbc43b7ac20234
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611521"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>配置帐户Microsoft Teams 会议室
 
阅读本主题，了解Microsoft Teams 会议室及其如何与 Exchange Skype for Business。
  
本主题介绍了如何创建 Microsoft Microsoft Teams 会议室 和 Exchange Skype for Business。 配置 Microsoft Teams 会议室 控制台 中介绍了Microsoft Teams 会议室[设备的部署说明](console.md)。 你的基础结构很可能属于以下配置之一：
  
- 联机部署：组织的环境完全部署在Microsoft 365 Office 365。 有关详细信息，请参阅使用 Microsoft Teams 会议室 或 Microsoft 365[部署Office 365。](with-office-365.md)
    
- 本地部署：组织有它控制的服务器，其中 Active Directory、Exchange和Skype for Business Server托管。 有关详细信息，请参阅使用 Microsoft Teams 会议室[部署Skype for Business Server](with-skype-for-business-server-2015.md)
    
- 混合部署：组织混合了一些服务，其中一些托管在本地，一些通过本地或 Microsoft 365 联机Office 365。 使用Microsoft Teams 会议室，支持以下混合方案：
    
  - Exchange Online本地Skype for Business Server部署。 有关详细信息，请参阅使用混合Microsoft Teams 会议室[部署Exchange Online () 。 ](with-exchange-online.md)
    
  - Exchange本地使用 Microsoft Teams 或 Skype for Business Online。 有关详细信息，请参阅使用本地Microsoft Teams 会议室[部署Exchange混合 () 。 ](with-exchange-on-premises.md)
    
你所拥有的配置类型将影响设备设置的准备方式。
  
Microsoft Teams 会议室 Active Directory、Exchange 和 Skype for Business。 该帐户用于访问其会议日历并建立Microsoft Teams或Skype for Business连接。 用户可通过使用此帐户安排会议来预订此帐户。 Microsoft Teams 会议室将能够加入该会议，并为与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有设备帐户，这些功能都不起作用。 
  
每个设备帐户对于单个设备Microsoft Teams 会议室唯一，并且需要进行一些设置：
  
- 必须正确配置设备帐户。
    
- 必须将基础结构配置为允许Microsoft Teams 会议室验证设备帐户，并访问相应的Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 

在混合环境中，用于 Microsoft Teams 会议室 的帐户必须在 Azure Active Directory (AAD) Sync 中启用密码同步，因为 Microsoft Teams 会议室 身份验证需要 Microsoft 365 或 Office 365 身份验证。 设置帐户时，请确保帐户的 SIP 地址与 AAD 中的 UPN (用户主体名称) 匹配。 
  
可以将设备帐户视为用户识别为会议室或会议空间帐户的资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 为了最Microsoft Teams 会议室，请对分配给每个帐户的设备帐户执行相同的操作。
  
如果已针对要安装资源的会议空间设置了资源邮箱帐户Microsoft Teams 会议室，可以将该资源帐户更改为设备帐户。 完成后，只需将设备帐户添加到 Microsoft Teams 会议室 设备。 请参阅下面提供的设备帐户设置示例。
  
通过附加配置，Microsoft Azure Monitor 实现远程管理，如使用[Azure Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室 管理、使用 Azure Monitor 部署 Microsoft Teams 会议室 管理以及使用[Azure Monitor](azure-monitor-manage.md)管理[Microsoft Teams 会议室](azure-monitor-deploy.md)设备中所述。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示设备帐户使用 Microsoft Teams 会议室。 你的设备帐户可能需要进一步设置。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 2013 SP1 (Exchange更高版本的邮箱，或 Exchange Online)   <br/> |通过启用具有 Exchange 邮箱的帐户，设备帐户能够接收和发送邮件和会议请求，以及显示 Microsoft Teams 会议室 日历。 Microsoft Teams 会议室邮箱必须是会议室邮箱。  <br/> |
|Skype for Business已启用  <br/> |Skype for Business启用此功能才能使用各种会议功能，例如视频呼叫、即时消息和屏幕共享。 支持Skype for Business Online 和 Skype for Business Server。  <br/> |
|已启用密码  <br/> |设备帐户必须使用密码启用，或者无法使用密码或Exchange Skype for Business Server。  <br/> |
   
## <a name="advanced-configuration"></a>高级配置

尽管基本配置的属性允许在简单环境中设置设备帐户，但环境可能对目录帐户有其他限制，必须满足这些限制，Microsoft Teams 会议室 才能成功使用设备帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |证书可能需要用于Exchange Skype for Business Server。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置设备帐户的最简单方法是使用远程客户端配置Windows PowerShell。 Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的设备帐户或验证现有资源帐户，以帮助将其转换为兼容的设备Microsoft Teams 会议室帐户。
  
如果你希望使用 Microsoft 365 或 Office 365 UI Windows PowerShell cmdlet，可以手动执行某些步骤。 请参阅[使用 Microsoft 365 或 Office 365 创建设备帐户](/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)