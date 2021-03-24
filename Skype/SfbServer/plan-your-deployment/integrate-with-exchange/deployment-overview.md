---
title: 集成本地统一消息和 Skype for Business 的部署过程概述
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要：在计划将 Skype for Business Server 与 Exchange 2013 或 Exchange 2016 集成时，请查看本主题。
ms.openlocfilehash: c6b2e70e9975182d9b6790b42a1120f66584bc7d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101558"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>集成本地统一消息和 Skype for Business 的部署过程概述
 
**摘要：** 在计划将 Skype for Business Server 与 Exchange 2013 或 Exchange 2016 集成时，请查看本主题。
  
 如果要将 Exchange 统一消息 (UM) Skype for Business Server 集成，则必须执行本主题中概述的任务。 此外，请务必查看 Plan [for Exchange Unified Messaging integration in Skype for Business](unified-messaging.md)中所述的规划和部署最佳做法。 本主题假定你已使用并并的中介服务器部署了 Skype for Business Server，并且你为用户启用了 Skype for Business Server，但你可能尚未执行所有部署和配置步骤来启用 企业语音，如部署文档中的在 [Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 中部署 企业语音 中所述。
 
> [!NOTE]
> 以前已知的 Exchange 统一消息在 Skype for Business Server 2019 中不再可用，Skype for Business Server 2019 使用电话系统录制语音邮件消息，然后将录音留在用户的 Exchange 邮箱中。 有关详细信息 [，请参阅规划](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 云语音邮件服务。
 
## <a name="unified-messaging-integration-process"></a>统一消息集成过程

> [!IMPORTANT]
> 与组织的 Exchange 管理员进行协调以确认每个人将执行的任务以帮助确保顺利、成功的集成，这一点非常重要。 
  
|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|部署下列各项之一：  <br/> • 邮箱  <br/> Microsoft Exchange Server 2010 或最新的 Service Pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果使用的是 Microsoft Exchange Server 2013，请在同一Exchange Server或与 Skype for Business Server 不同的林中安装以下角色：  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果Microsoft Exchange Server 2013 和 Exchange 统一消息 (UM) 安装在不同的林中，请配置每个 Exchange 林以信任 Skype for Business Server 林。  <br/> 如果使用的是 Exchange 2010，请在同一林Exchange Server Skype for Business Server 的不同林中安装以下角色：  <br/> • 统一消息  <br/> • 集线器传输  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果 Skype for Business Server 和 Exchange 统一 (UM) 安装在不同的林中，请配置每个 Exchange 林以信任 Skype for Business Server 林。  <br/> |企业管理员（如果这是组织中的第一个 Exchange Server）  <br/> - 或者 -  <br/> Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）  <br/> |请参阅适用于您的 Exchange Server 版本的文档：  <br/> Exchange Server 2010 或最新的 Service Pack 部署文档 <br/> Exchange Server 2013 规划和部署 <br/> Exchange Server 2016 规划和部署|
|安装证书。  <br/> |从 CA 信任根证书颁发机构下载并安装每个 Exchange UM (证书) 。 在运行 Exchange UM 和 Skype for Business Server 的服务器之间 (MTLS) 需要证书。  <br/> |管理员  <br/> |[在运行统一消息Exchange Server证书](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|创建和配置新的 Exchange UM SIP 拨号计划。  <br/> |在 Exchange UM 服务器上，根据组织的特定部署要求创建 SIP 拨号计划。  <br/> |Exchange 组织管理员  <br/> | [配置统一消息Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|配置 Exchange UM SIP 拨号计划的安全设置。  <br/> |若要加密企业语音流量，请配置 Exchange UM SIP 拨号计划上的安全设置为 **SIP 安全** 或 **安全**。 如果已部署或计划在你的环境中部署 Lync Phone Edition 设备，则这是一个非常重要的步骤。 为了在具有 Exchange UM 集成的环境中运行 Lync Phone Edition 设备，Skype for Business Server 加密设置必须与 Exchange UM 拨号计划安全设置一致。 有关详细信息，请参考部署文档。  <br/> |Exchange 组织管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，另请参阅：  <br/> [在 UM 拨号计划上配置 VoIP 安全性](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))。  <br/> 对于 Exchange 2013，请参阅 [统一消息](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|将统一消息服务器添加到 Exchange UM SIP 拨号计划。  <br/> |要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，将服务器添加到 Exchange UM SIP 拨号计划。  <br/> |管理员  <br/> Exchange Server 管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，请参阅 [查看或配置 UM 服务器的属性](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))。  <br/> 对于 Exchange 2013，请参阅 [统一消息](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|配置使用 SIP 地址的邮箱。  <br/> |将 SIP 地址分配给将企业语音 Exchange UM 功能的用户的邮箱。  <br/> |Skype for Business Server 管理员  <br/> Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，请参阅 [Modify a SIP Address for a UM-Enabled User](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))。  <br/> 对于 Exchange 2013，请参阅 [统一消息](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|运行 exchucutil.ps1 脚本。  <br/> |在运行 Exchange UM 服务的服务器上，打开 Exchange 命令行管理程序 并运行 exchucutil.ps1 脚本，这将执行以下操作： <br/> <br/> • 授予 Skype for Business Server 读取 Exchange UM Active Directory 域服务对象的权限，特别是以前任务中创建的 SIP 拨号计划。  <br/><br/> • 在 Active Directory 中为每个 Skype for Business Server Enterprise Edition 池或 Standard Edition Server 创建一个统一消息 IP 网关对象，该池或 Standard Edition Server 托管启用了 企业语音。  <br/><br/> • 为每个网关创建一个 Exchange UM 智能寻线。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。  <br/> |Exchange 组织管理员  <br/> Exchange 收件人管理员  <br/> |[在 Microsoft Exchange 上配置统一消息ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|配置 Skype for Business Server 拨号计划。  <br/> |如果要与 Exchange 2010 集成，请创建一个新的 企业语音 拨号计划，其名称与 Exchange UM 拨号计划的完全限定域名与 FQDN (匹配) 。  <br/> **注意：** 您需要针对每个 UM 拨号计划进行此操作。 <br/> 如果要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/站点级别或池企业语音拨号计划。  <br/> **注意：** 如果要与 Exchange 2010 SP1 集成，则 Skype for Business Server 拨号计划和 Exchange UM SIP 拨号计划名称不需要匹配。 <br/> |RTCUniversalServerAdmins  <br/> |[在 Skype for Business Server 中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|运行 Exchange UM 集成工具。  <br/> | 在 Skype for Business Server 上 **，ocsumutil.exe**，其中：  <br/>  创建订阅者访问和自动助理联系人对象。 <br/>  验证存在名称企业语音 Exchange UM 拨号计划 FQDN 的拨号计划。 如果运行的是 Exchange 2010 SP1 或更高版本，拨号计划名称不需要匹配，可以忽略工具的有关此的警告。 <br/>  此工具的工作方式是扫描 Active Directory 中的 Exchange UM 设置并允许 Skype for Business Server 管理员查看、创建和编辑联系人对象。 <br/> |RTCUniversalServerAdmins  *和*  RTCUniversalUserAdmins <br/> **重要提示：** 若要ocsumutil.exe运行，用户必须同时属于这两个组。 <br/> **注意：** 若要创建联系人对象，运行联系人ocsumutil.exe必须具有对存储新联系人对象的 Active Directory 组织单位 (OU) 的正确权限。 可通过运行 **Grant-CsOUPermission** cmdlet 授予此权限。 有关详细信息，请参阅 Skype for Business Server 命令行管理程序文档。 <br/> |[为Exchange Server Skype for Business Server 语音邮件配置统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有必要，执行其他企业语音配置步骤。  <br/> |如果尚未配置有关服务器或用户的企业语音设置，请执行下列一项或多项操作：  <br/> • 部署和配置  <br/> PSTN 网关和中介 (公用) 电话交换网  <br/> • 定义语音策略、PSTN 用法记录和出站呼叫路由。  <br/> • 为用户启用企业语音。  <br/> • （可选）使用拨号计划配置特定用户。  <br/> 可能还需要其他配置步骤，具体取决于启用的企业语音功能。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |请参阅以下各节中的主题：  <br/> •[在 Skype for Business 中配置语音策略、PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)用法记录和语音路由 <br/> • [企业语音 Skype for Business Server 中部署用户](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|为企业语音启用 Exchange UM。  <br/> |在 Exchange UM 服务器上，确保已创建统一消息邮箱策略，并且每个用户都有唯一的分机号码分配，然后为该用户启用统一消息。  <br/> |Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，请参阅 [为用户启用统一消息](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))。  <br/> 对于 Exchange 2013，请参阅 [统一消息](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
   




## <a name="see-also"></a>另请参阅

[规划 Skype for Business 中的 Exchange 统一消息集成](unified-messaging.md)