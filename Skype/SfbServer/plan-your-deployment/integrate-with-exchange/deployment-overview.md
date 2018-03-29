---
title: 集成本地统一消息与 Skype for Business 的部署过程概述
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: 摘要： 计划集成为 Exchange 2013 具有的业务服务器 2015 Skype 时仔细阅读本主题。
ms.openlocfilehash: bf035712a635c8ed293ca65639d68c6cac8a5d9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>集成本地统一消息与 Skype for Business 的部署过程概述
 
**摘要：**计划为 Exchange 2013 具有的业务服务器 2015年集成 Skype 时仔细阅读本主题。
  
 如果您想要将 Exchange 统一消息 (UM) 与 Skype 集成的业务服务器 2015年，则必须执行本主题中列出的任务。 还要确保您查看[Exchange 统一消息业务的 Skype 集成计划](unified-messaging.md)中描述的规划和部署最佳做法。 本主题假定您按顺序排列的中介服务器具有的业务服务器 2015年为部署了 Skype，您启用了用户的 Skype 的业务服务器 2015，但您可能不具有执行所有部署和配置步骤以启用企业语音，所述[业务服务器 2015年的 Skype 在部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)的部署文档中。
  
## <a name="unified-messaging-integration-process"></a>统一消息集成过程

> [!IMPORTANT]
> 这一点至关重要，您与协调组织的 Exchange 管理员，以确认这些任务的每个您需要执行有助于确保成功、 顺利地集成。 
  
