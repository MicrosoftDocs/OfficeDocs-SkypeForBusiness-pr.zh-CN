---
title: 集成本地统一消息和统一消息的部署Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要：在计划将 2013 Skype for Business Server 2016 Exchange本主题。
ms.openlocfilehash: 555a58d4497da2931666474399e8018c7178e892
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835090"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>集成本地统一消息和统一消息的部署Skype for Business
 
**摘要：** 在计划将 2013 Skype for Business Server 2016 Exchange本主题。
  
 如果要将统一消息Exchange UM () 与 Skype for Business Server 集成，则必须执行本主题中概述的任务。 此外，还请务必查看在 Exchange 中规划统一消息集成中所述的规划和部署[Skype for Business。](unified-messaging.md) 本主题假定你已使用并并的中介服务器部署了 Skype for Business Server，并且为用户启用了 Skype for Business Server，但您可能尚未执行所有部署和配置步骤来启用 企业语音，如 中的部署 企业语音 中所述[Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)中的说明。
 
> [!NOTE]
> Exchange以前已知的统一消息在 Skype for Business Server 2019 中不再可用，2019 使用 电话系统 录制语音邮件，然后将录制保留到用户的 Exchange 邮箱中。 有关详细信息[，请参阅云语音邮件](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)服务。
 
## <a name="unified-messaging-integration-process"></a>统一消息集成过程

> [!IMPORTANT]
> 与组织的管理员协调，Exchange以确认每个人将执行的任务，以帮助确保顺利、成功地进行集成，这一点非常重要。 
  
