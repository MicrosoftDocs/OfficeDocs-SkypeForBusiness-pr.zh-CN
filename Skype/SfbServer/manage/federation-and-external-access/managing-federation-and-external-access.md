---
title: Lync Server 2013：管理对 lync Server 2013 的联盟Skype for Business Server
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
description: 您可以启用和配置外部用户访问，以控制受支持的外部用户是否可以与内部用户Skype for Business Server协作。
ms.openlocfilehash: f783e0744443a7efb4f59c218789fb05241aa158eaa9fbf6de673a0cd959ff90
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336832"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理对联盟的联盟和外部Skype for Business Server

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅在 Skype for Business Server[中部署边缘服务器](../../deploy/deploy-edge-server/deploy-edge-server.md)。

安装和配置 Skype for Business Server 的内部部署后，您组织的内部用户可以与在 Active Directory 域服务 (AD DS) 中拥有 SIP 帐户的其他内部用户进行协作。 协作可包括发送和接收即时消息以及更新当前状态和参与会议（也称为“会议”）。 您可以启用和配置外部用户访问，以控制受支持的外部用户是否可以与内部用户Skype for Business Server协作。 外部用户可以包括部署的远程用户、联盟用户 (包括支持的公共即时消息 (IM) 服务提供商) 用户和匿名与会者。

如果您的部署包括安装 Skype for Business Server 边缘服务器或边缘池，则可能的通信类型的范围会通过多种外部用户访问、与其他 SIP 联盟域的成员和 SIP 联盟提供程序的通信选项大大扩展。 设置边缘服务器或边缘池后，您可以启用要提供的外部用户访问类型，并配置策略以控制外部访问。 在Skype for Business Server中，根据任务要求，使用 Skype for Business Server 控制面板和/或[Skype for Business Server 命令行](../management-shell.md)管理程序 启用和配置外部用户访问和策略。 



> [!IMPORTANT]  
> 在为外部用户访问设计您的配置和策略时，您必须了解策略的优先级以及如何应用这些策略。 Skype for Business Server一个策略级别应用的策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。


默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，同时指定每个策略支持的外部用户访问类型。其中包括以下外部访问策略：

  - **全局策略**   全局策略是在部署边缘服务器时创建的。默认情况下，不会在全局策略中启用任何外部用户访问选项。要在全局级别支持外部用户访问，请配置全局策略以支持一个或多个外部用户访问选项类型。全局策略适用于组织中的所有用户，但是站点策略和用户策略会覆盖全局策略。删除全局策略并不会将其实际移除，而只是将其重置为默认设置。

  - **站点策略**   可以创建并配置一个或多个站点策略以将对外部用户访问的支持限制为特定站点。站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。例如，即使在全局策略中启用远程用户访问，仍然可以指定站点策略为特定站点禁用远程用户访问。默认情况下，站点策略将应用于该站点的所有用户，但是可以为用户分配用户策略以覆盖站点策略设置。

  - **用户策略**   可以创建并配置一个或多个用户策略以将对远程用户访问的支持限制为特定用户。用户策略配置将覆盖全局策略和站点策略，但是仅限于分配了该用户策略的特定用户。例如，即使在全局策略和站点策略中启用了远程用户访问，仍然可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。如果创建用户策略，则必须将其应用于一个或多个用户，此后该策略才能生效。

若要确定您需要创建或编辑哪些配置设置和哪些策略，请参阅以下决策点：

**是否要允许域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

配置主题配置策略以控制远程用户访问 [和启用](external-access-policies/configure-policies-to-control-remote-user-access.md)或禁用联盟和公共 IM 连接 [中详述的设置](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

**是否要允许匿名用户参加和受邀参加由您的部署中的用户主持的会议？**

配置主题分配会议策略以支持匿名用户[](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)和[创建会议策略中详述的设置](../conferencing/create-policies.md)。

**是否要允许用户与 SIP 联盟域联系人通信？**

按配置策略以控制联盟用户访问、[](external-access-policies/configure-policies-to-control-federated-user-access.md)启用或禁用联盟和公共[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)连接以及管理[组织的 SIP 联盟](sip-domains/manage-sip-federated-domains-for-your-organization.md)域主题中详述的设置。


**如果已启用与 SIP 联盟域的通信，是否要启用 SIP 联盟自动发现？**

配置启用或禁用联盟 [伙伴发现主题中详述的设置](access-edge/enable-or-disable-discovery-of-federation-partners.md)。

**如果您已允许与 SIP 联盟域进行通信，是否要允许向联盟联系人发送弃用声明，以通知他们您使用存档且可以对通信进行存档？**

配置主题 Enable [or disable sending an Archiving disclaimer to federated partners in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)中详述的设置。

**是否要允许用户与启用与公共提供商通信的 SIP 联盟提供商进行通信？**

配置主题配置策略以控制公共用户访问[](external-access-policies/configure-policies-to-control-public-user-access.md)、启用或禁用联盟和公共[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)连接以及创建或编辑公共 SIP[联盟](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)提供程序中详述的设置


**是否要允许用户与 SIP 联盟提供程序进行通信，SIP 联盟提供程序是运行 Microsoft 365 或 Office 365 Skype for Business Online 的托管提供商？**

配置设置，如启用或禁用联盟和公共 [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 连接和创建或编辑托管 [SIP 联盟提供程序主题所详细介绍](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**是否在拆分（也称为混合）域中配置您的部署？在该域中，某些用户的主服务器位于本地部署中，而其他用户的主服务器配置为位于联机环境中**

配置主题配置策略以控制联盟用户访问[](external-access-policies/configure-policies-to-control-federated-user-access.md)、启用或禁用联盟和公共[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)连接以及创建或编辑托管[SIP 联盟](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)提供程序中详述的设置。


即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。

边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。

