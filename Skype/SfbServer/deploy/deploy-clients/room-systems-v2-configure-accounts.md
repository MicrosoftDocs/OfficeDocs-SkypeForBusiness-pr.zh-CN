---
title: 为 Microsoft 团队房间配置帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 阅读本主题以了解如何在 Exchange 配置帐户的 Microsoft 团队聊天室和 Skype 的业务。
ms.openlocfilehash: 7606f31dde96236111b4a44919427245fa32215d
ms.sourcegitcommit: 856793c99fc02fb016383d0b6f8411c386d78886
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "31828949"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>为 Microsoft 团队房间配置帐户
 
阅读此主题以了解有关 Microsoft 团队聊天室以及它如何与 Exchange 和 Skype 的业务集成。
  
本主题介绍如何创建 for Business 使用 Microsoft Exchange 和 Skype 中的 Microsoft 团队聊天室的帐户。 [配置 Microsoft 团队聊天室控制台](console.md)中介绍了 Microsoft 团队聊天室设备的部署说明。 你的基础结构很可能属于以下配置之一：
  
- Online 部署： 完全在 Office 365 上部署您的组织的环境。 有关详细信息，请参阅[与 Office 365 部署 Microsoft 团队的聊天室](with-office-365.md)。
    
- 本地部署： 贵组织拥有的它控制，服务器承载 Active Directory、 Exchange 和 Skype 业务服务器。 有关详细信息，请参阅[与 Skype 的业务服务器中部署 Microsoft 团队聊天室](with-skype-for-business-server-2015.md)
    
- 混合部署： 贵组织拥有一些部署和一些在线承载通过 Office 365 上承载的服务，组合。 与 Microsoft 团队聊天室，支持以下混合方案： 
    
  - Exchange Online 与 Skype 的本地业务服务器。 有关详细信息，请参阅[与 Exchange Online （混合） 部署 Microsoft 团队的聊天室](with-exchange-online.md)。
    
  - 在本地与 Skype 的 exchange online 业务。 有关详细信息，请参阅[与 Exchange 本地 （混合） 部署 Microsoft 团队的聊天室](with-exchange-on-premises.md)。
    
你所拥有的配置类型将影响设备设置的准备方式。
  
Microsoft 团队聊天室需要 Active Directory、 Exchange 和 Skype for Business 中分配"设备帐户"。 帐户用于访问其会议日历并建立 Skype 业务连接。 用户可通过使用此帐户安排会议来预订此帐户。 Microsoft 团队聊天室都将能够加入的会议并向会议与会者提供各种功能。
  
> [!IMPORTANT]
> 没有设备帐户，无这些功能将工作。 
  
每个设备的帐户是唯一的单个 Microsoft 团队聊天室设备，并且需要进行一些设置：
  
- 必须正确配置的设备帐户。
    
- 必须将您的基础结构配置为允许 Microsoft 团队聊天室验证设备帐户，并获得相应的 Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 在混合环境中用于 Microsoft 团队聊天室的帐户必须具有启用在 AAD 同步，因为 Microsoft 团队聊天室身份验证要求 0ffice 365 身份验证的密码同步。
  
您可以将设备帐户视为识别为会议会议室的或会议空间的帐户的人员的资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 为了最有效地使用 Microsoft 团队聊天室，则执行与分配给每个设备帐户相同。
  
如果您已有资源邮箱帐户设置为正在安装 Microsoft 团队会议室的会议空间，可以将该资源帐户更改为设备帐户。 完成后，您需要执行操作是将设备帐户添加到 Microsoft 团队聊天室设备。 请参阅下面提供了设备帐户安装程序示例。
  
其他配置远程管理是可以[使用 Azure 监视器规划 Microsoft 团队聊天室管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md)、[部署 Microsoft 团队聊天室管理使用 Azure 监视器](azure-monitor.md)和[中所述使用 Microsoft Azure 监视器管理使用 Azure 监视器的 Microsoft 团队聊天室设备](../../manage/skype-room-systems-v2/azure-monitor.md)。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示要使用 Microsoft 团队聊天室的设备帐户的最低配置。 您的设备帐户可能需要进一步的安装程序。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)  <br/> |启用 Exchange 邮箱的帐户授予设备帐户接收和发送邮件和会议请求，并显示会议日历 Microsoft 团队聊天室设备上的功能。 Microsoft 团队会议室邮箱必须会议室邮箱。  <br/> |
|启用 Skype for Business  <br/> |若要使用各种会议功能，如视频呼叫、 IM 和屏幕共享，必须启用 for Business 的 Skype。 支持的业务联机 Skype 和 Skype 业务服务器。  <br/> |
|已启用密码  <br/> |设备帐户必须启用使用的密码，或进行不能与 Exchange 或 Skype 业务服务器身份验证。  <br/> |
   
## <a name="advanced-configuration"></a>高级的配置

属性时的基本配置将允许设备帐户设置在简单环境中，则可能您的环境有其他限制的顺序的 Microsoft 团队会议室成功使用，必须满足的 directory 帐户设备的帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |Exchange 和 Skype 业务服务器可能需要使用证书。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置设备帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。 Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的设备帐户，或验证必须以帮助您将它们转换为兼容的 Microsoft 团队聊天室设备帐户的现有资源帐户。
  
如果您希望使用 Windows PowerShell cmdlet 通过 Office 365 用户界面，可以手动执行一些步骤。 请参阅[创建设备帐户使用 Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

[规划 Microsoft 团队聊天室](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft 团队聊天室](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

