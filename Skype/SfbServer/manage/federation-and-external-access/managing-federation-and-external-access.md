---
title: Lync Server 2013：管理对 Skype for Business Server 的联盟和外部访问
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 启用和配置外部用户访问，以控制受支持的外部用户是否可以与内部 Skype for Business Server 用户进行协作。
ms.openlocfilehash: df8ca25dcaffb9ee563691eb327dc9ea6e9a229c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826602"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理对 Skype for Business Server 的联盟和外部访问

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅在 [Skype for Business Server 中部署边缘服务器](../../deploy/deploy-edge-server/deploy-edge-server.md)。

安装和配置 Skype for Business Server 的内部部署后，组织内部用户可以与在 Active Directory 域服务 (AD DS) 中拥有 SIP 帐户的其他内部用户进行协作。 协作可包括发送和接收即时消息以及更新当前状态和参与会议（也称为“会议”）。 启用和配置外部用户访问，以控制受支持的外部用户是否可以与内部 Skype for Business Server 用户进行协作。 外部用户可以包括部署的远程用户、联盟用户 (包括支持的公共即时消息 (IM) 服务提供商) 用户和匿名与会者。

如果您的部署包括安装 Skype for Business Server 边缘服务器或边缘池，则可能的通信类型的范围会通过大量外部用户访问选项（与其他 SIP 联盟域的成员和 SIP 联盟提供程序的通信）大大扩展。 设置边缘服务器或边缘池后，启用要提供的外部用户访问类型，并配置策略以控制外部访问。 在 Skype for Business Server 中，根据任务要求，使用 Skype for Business Server 控制面板和/或 [Skype for Business Server](../management-shell.md)命令行管理程序 启用和配置外部用户访问和策略。 



> [!IMPORTANT]  
> 在为外部用户访问设计您的配置和策略时，您必须了解策略的优先级以及如何应用这些策略。 在一个策略级别应用的 Skype for Business Server 策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。


默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，同时指定每个策略支持的外部用户访问类型。其中包括以下外部访问策略：

  - **全局策略**   部署边缘服务器时将创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 要支持全局级别的外部用户访问，请将全局策略配置为支持一种或多种外部用户访问选项。 全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。 如果删除全局策略，则不要将其移除。 相反，将其重置为默认设置。

  - **站点策略**   可以创建和配置一个或多个网站策略，以限制对外部用户访问特定网站的支持。 站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。 例如，如果在全局策略中启用远程用户访问，则可以指定禁用特定站点的远程用户访问的站点策略。 默认情况下，站点策略应用于该站点的所有用户，但可以将用户策略分配给用户以覆盖站点策略设置。

  - **用户策略**   可以创建和配置一个或多个用户策略，以限制对特定用户进行远程用户访问的支持。 用户策略中的配置将覆盖全局和站点策略，但仅适用于为其分配策略的特定用户。 例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。

若要确定您需要创建或编辑哪些配置设置和哪些策略，请参阅以下决策点：

**是否要允许域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

配置设置，如主题"配置策略以[控制远程](external-access-policies/configure-policies-to-control-remote-user-access.md)用户访问"，以及启用或[禁用联盟和公共 IM 连接。](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

**是否要允许匿名用户参加和受邀参加由您的部署中的用户主持的会议？**

配置主题"分配会议策略以支持匿名[](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)用户和[创建会议策略"中详述的设置](../conferencing/create-policies.md)。

**是否要允许用户与 SIP 联盟域联系人通信？**

配置设置，如主题["](external-access-policies/configure-policies-to-control-federated-user-access.md)配置策略以控制联盟用户访问、启用或[禁用](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)联盟和公共 IM 连接以及管理组织的 SIP 联盟域"[中详述。](sip-domains/manage-sip-federated-domains-for-your-organization.md)


**如果已启用与 SIP 联盟域的通信，是否要启用 SIP 联盟自动发现？**

配置设置，如主题["启用或禁用联盟伙伴发现"中详述。](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**如果您已允许与 SIP 联盟域进行通信，是否要允许向联盟联系人发送弃用声明，以通知他们您使用存档且可以对通信进行存档？**

配置主题"启用或禁用向联盟伙伴发送存档免责声明 ["中详述的设置](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

**是否要允许用户与 SIP 联盟提供商进行通信，以便与公共提供商进行通信？**

配置设置，如主题["](external-access-policies/configure-policies-to-control-public-user-access.md)配置策略以控制公共用户访问、启用或禁用联盟和公共[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)连接以及创建或编辑公共[SIP 联盟](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)提供程序"


**是否要允许用户与作为运行 Microsoft 365 或 Office 365 和 Skype for Business Online 的托管提供商的 SIP 联盟提供商进行通信？**

配置设置，如主题["启用](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)或禁用联盟和公共 IM 连接以及[创建或编辑托管 SIP 联盟提供程序"中详述。](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**是否在拆分（也称为混合）域中配置您的部署？在该域中，某些用户的主服务器位于本地部署中，而其他用户的主服务器配置为位于联机环境中**

配置设置，如主题 ["](external-access-policies/configure-policies-to-control-federated-user-access.md)配置策略以控制联盟用户访问、启用或禁用联盟和公共 [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)连接以及创建或编辑托管 SIP 联盟提供程序"中 [详述的设置](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。


即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。

边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。

