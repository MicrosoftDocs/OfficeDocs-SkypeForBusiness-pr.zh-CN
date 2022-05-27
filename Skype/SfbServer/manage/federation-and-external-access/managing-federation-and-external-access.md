---
title: Lync Server 2013：管理联合身份验证和对Skype for Business Server的外部访问
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 启用和配置外部用户访问权限，以控制受支持的外部用户是否可以与内部Skype for Business Server用户协作。
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676214"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理联合身份验证和对 Skype for Business Server 的外部访问

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署 Edge Server 的详细信息，请参阅 [Skype for Business Server 中的部署 Edge Server](../../deploy/deploy-edge-server/deploy-edge-server.md)。

安装并配置Skype for Business Server的内部部署后，组织中的内部用户可以与其他在 Active Directory 域服务 (AD DS) 中拥有 SIP 帐户的其他内部用户进行协作。 协作可包括发送和接收即时消息以及更新当前状态和参与会议（也称为“会议”）。 启用和配置外部用户访问权限，以控制受支持的外部用户是否可以与内部Skype for Business Server用户协作。 外部用户可以包括部署的远程用户、联合用户 (包括公共即时消息 (IM) 服务提供商) 支持的用户，以及会议中的匿名参与者。

如果部署包括Skype for Business Server边缘服务器或边缘池，则可能的通信类型范围将大大扩展。 有许多选项可用于外部用户访问、与其他 SIP 联合域的成员通信以及 SIP 联合提供商。 设置 Edge Server 或 Edge 池后，启用外部用户访问类型并配置策略以控制外部访问。 在Skype for Business Server中，可以使用 Skype for Business Server 控制面板、Skype for Business Server [Management Shell](../management-shell.md) 或两者同时启用和配置外部用户访问和策略。

> [!IMPORTANT]
> 在为外部用户访问设计您的配置和策略时，您必须了解策略的优先级以及如何应用这些策略。 Skype for Business Server在一个策略级别应用的策略设置可以替代在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。

默认情况下，没有任何策略支持外部用户访问 (包括远程用户访问和联合用户访问) ，即使你已为组织启用了外部用户访问支持。 若要控制外部用户访问权限的使用，必须配置一个或多个策略。 在以下策略中，指定受支持的外部用户访问类型：

- **全局策略**：部署 Edge Server 时会创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问。 全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。 如果删除全局策略，则不要将其移除。 相反，将其重置为默认设置。

- **站点策略**：可以创建和配置一个或多个站点策略，以限制对特定网站的外部用户访问的支持。 站点策略中的配置将替代全局策略，但仅针对网站策略涵盖的特定站点。 默认情况下，网站策略将应用到该网站中的所有用户，但用户策略将覆盖站点策略设置。

- **用户策略**：可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问支持。 用户策略中的配置将替代全局策略和站点策略，但仅针对策略分配给的特定用户。 如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。

若要确定您需要创建或编辑哪些配置设置和哪些策略，请参阅以下决策点：

**是否要允许域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

按主题中所述配置设置 [，配置策略以控制远程用户加入](external-access-policies/configure-policies-to-control-remote-user-access.md)，并 [启用或禁用联合身份验证和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

**是否要允许匿名用户参加和受邀参加由您的部署中的用户主持的会议？**

按照主题中的详细信息配置设置 [，分配会议策略以支持匿名用户](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) 和 [创建会议策略](../conferencing/create-policies.md)。

**是否要允许用户与 SIP 联盟域联系人通信？**

按主题中所述配置设置 [，配置策略以控制联合用户访问](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [启用或禁用联合身份验证和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，以及 [管理组织的 SIP 联合域](sip-domains/manage-sip-federated-domains-for-your-organization.md)。

**如果已启用与 SIP 联合域的通信，是否启用 SIP 联合身份验证自动发现？**

按主题“ [启用或禁用联合合作伙伴的发现](access-edge/enable-or-disable-discovery-of-federation-partners.md)”中所述配置设置。

**如果您已允许与 SIP 联盟域进行通信，是否要允许向联盟联系人发送弃用声明，以通知他们您使用存档且可以对通信进行存档？**

根据主题“ [启用或禁用向联合合作伙伴发送存档免责声明](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)”中所述配置设置。

**是否允许用户与启用与公共提供商通信的 SIP 联合提供商通信？**

按照主题中所述配置设置 [，配置策略以控制公共用户访问权限](external-access-policies/configure-policies-to-control-public-user-access.md)、 [启用或禁用联合身份验证和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，以及 [创建或编辑公共 SIP 联合提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**是否允许用户与 SIP 联合提供商通信，这些提供商是托管Microsoft 365或Office 365和 Skype for Business Online 的托管提供商？**

按主题中所述配置设置 [，启用或禁用联合身份验证和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) ， [并创建或编辑托管的 SIP 联合提供程序](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**是否在拆分（也称为混合）域中配置您的部署？在该域中，某些用户的主服务器位于本地部署中，而其他用户的主服务器配置为位于联机环境中**

按照主题中所述配置设置 [，配置策略以控制联合用户访问权限](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [启用或禁用联合身份验证和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，以及 [创建或编辑托管的 SIP 联合提供程序](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

即使尚未为组织启用外部用户访问权限，也可以配置外部用户访问设置。 但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。 禁用外部用户访问权限或未配置外部用户访问策略以支持外部用户访问策略时，外部用户无法与用户通信。

边缘部署根据配置边缘支持的方式对外部用户的类型进行身份验证并控制访问。 此规则的例外情况是匿名用户，他们在创建会议并邀请参与者时，会通过会议 ID 和发送给匿名参与者的传递密钥进行身份验证。 若要控制通信，可以配置一个或多个策略来定义组织内部和外部的用户相互通信的方式。 策略和设置包括可创建和配置的默认全局策略、站点策略和用户策略。