|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|部署下列各项之一：  <br/> • 邮箱  <br/> Microsoft Exchange Server 2010年上，或者新的服务包  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/> |如果您使用的 Microsoft Exchange Server 2013年，安装下列 Exchange Server 角色位于同一个林中或不同树林中为 Skype 业务服务器 2015年:  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果在不同的目录林中安装 Microsoft Exchange Server 2013年和 Exchange 统一消息 (UM)，配置每个 Exchange 目录林信任的业务服务器 2015年林 Skype。  <br/> 如果您使用的 Exchange 2010，安装下列 Exchange Server 角色位于同一个林中或不同树林中为 Skype 业务服务器 2015年:  <br/> • 统一消息  <br/> • 集线器传输  <br/> • 客户端访问  <br/> • 邮箱  <br/> 如果 Skype 业务服务器 2015年和 Exchange 统一消息 (UM) 安装在不同的目录林中，配置每个 Exchange 目录林信任的业务服务器 2015年林 Skype。  <br/> |企业管理员（如果这是组织中的第一个 Exchange Server）  <br/> - 或者 -  <br/> Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）  <br/> |请参阅适用于您的 Exchange Server 版本的文档：  <br/> Exchange Server 2010年或最新服务包部署 documentationExchange 服务器 2013年规划和 DeploymentExchange 服务器 2016年规划和部署|
|安装证书。  <br/> |下载并安装来自受信任的根证书颁发机构 (CA) 为每个 Exchange UM 服务器的证书。 证书是用于相互传输级别安全性 (MTLS) 之间的业务服务器 2015年运行 Exchange UM 和 Skype 的服务器所必需的。  <br/> |管理员  <br/> ||
|创建和配置新的 Exchange UM SIP 拨号计划。  <br/> |在 UM Exchange 服务器上，创建基于贵组织的特定部署需要 SIP 拨号计划。  <br/> |Exchange 组织管理员  <br/> |有关 Exchange 2010 最新服务包，请参阅[创建 UM 拨号计划](https://go.microsoft.com/fwlink/p/?linkId=268674)。  <br/> 交换 2013，请参见[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> [配置在 Microsoft Exchange 统一消息](http://technet.microsoft.com/library/07547968-c59b-4dde-ace4-9fd286933759.aspx) <br/> |
|配置的 Exchange UM SIP 拨号计划的安全设置。  <br/> |要加密企业语音流量，配置**SIP 安全**或**安全**交换 UM SIP 拨号计划上的安全设置。 这是特别重要的步骤，如果您已经部署或者计划部署 Lync 电话版设备在您的环境中。 对于 Lync 电话版设备具有 Exchange UM 集成的环境中工作，Lync 服务器的加密设置必须与 Exchange UM 拨号计划安全设置保持一致。 有关详细信息，请参考部署文档。  <br/> |Exchange 组织管理员  <br/> |对于 Exchange 2010 或最新的 Service Pack，另请参阅：  <br/> [配置 UM 拨号计划上的 VoIP 安全](https://go.microsoft.com/fwlink/p/?LinkId=268697)。  <br/> 交换 2013，请参见[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|添加到 Exchange UM SIP 统一消息服务器拨号计划。  <br/> |要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，将服务器添加到 Exchange UM SIP 拨号计划。  <br/> |管理员  <br/> Exchange Server 管理员  <br/> |有关 Exchange 2010 最新服务包，请参阅[查看或配置 UM 服务器的属性](https://go.microsoft.com/fwlink/p/?linkId=268682)。  <br/> 交换 2013，请参见[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|配置使用 SIP 地址的邮箱。  <br/> |企业语音将使用 UM 交换功能的用户的邮箱分配 SIP 地址。  <br/> |Skype 业务服务器 2015年管理员  <br/> Exchange 收件人管理员  <br/> |对于 Exchange 2010 或新的服务包，请参阅[修改 UM-Enabled 用户的 SIP 地址](https://go.microsoft.com/fwlink/p/?LinkId=268699)。  <br/> 交换 2013，请参见[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|运行 exchucutil.ps1 脚本。  <br/> |在服务器上运行 Exchange UM 服务，Exchange 管理外壳程序打开并运行 exchucutil.ps1 脚本，执行以下任务：  <br/> • 业务服务器 2015年权限读取 Exchange UM Active Directory 域服务对象，具体来说，SIP 的 Skype 拨号计划创建在前一项任务授权。  <br/> • 创建统一邮件 IP 网关对象在 Active Directory 中为每个 Skype 业务服务器 2015年企业版池或标准版服务器主机的用户启用了企业语音。  <br/> • 创建为每个网关交换 UM 查寻组。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。  <br/> |Exchange 组织管理员  <br/> Exchange 收件人管理员  <br/> |[配置上与 ExchUCUtil.ps1 Microsoft Exchange 统一消息](http://technet.microsoft.com/library/07547968-c59b-4dde-ace4-9fd286933759.aspx) <br/> |
|配置 Skype 业务服务器 2015年拨号计划。  <br/> |如果您正在使用 Exchange 2007 SP1 或最新的 service pack 或 Exchange 2010 集成，创建新的企业语音拨号计划名称相匹配的 Exchange UM 拨号计划完全合格的域名称 (FQDN)。  <br/> **注意：**您需要执行此操作为每个 UM 拨号计划。 <br/> 如果您正在集成与 Exchange 2010 SP1，请确保已配置适合全局/站点级别或池级企业语音拨号计划。  <br/> **注意：**如果您正在使用 Exchange 2010 SP1 集成，Lync Server 拨号计划吸交换 UM 拨号的计划名称不需要匹配。 <br/> |RTCUniversalServerAdmins  <br/> |[配置拨号计划和规范化规则](http://technet.microsoft.com/library/d4a4d803-f1a8-4ed9-907e-5f532a0f6c6b.aspx) <br/> |
|运行 Exchange UM 集成工具。  <br/> | 为业务服务器 2015 Skype，在运行**ocsumutil.exe**，其中：  <br/>  创建订阅者访问和自动助理联系对象。 <br/>  验证具有匹配的 Exchange UM 拨号计划 FQDN 名称企业语音拨号计划。 如果您运行的 Exchange 2010 SP1 或更高版本，拨号计划名称不需要匹配，并且您可以忽略关于此工具的警告。 <br/>  此工具的工作原理是扫描 Exchange UM 设置活动目录，并允许 Skype 业务服务器 2015年的管理员可以查看、 创建和编辑联系人对象。 <br/> |RTCUniversalServerAdmins*和*RTCUniversalUserAdmins <br/> **重要：**若要成功运行 ocsumutil.exe，该用户必须属于这两个组。 <br/> **注意：**要创建的联系人对象，运行 ocsumutil.exe 的用户必须具有新联系人对象的存储位置的 Active Directory 组织单位 (OU) 中的正确权限。 可以通过运行**授予 CsOUPermission** cmdlet 授予此权限。 有关详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。 <br/> |[使用 Microsoft Exchange Server 上的统一消息配置 Lync Server 工作](http://technet.microsoft.com/library/1098ae4d-f57f-44f3-804e-39889d9fc14e.aspx) <br/> |
|如果需要，执行其他企业语音配置步骤。  <br/> |如果尚未企业语音设置配置您的服务器或用户，请执行下列一项或多项操作：  <br/> • 部署和配置  <br/> 公用电话交换网 (PSTN) 网关和中介服务器  <br/> • 语音策略、 PSTN 使用记录和出站呼叫路由定义。  <br/> • 允许用户为企业语音。  <br/> • 或者，使用拨号计划配置特定用户。  <br/> 根据启用的企业语音功能可能需要使用其他配置步骤。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |请参阅以下各节中的主题：  <br/> •[配置语音策略、 PSTN 使用记录和业务 2015年的 Skype 语音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> •[部署在 Skype 业务服务器 2015年企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|启用针对 Exchange UM 企业语音用户。  <br/> |在 UM Exchange 服务器上，请确保已创建统一邮件邮箱策略并且每个用户都有唯一的扩展名分配的编号，然后启用统一消息的用户。  <br/> |Exchange 收件人管理员  <br/> |有关 Exchange 2010 最新服务包，请参阅[启用统一消息的用户](https://go.microsoft.com/fwlink/p/?LinkId=268701)。  <br/> 交换 2013，请参见[统一消息](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
   
## <a name="see-also"></a>另请参阅

#### 

[Exchange 统一消息业务的 Skype 集成计划](unified-messaging.md)

