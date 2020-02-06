---
title: 集成本地统一消息与 Skype for Business 的部署过程概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时，请查看本主题。
ms.openlocfilehash: db6cdbf5297c2397acadcb65ad615533ae6dbe2f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815890"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>集成本地统一消息与 Skype for Business 的部署过程概述
 
**摘要：** 在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时，请查看此主题。
  
 如果要将 Exchange 统一消息（UM）与 Skype for Business 服务器集成，则必须执行本主题中所述的任务。 此外，请确保查看在[Skype For business 中规划 Exchange 统一消息集成](unified-messaging.md)中介绍的规划和部署最佳做法。 本主题假定你已使用 collocated 中介服务器部署了 Skype for business 服务器，并且已启用 Skype for business Server 的用户，但你可能尚未执行所有部署和配置步骤来启用企业语音，如在部署文档中的[Skype for Business 服务器中部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)时所述。
 
> [!NOTE]
> Skype for Business Server 2019 中不再提供 Exchange 统一消息，它使用电话系统录制语音邮件，然后将录制内容保留在用户的 Exchange 邮箱中。 有关详细信息，请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
 
## <a name="unified-messaging-integration-process"></a>统一消息集成过程

> [!IMPORTANT]
> 请务必与组织的 Exchange 管理员协调，以确认每个要执行的任务，以帮助确保顺利、成功的集成。 
  