|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|部署下列各项之一：  <br/> • 邮箱  <br/> Microsoft Exchange Server 2010 或最新的 Service Pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果使用的是 Microsoft Exchange Server 2013，请在同一Exchange Server林或与 2013 不同的林中安装以下Skype for Business Server：  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果Microsoft Exchange Server 2013 Exchange统一消息 (UM) 安装在不同的林中，请配置每个 Exchange 林以信任 Skype for Business Server 林。  <br/> 如果使用的是 Exchange 2010，请在同一Exchange Server林或与 2010 不同的林中安装以下Skype for Business Server：  <br/> • 统一消息  <br/> • 集线器传输  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果Skype for Business Server Exchange统一消息 (UM) ，请配置每个 Exchange 林以信任该Skype for Business Server林。  <br/> |企业管理员（如果这是组织中的第一个 Exchange Server）  <br/> - 或者 -  <br/> Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）  <br/> |请参阅适用于您的 Exchange Server 版本的文档：  <br/> Exchange Server 2010 或最新的 Service Pack 部署文档 <br/> Exchange Server 2013 规划和部署 <br/> Exchange Server 2016 规划和部署|
|安装证书。  <br/> |从 CA 证书颁发Exchange信任根证书颁发机构下载并安装每个 UM (证书) 。 证书是相互传输级别安全性 (MTLS) 运行 UM Exchange服务器Skype for Business Server。  <br/> |管理员  <br/> |[在运行统一消息的Exchange Server配置证书](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|创建和配置新的 UM SIP Exchange UM SIP 拨号计划。  <br/> |在Exchange UM 服务器上，根据组织的特定部署要求创建 SIP 拨号计划。  <br/> |Exchange 组织管理员  <br/> | [配置统一消息Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|配置 UM SIP 拨号Exchange安全设置。  <br/> |若要加密企业语音，请配置 UM SIP 拨号计划上的安全设置Exchange SIP **安全或****安全**。 如果已部署或计划在你的环境中部署 Lync 电话 Edition 设备，则这是一个非常重要的步骤。 若要使 Lync 电话 Edition 设备在具有 um 集成的环境中Exchange，Skype for Business Server加密设置必须与 um 拨号Exchange安全设置一致。 有关详细信息，请参考部署文档。  <br/> |Exchange 组织管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，另请参阅：  <br/> [在 UM 拨号计划上配置 VoIP 安全性](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))。  <br/> 有关 Exchange 2013 的信息，请参阅[Unified Messaging](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|将统一消息服务器添加到统Exchange UM SIP 拨号计划。  <br/> |要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，将服务器添加到 um SIP Exchange拨号计划中。  <br/> |管理员  <br/> Exchange Server 管理员  <br/> |有关 Exchange 2010 或最新的 Service Pack 的信息，请参阅[查看或配置 UM 服务器的属性](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))。  <br/> 有关 Exchange 2013 的信息，请参阅[Unified Messaging](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|配置使用 SIP 地址的邮箱。  <br/> |将 SIP 地址分配给企业语音 UM 功能的用户Exchange SIP 地址。  <br/> |Skype for Business Server管理员  <br/> Exchange 收件人管理员  <br/> |有关 Exchange 2010 或最新的 Service Pack，请参阅[Modify a SIP Address for a UM-Enabled User](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))。  <br/> 有关 Exchange 2013 的信息，请参阅[Unified Messaging](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|运行 exchucutil.ps1 脚本。  <br/> |在运行 UM Exchange服务器上，Exchange命令行管理程序并运行 exchucutil.ps1 脚本，这将执行以下操作： <br/> <br/> • 授予Skype for Business Server读取 UM Active Directory Exchange服务对象的权限，特别是以前任务中创建的 SIP 拨号计划的权限。  <br/><br/> • 在 Active Directory 中为承载启用了统一消息的用户的每个 Skype for Business Server Enterprise Edition 池或 Standard Edition 服务器创建统一消息 IP 网关企业语音。  <br/><br/> • 为每个网关Exchange UM 智能寻线。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。  <br/> |Exchange 组织管理员  <br/> Exchange 收件人管理员  <br/> |[使用统一消息配置 Microsoft Exchange 统一ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|配置Skype for Business Server拨号计划。  <br/> |如果要与 Exchange 2010 集成，请创建一个新的 企业语音 拨号计划，其名称与 Exchange UM 拨号计划的完全限定域名 (FQDN) 。  <br/> **注意：** 您需要针对每个 UM 拨号计划进行此操作。 <br/> 如果要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/站点级别或池企业语音拨号计划。  <br/> **注意：** 如果要与 Exchange 2010 SP1 集成，Skype for Business Server拨号Exchange UM SIP 拨号计划名称不需要匹配。 <br/> |RTCUniversalServerAdmins  <br/> |[在拨号计划中创建或修改Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|运行 Exchange UM 集成工具。  <br/> | 在Skype for Business Server，运行 **ocsumutil.exe**，其中：  <br/>  创建订阅者访问和自动助理联系人对象。 <br/>  验证是否有名称企业语音 UM 拨号计划 FQDN Exchange拨号计划。 如果您运行的是 Exchange 2010 SP1 或更高版本，则拨号计划名称不需要匹配，可以忽略该工具的有关此名称的警告。 <br/>  此工具的工作方式是扫描 Active Directory Exchange UM 设置，并允许 Skype for Business Server管理员查看、创建和编辑联系人对象。 <br/> |RTCUniversalServerAdmins  *和*  RTCUniversalUserAdmins <br/> **重要提示：** 若要ocsumutil.exe运行，用户必须同时属于这两个组。 <br/> **注意：** 若要创建 Contact 对象，ocsumutil.exe必须对存储新联系人对象的 Active Directory 组织单位 (OU) 具有正确的权限。 可通过运行 **Grant-CsOUPermission** cmdlet 授予此权限。 有关详细信息，请参阅 Skype for Business Server命令行管理程序文档。 <br/> |[为Exchange Server语音邮件配置Skype for Business Server统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有必要，执行其他企业语音配置步骤。  <br/> |如果尚未配置有关服务器或用户的企业语音设置，请执行下列一项或多项操作：  <br/> • 部署和配置  <br/> PSTN 网关和中介 (公用) 电话交换网  <br/> • 定义语音策略、PSTN 用法记录和出站呼叫路由。  <br/> • 为用户启用企业语音。  <br/> • （可选）使用拨号计划配置特定用户。  <br/> 可能还需要其他配置步骤，具体取决于启用的企业语音功能。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |请参阅以下各节中的主题：  <br/> •[在呼叫中配置语音策略、PSTN 用法记录和Skype for Business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[企业语音部署Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|为企业语音 UM 启用Exchange用户。  <br/> |在 um Exchange上，确保已创建统一消息邮箱策略，并且每个用户都有唯一的分机号码分配，然后为该用户启用统一消息。  <br/> |Exchange 收件人管理员  <br/> |有关 Exchange 2010 或最新的 Service Pack 的信息，请参阅 Enable [a User for Unified Messaging](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))。  <br/> 有关 Exchange 2013 的信息，请参阅[Unified Messaging](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
   




## <a name="see-also"></a>另请参阅

[规划Exchange统一消息集成Skype for Business](unified-messaging.md)