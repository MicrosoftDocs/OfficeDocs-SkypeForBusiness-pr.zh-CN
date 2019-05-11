---
title: 集成本地统一消息与 Skype for Business 的部署过程概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要： 查看 while planning to Exchange 2013 或 2016年业务服务器集成 Skype 本主题。
ms.openlocfilehash: 20523415fb3692f97931f907e636a5433aa25514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907218"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>集成本地统一消息与 Skype for Business 的部署过程概述
 
**摘要：** While planning to Exchange 2013 或 2016年业务服务器集成 Skype 查看以下主题。
  
 如果您想要将 Exchange 统一消息 (UM) 与 Skype 集成业务服务器，必须执行本主题中列出的任务。 还要确保您查看[Plan for Business 的 Skype 中的 Exchange 统一消息集成](unified-messaging.md)中所述的规划和部署最佳做法。 本主题假设已并置的中介服务器与业务服务器部署 Skype 并您为启用了用户的 Skype 企业服务器，但可能不执行所有的部署和配置步骤，若要为启用企业语音部署文档中的描述在[部署中的业务服务器 Skype 的企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
 
> [!NOTE]
> Exchange 统一消息为以前已知不再可用的业务服务器 2019，使用电话系统来记录中的语音邮件，然后用户的 Exchange 邮箱中保留录制的 Skype 中。 有关详细信息，请参阅[规划语音邮件云服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
 
## <a name="unified-messaging-integration-process"></a>统一消息集成过程

> [!IMPORTANT]
> 非常重要，您与贵组织的 Exchange 管理员协调确认任务的每个您将执行以帮助确保顺利而又成功地集成。 
  
|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|部署下列各项之一：  <br/> • 邮箱  <br/> Microsoft Exchange Server 2010 或最新 service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果您使用 Microsoft Exchange Server 2013，安装下列 Exchange Server 角色在同一个林或另一个林 Skype 业务服务器：  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果在不同的林中安装 Microsoft Exchange Server 2013 和 Exchange 统一消息 (UM)，配置每个 Exchange 林信任的业务 Server 林 Skype。  <br/> 如果您使用 Exchange 2010，安装下列 Exchange Server 角色在同一个林或另一个林 Skype 业务服务器：  <br/> • 统一消息  <br/> • 集线器传输  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果在不同的林中安装 Business Server 和 Exchange 统一消息 (UM) 的 Skype，配置每个 Exchange 林信任的业务 Server 林 Skype。  <br/> |企业管理员（如果这是组织中的第一个 Exchange Server）  <br/> - 或者 -  <br/> Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）  <br/> |请参阅适用于您的 Exchange Server 版本的文档：  <br/> Exchange Server 2010 或最新 service pack 部署文档 <br/> Exchange Server 2013 规划和 DeploymentExchange 服务器 2016年规划和部署|
|安装证书。  <br/> |下载并安装证书的每台 Exchange UM 服务器从受信任的根证书颁发机构 (CA)。 证书所需的相互传输级别安全性 (MTLS) 之间的业务服务器运行 Exchange UM 和 Skype 的服务器。  <br/> |管理员  <br/> |[在运行 Exchange Server 统一消息的服务器上配置证书](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|创建和配置新的 Exchange UM SIP 拨号计划。  <br/> |在 Exchange UM 服务器上，创建一个 SIP 拨号计划，根据组织的特定部署要求。  <br/> |Exchange 组织管理员  <br/> | [配置 Microsoft Exchange Server 统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|配置 Exchange UM SIP 拨号计划的安全设置。  <br/> |若要加密企业语音通信，请上的 Exchange UM SIP 拨号计划配置为**SIP 安全**或**安全**配置的安全设置。 这是特别重要的步骤，如果已部署或 plan to deploy 环境中的 Lync Phone Edition 设备。 为 Lync Phone Edition 设备才能使用 Exchange UM 集成环境中，业务服务器加密设置的 Skype 必须与 Exchange UM 拨号计划安全性设置相一致。 有关详细信息，请参考部署文档。  <br/> |Exchange 组织管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，另请参阅：  <br/> [配置 VoIP 安全性 UM 拨号计划](https://go.microsoft.com/fwlink/p/?LinkId=268697)。  <br/> 有关 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|添加统一消息服务器添加到 Exchange UM SIP 拨号计划。  <br/> |要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，将服务器添加到 Exchange UM SIP 拨号计划。  <br/> |管理员  <br/> Exchange Server 管理员  <br/> |对于 Exchange 2010 或最新 service pack，请参阅[查看或配置 UM 服务器的属性](https://go.microsoft.com/fwlink/p/?linkId=268682)。  <br/> 有关 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|配置使用 SIP 地址的邮箱。  <br/> |将 Exchange UM 功能使用的企业语音用户的邮箱分配 SIP 地址。  <br/> |Skype 业务服务器管理员  <br/> Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新 service pack，请参阅[修改启用了 um 用户 SIP 地址](https://go.microsoft.com/fwlink/p/?LinkId=268699)。  <br/> 有关 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|运行 exchucutil.ps1 脚本。  <br/> |在服务器上运行 Exchange UM 服务，打开 Exchange Management Shell 并运行 exchucutil.ps1 脚本，这会执行以下： <br/> <br/> • 授予 Skype Business Server 权限读取 Exchange UM Active Directory 域服务对象，具体而言，SIP 拨号计划在上一任务中创建。  <br/><br/> • 创建一个统一消息 IP 网关对象在 Active Directory 中的业务 Server 企业版池或 Standard Edition server 的每个 Skype 用户所在的启用了企业语音。  <br/><br/> • 创建每个网关的 Exchange UM 智能寻线组。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。  <br/> |Exchange 组织管理员  <br/> Exchange 收件人管理员  <br/> |[Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1](#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|为 Business Server 拨号计划配置 Skype。  <br/> |如果要与 Exchange 2010 集成，创建新的企业语音拨号计划名称相匹配的 Exchange UM 拨号计划完全限定的域名 (FQDN)。  <br/> **注意：** 您将需要执行此操作的每个 UM 拨号计划。 <br/> 如果要与 Exchange 2010 SP1 集成，确保已配置合适的全局/站点级别或池级别企业语音拨号计划。  <br/> **注意：** 如果要与 Exchange 2010 SP1 集成，业务服务器拨号计划和 Exchange UM SIP 拨号计划的名称 Skype 不需要匹配。 <br/> |RTCUniversalServerAdmins  <br/> |[创建或修改拨号计划中 Skype 业务服务器](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|运行 Exchange UM 集成工具。  <br/> | 业务服务器 Skype 上, 运行**ocsumutil.exe**，其中：  <br/>  创建订阅者访问和自动助理联系对象。 <br/>  验证存在名称与 Exchange UM 拨号计划 FQDN 相匹配的企业语音拨号计划。 如果您运行的 Exchange 2010 SP1 或更高版本、 拨号计划名称不需要匹配，并且您可以忽略有关此工具的警告。 <br/>  此工具的工作方式是，扫描 Active Directory 中的 Exchange UM 设置并允许 Skype 业务服务器的管理员可以查看、 创建和编辑联系人对象。 <br/> |RTCUniversalServerAdmins*和*RTCUniversalUserAdmins <br/> **重要：** 若要成功运行 ocsumutil.exe，用户必须属于这两个组。 <br/> **注意：** 若要创建联系对象，运行 ocsumutil.exe 的用户必须具有正确的权限，对新的联系对象存储在何处的 Active Directory 组织单位 (OU)。 可以通过运行 **Grant-CsOUPermission** cmdlet 授予此权限。 有关详细信息，请参阅 Business Server Management Shell 文档 Skype。 <br/> |[为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有必要，执行其他企业语音配置步骤。  <br/> |如果尚未在服务器或用户配置企业语音设置，请执行一个或多个以下操作：  <br/> • 部署和配置  <br/> 公用电话交换网 (PSTN) 网关和中介服务器  <br/> • 定义语音策略、 PSTN 用法记录和出站呼叫路由。  <br/> • 为用户启用企业语音。  <br/> • （可选） 与拨号计划配置特定用户。  <br/> 其他配置步骤可能需要具体取决于您启用企业语音功能。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |请参阅以下各节中的主题：  <br/> •[配置语音策略、 PSTN 用法记录和 Skype for Business 中的语音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[部署中的业务服务器 Skype 的企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|企业语音用户启用 Exchange UM。  <br/> |在 Exchange UM 服务器上，确保已创建了统一消息邮箱策略和每个用户都有一个唯一的分机号码分配，，然后启用统一消息的用户。  <br/> |Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新 service pack，请参阅[启用统一消息用户](https://go.microsoft.com/fwlink/p/?LinkId=268701)。  <br/> 有关 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
   




## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划 Exchange 统一消息集成](unified-messaging.md)
