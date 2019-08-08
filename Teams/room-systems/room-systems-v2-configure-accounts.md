---
title: 为 Microsoft 团队聊天室配置帐户
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 阅读本主题, 了解如何在 Exchange 和 Skype for Business 中配置 Microsoft 团队聊天室的帐户。
ms.openlocfilehash: 30e887aa09b9013c3db18fb33133d11c639f9fe8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243318"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>为 Microsoft 团队聊天室配置帐户
 
阅读本主题, 了解 Microsoft 团队聊天室以及它与 Exchange 和 Skype for business 的集成方式。
  
本主题介绍如何在 Microsoft Exchange 和 Skype for Business 中创建 Microsoft 团队聊天室使用的帐户。 有关 Microsoft 团队聊天室设备的部署说明, 请在[配置 Microsoft 团队聊天室控制台](console.md)中介绍。 你的基础结构很可能属于以下配置之一：
  
- 联机部署: 你的组织的环境完全部署在 Office 365 上。 有关详细信息, 请参阅[通过 Office 365 部署 Microsoft 团队聊天室](with-office-365.md)。
    
- 本地部署: 你的组织具有其控制的服务器, 其中托管了 Active Directory、Exchange 和 Skype for business 服务器。 有关详细信息, 请参阅[用 Skype For Business 服务器部署 Microsoft 团队聊天室](with-skype-for-business-server-2015.md)
    
- 混合部署: 你的组织具有混合服务, 其中一些托管在本地, 而某些托管联机通过 Office 365。 在 Microsoft 团队聊天室中, 支持以下混合方案: 
    
  - 与本地 Skype for business 服务器的 Exchange Online。 有关详细信息, 请参阅[通过 Exchange Online (混合) 部署 Microsoft 团队聊天室](with-exchange-online.md)。
    
  - 与 Microsoft 团队或 Skype for business Online 的本地 Exchange。 有关详细信息, 请参阅[通过 Exchange on on-premises (混合) 部署 Microsoft 团队聊天室](with-exchange-on-premises.md)。
    
你所拥有的配置类型将影响设备设置的准备方式。
  
需要在 Active Directory、Exchange 和 Skype for Business 中为 Microsoft 团队会议室分配 "设备帐户"。 该帐户用于访问其会议日历, 建立 Microsoft 团队或 Skype for business 连接。 用户可通过使用此帐户安排会议来预订此帐户。 Microsoft 团队聊天室将能够加入该会议并向会议与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有设备帐户, 这些功能都将不起作用。 
  
每个设备帐户对单个 Microsoft 团队聊天室设备而言都是唯一的, 并且需要一些设置:
  
- 必须正确配置设备帐户。
    
- 你的基础结构必须配置为允许 Microsoft 团队聊天室验证设备帐户, 并访问相应的 Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 在混合环境中, 用于 Microsoft 团队聊天室的帐户必须在 AAD 同步中启用密码同步, 因为 Microsoft 团队聊天室身份验证需要 Office 365 身份验证。
  
你可以将设备帐户视为用户将其识别为会议室或会议空间的帐户的资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 为了最有效地使用 Microsoft 团队聊天室, 您可以使用分配给每个团队聊天室的设备帐户执行相同操作。
  
如果你已为安装 Microsoft 团队聊天室的会议空间设置了资源邮箱帐户, 则可以将该资源帐户更改为设备帐户。 完成后, 你需要做的就是将设备帐户添加到 Microsoft 团队聊天室设备。 请参阅下面提供的设备帐户设置示例。
  
有了其他配置, 使用 Microsoft Azure 监视器可以进行远程管理, 如使用[Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)、使用[Azure 监视器部署 microsoft 团队会议室管理](azure-monitor-deploy.md)和[通过 Azure 监视器管理 Microsoft 团队聊天室设备](azure-monitor-manage.md)。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示用于处理 Microsoft 团队聊天室的设备帐户的最低配置。 您的设备帐户可能需要进一步设置。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 邮箱 (Exchange 2013 SP1 或更高版本, 或 Exchange Online)  <br/> |启用具有 Exchange 邮箱的帐户将使设备帐户能够接收和发送邮件和会议请求, 并在 Microsoft 团队聊天室设备上显示会议日历。 Microsoft 团队聊天室邮箱必须是会议室邮箱。  <br/> |
|已启用 Skype for Business  <br/> |必须启用 Skype for Business 才能使用各种会议功能, 如视频通话、即时消息和屏幕共享。 Skype for business Online 和 Skype for business 服务器均受支持。  <br/> |
|已启用密码  <br/> |必须使用密码启用设备帐户, 或者不能通过 Exchange 或 Skype for business 服务器进行身份验证。  <br/> |
   
## <a name="advanced-configuration"></a>高级配置

虽然基本配置的属性将允许在简单环境中设置设备帐户, 但你的环境可能对必须满足的目录帐户具有其他限制, 以便 Microsoft 团队聊天室成功使用设备帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |Exchange 和 Skype for business 服务器可能都需要证书。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置设备帐户最简单的方法是使用远程 Windows PowerShell 进行配置。 Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105), 该脚本将帮助创建新的设备帐户, 或验证你拥有的现有资源帐户, 以帮助你将它们转换为兼容的 Microsoft 团队聊天室设备帐户。
  
如果你希望通过 Windows PowerShell cmdlet 使用 Office 365 UI, 则可以手动执行某些步骤。 请参阅[使用 Office 365 创建设备帐户](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)