|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|部署下列各项之一：  <br/> •邮箱  <br/> Microsoft Exchange Server 2010 或最新服务包  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |如果您使用的是 Microsoft Exchange Server 2013，请在与 Skype for business 服务器相同的林中或不同的林中安装以下 Exchange Server 角色：  <br/> •客户端访问  <br/> •邮箱  <br/> 如果 Microsoft Exchange Server 2013 和 Exchange 统一消息（UM）安装在不同的林中，请将每个 Exchange 林配置为信任 Skype for Business Server 林。  <br/> 如果您使用的是 Exchange 2010，请在与 Skype for business 服务器相同的林中或不同的林中安装以下 Exchange Server 角色：  <br/> •统一消息  <br/> •集线器传输  <br/> •客户端访问  <br/> •邮箱  <br/> 如果 Skype for business 服务器和 Exchange 统一消息（UM）安装在不同的林中，请将每个 Exchange 林配置为信任 Skype for business Server 林。  <br/> |企业管理员（如果这是组织中的第一个 Exchange Server）  <br/> - 或者 -  <br/> Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）  <br/> |请参阅适用于您的 Exchange Server 版本的文档：  <br/> Exchange Server 2010 或最新的 service pack 部署文档 <br/> Exchange Server 2013 规划和部署 <br/> Exchange Server 2016 规划和部署|
|安装证书。  <br/> |从受信任的根证书颁发机构（CA）下载并安装每个 Exchange UM 服务器的证书。 证书对于运行 Exchange UM 和 Skype for business 服务器的服务器之间的相互传输级别安全（MTLS）是必需的。  <br/> |管理员  <br/> |[在运行 Exchange Server 统一消息的服务器上配置证书](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|创建和配置新的 Exchange UM SIP 拨号计划。  <br/> |在 Exchange UM 服务器上，根据组织的特定部署要求创建 SIP 拨号计划。  <br/> |Exchange 组织管理员  <br/> | [在 Microsoft Exchange Server 上配置统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|配置 Exchange UM SIP 拨号计划的安全设置。  <br/> |若要对企业语音流量进行加密，请将 Exchange UM SIP 拨号计划中的安全设置配置为**SIP 安全**或**安全**。 如果你已部署或计划在你的环境中部署 Lync Phone Edition 设备，这是一个非常重要的步骤。 为了使 Lync Phone Edition 设备在具有 Exchange UM 集成的环境中正常工作，Skype for business 服务器加密设置必须与 Exchange UM 拨号计划安全设置相一致。 有关详细信息，请参考部署文档。  <br/> |Exchange 组织管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，另请参阅：  <br/> [在 UM 拨号计划上配置 VoIP 安全](https://go.microsoft.com/fwlink/p/?LinkId=268697)。  <br/> 对于 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|将统一消息服务器添加到 Exchange UM SIP 拨号计划。  <br/> |要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，将服务器添加到 Exchange UM SIP 拨号计划。  <br/> |管理员  <br/> Exchange Server 管理员  <br/> |对于 Exchange 2010 或最新服务包，请参阅[查看或配置 UM 服务器的属性](https://go.microsoft.com/fwlink/p/?linkId=268682)。  <br/> 对于 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|配置使用 SIP 地址的邮箱。  <br/> |将 SIP 地址分配给将使用 Exchange UM 功能的企业语音用户的邮箱。  <br/> |Skype for Business 服务器管理员  <br/> Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新服务包，请参阅[修改启用 UM 的用户的 SIP 地址](https://go.microsoft.com/fwlink/p/?LinkId=268699)。  <br/> 对于 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|运行 exchucutil.ps1 脚本。  <br/> |在运行 Exchange UM 服务的服务器上，打开 Exchange 命令行管理程序并运行 exchucutil 脚本，该脚本执行以下操作： <br/> <br/> •授予 Skype for business 服务器权限以读取 Exchange UM Active Directory 域服务对象，特别是在上一任务中创建的 SIP 拨号计划。  <br/><br/> •为托管已启用企业语音的用户的每个 Skype for Business Server 企业版池或标准版服务器在 Active Directory 中创建统一消息 IP 网关对象。  <br/><br/> •为每个网关创建一个 Exchange UM 查寻组。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。  <br/> |Exchange 组织管理员  <br/> Exchange 收件人管理员  <br/> |[Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|配置 Skype for business 服务器拨号计划。  <br/> |如果要与 Exchange 2010 集成，请使用与 Exchange UM 拨号计划完全限定的域名（FQDN）匹配的名称创建新的企业语音拨号计划。  <br/> **注意：** 你将需要为每个 UM 拨号计划执行此操作。 <br/> 如果您要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/网站级或池级的企业语音拨号计划。  <br/> **注意：** 如果您与 Exchange 2010 SP1 集成，则 Skype for business Server 拨号计划和 Exchange UM SIP 拨号计划名称不需要匹配。 <br/> |RTCUniversalServerAdmins  <br/> |[在 Skype for Business 服务器中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|运行 Exchange UM 集成工具。  <br/> | 在 Skype for Business 服务器上，运行**ocsumutil**，它：  <br/>  创建订阅者访问和自动助理联系对象。 <br/>  验证是否存在具有与 Exchange UM 拨号计划 FQDN 匹配的名称的企业语音拨号计划。 如果你运行的是 Exchange 2010 SP1 或更高版本，则拨号计划名称不需要匹配，你可以忽略该工具关于此工具的警告。 <br/>  此工具的工作原理是扫描 Active Directory for Exchange UM 设置，并允许 Skype for Business Server 管理员查看、创建和编辑联系人对象。 <br/> |RTCUniversalServerAdmins*和*RTCUniversalUserAdmins <br/> **重要提示：** 若要成功运行 ocsumutil，用户必须属于这两个组。 <br/> **注意：** 若要创建联系人对象，运行 ocsumutil 的用户必须具有在其中存储新联系人对象的 Active Directory 组织单位（OU）的正确权限。 可以通过运行 **Grant-CsOUPermission** cmdlet 授予此权限。 有关详细信息，请参阅 Skype for Business 服务器管理外壳文档。 <br/> |[为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|如有必要，请执行其他企业语音配置步骤。  <br/> |如果尚未在服务器或用户上配置企业语音设置，请执行下列一项或多项操作：  <br/> •部署和配置  <br/> 公用电话交换网 (PSTN) 网关和中介服务器  <br/> •定义语音策略、PSTN 使用记录和出站呼叫路由。  <br/> •为用户启用企业语音。  <br/> •为特定用户配置拨号计划（可选）。  <br/> 可能需要其他配置步骤，具体取决于你启用的企业语音功能。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |请参阅以下各节中的主题：  <br/> •[在 Skype For business 中配置语音策略、PSTN 使用记录和语音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[在 Skype For Business 服务器中部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|为 Exchange UM 启用企业语音用户。  <br/> |在 Exchange UM 服务器上，确保已创建统一消息邮箱策略，并且每位用户都有唯一的分机号码分配，然后为用户启用统一消息。  <br/> |Exchange 收件人管理员  <br/> |对于 Exchange 2010 或最新服务包，请参阅[为用户启用统一消息](https://go.microsoft.com/fwlink/p/?LinkId=268701)。  <br/> 对于 Exchange 2013，请参阅[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
   




## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划 Exchange 统一消息集成](unified-messaging.md)
