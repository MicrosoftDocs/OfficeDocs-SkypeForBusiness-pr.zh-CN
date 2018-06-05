---
title: 配置帐户 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: 阅读此主题以了解有关在 Exchange 配置帐户 Skype 会议室系统 v2 和 Skype 的业务服务器 2015年。
ms.openlocfilehash: 1aa6c3d9ca8d80f054550cfa167a7a75e032ef0f
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501374"
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a>配置帐户 Skype 会议室系统 v2
 
阅读本主题可了解 Skype 会议室系统 v2 以及如何将其集成 Exchange 与 Skype 的业务服务器 2015年。
  
本主题介绍如何创建用于通过在 Microsoft Exchange 和 Skype 的 Skype 会议室系统 v2 业务服务器 2015年的帐户。 Skype 会议室系统 v2 设备的部署说明涵盖在[配置 Skype 会议室系统 v2 控制台](console.md)。 你的基础结构很可能属于以下配置之一：
  
- Online 部署： 完全在 Office 365 上部署您的组织的环境。 有关详细信息，请参阅[Office 365 的部署 Skype 会议室系统 v2](with-office-365.md)。
    
- 本地部署： 贵组织拥有的它控制，服务器承载 Active Directory、 Exchange 和 Skype 的业务服务器 2015年。 有关详细信息，请参阅[部署 Skype 会议室系统 v2 与 Skype 的业务服务器 2015](with-skype-for-business-server-2015.md)
    
- 混合部署： 贵组织拥有一些部署和一些在线承载通过 Office 365 上承载的服务，组合。 与 Skype 会议室系统 v2 支持以下混合方案： 
    
  - Exchange Online 与 Skype 的本地业务服务器 2015年。 有关详细信息，请参阅[与 Exchange Online （混合） 的部署 Skype 会议室系统 v2](with-exchange-online.md)。
    
  - 在本地与 Skype 的 exchange online 业务。 有关详细信息，请参阅[与 Exchange 本地 （混合） 的部署 Skype 会议室系统 v2](with-exchange-on-premises.md)。
    
你所拥有的配置类型将影响设备设置的准备方式。
  
Skype 会议室系统 v2 需要 Active Directory、 Exchange 和 Skype for Business 中分配"用户帐户"。 帐户用于访问其会议日历并建立 Skype 业务连接。 用户可通过使用此帐户安排会议来预订此帐户。 Skype 会议室系统 v2 都将能够加入的会议并向会议与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有用户帐户，所有功能都将不能使用。 
  
每个用户帐户是唯一的单个 Skype 会议室系统 v2 设备，并且需要进行一些设置：
  
- 必须对用户帐户进行正确配置。
    
- 必须将您的基础结构配置为允许 Skype 会议室系统 v2 来验证用户帐户，并获得相应的 Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 
  
您可以将用户帐户视为识别为会议会议室的或会议空间的帐户的人员的资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 若要最有效地使用 Skype 会议室系统 v2，您将执行与分配给每个用户帐户相同。
  
如果您已有资源邮箱帐户设置为正在安装 Skype 会议室系统 v2 的会议空间，可以将该资源帐户更改为用户帐户。 完成后，只需执行操作是将用户帐户添加到 Skype 会议室系统 v2 设备。 请参阅下面提供的用户帐户设置示例。
  
其他配置远程管理是可以[使用 OMS 的规划 Skype 会议室系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[使用 OMS 的部署 Skype 会议室系统 v2 管理](with-oms.md)和[管理中所述使用 Microsoft 操作管理套件 (OMS)OMS Skype 会议室系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示用户帐户以使用 Skype 会议室系统 v2 的最低配置。 你的用户帐户可能需要进行更多设置。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)  <br/> |启用 Exchange 邮箱的帐户提供的用户帐户接收和发送邮件和会议请求，并显示会议日历 Skype 会议室系统 v2 设备上的功能。 Skype 会议室系统 v2 邮箱必须会议室邮箱。  <br/> |
|启用 Skype for Business  <br/> |若要使用各种会议功能，如视频呼叫、 IM 和屏幕共享，必须启用 for Business 的 Skype。 支持的业务联机 Skype 和 Skype 业务服务器。  <br/> |
|已启用密码  <br/> |必须使用密码，启用的用户帐户或进行不能与 Exchange 或 Skype 业务服务器身份验证。  <br/> |
   
## <a name="advanced-configuration"></a>高级的配置

属性时的基本配置将允许在简单环境中，设置的用户帐户，则可能您的环境有其他限制的顺序的 Skype 会议室系统 v2 成功使用，必须满足的 directory 帐户用户帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |Exchange 和 Skype 业务服务器可能需要使用证书。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置用户帐户的最佳方式是它们使用远程 Windows PowerShell 进行配置。 Microsoft 提供的[SkypeRoomProvisioningScript.ps1](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomProvisioningScript.ps1.txt)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。
  
如果您希望使用 Windows PowerShell cmdlet 通过 Office 365 用户界面，可以手动执行一些步骤。 请参阅[创建设备帐户使用 Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

