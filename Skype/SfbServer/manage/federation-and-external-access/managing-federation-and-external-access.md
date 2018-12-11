---
title: Lync Server 2013： 管理联合身份验证和外部访问 Skype 业务服务器
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 启用并配置外部用户访问控制是否支持外部用户可以与内部 Skype 业务 Server 用户进行协作。
ms.openlocfilehash: bc96f0d221071393b6c9ef7b7279159fdaa4468f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223120"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理联合身份验证和 Skype 业务服务器的外部访问

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅[Skype 业务服务器中部署边缘服务器](../../deploy/deploy-edge-server/deploy-edge-server.md)。

后安装和配置内部部署的 Skype 业务服务器，您的组织中的内部用户可以与其他内部用户拥有 Active Directory 域服务 (AD DS) 中的 SIP 帐户进行协作。 协作可以包括发送和接收即时消息和更新的状态和参加会议 （也称为"会议"）。 启用并配置外部用户访问控制是否支持外部用户可以与内部 Skype 业务 Server 用户进行协作。 外部用户可以包括您的部署、 （包括支持的公共即时消息 (IM) 服务提供商的用户数） 的联盟的用户和匿名参与者在会议中的远程用户。

如果您的部署包括 Business Server 边缘服务器或边缘池的 Skype 安装，可能的通信类型的范围是已大幅度扩展了大量的外部用户访问，与其他 SIP 联盟的成员的通信选项域和 SIP 联盟提供商。 设置边缘服务器或边缘池后, 您启用您想要提供的外部用户访问的类型，并配置策略以控制外部访问。 Skype 业务服务器，在启用和配置外部用户访问和使用业务 Server Control Panel Skype 的策略，和 / 或[Skype 的业务 Server Management Shell](../management-shell.md)中，基于任务要求。 



> [!IMPORTANT]  
> 在设计您的配置和外部用户访问策略时，您必须了解的策略和如何应用策略的优先级。 Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


默认情况下，没有策略配置为支持外部用户访问，包括远程用户访问，即使您已为您的组织已启用外部用户访问支持联盟用户访问。 若要控制外部用户访问的使用，必须配置一个或多个策略，指定类型的外部用户访问支持的每个策略。 这包括以下外部访问策略：

  - **全局策略**   部署边缘服务器时创建的全局策略。 默认情况下，没有外部用户访问选项被启用在全局策略。 若要支持外部用户访问，在全局级别，您可以配置全局策略以支持一个或多个类型的外部用户访问选项。 全局策略应用于组织中的所有用户，但网站策略和用户策略将覆盖全局策略。 如果您删除全局策略，则不要删除它。 相反，您其重置为默认设置。

  - **站点策略**   可以创建并配置一个或多个站点策略，以限制到特定站点的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如，如果您启用远程用户访问，在全局策略，您可能指定禁用特定站点的远程用户访问的站点策略。 默认情况下的站点策略应用于所有用户的网站，但可以将用户策略分配给用户将会覆盖站点策略设置。

  - **用户策略**   可以创建并配置一个或多个用户策略，以限制为特定用户的远程用户访问的支持。 在用户策略重写全局和站点策略，但仅限于为其分配的用户策略的特定用户的配置。 例如，如果您启用远程用户访问中的全局策略和站点策略，您可能指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果您创建的用户策略，您必须将它应用于一个或多个用户才能生效。

若要确定哪些配置设置和哪些策略，您需要创建或编辑，请参阅以下决策点：

**若要允许内部和外部用户的域能够使用即时消息、 Web 会议和音频/视频协作吗？**

按[配置策略以控制远程用户访问](external-access-policies/configure-policies-to-control-remote-user-access.md)和[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)的主题中所述配置设置。

**若要允许匿名用户参加和受邀参加由您部署中的用户承载的会议吗？**

按[分配会议策略以支持匿名用户](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)的主题并[创建会议策略](../conferencing/create-policies.md)中所述配置设置。

**是否要允许用户与 SIP 联盟域联系人通信？**

按[配置策略以控制联盟用户访问](external-access-policies/configure-policies-to-control-federated-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，和[管理 SIP 联盟域为您的组织](sip-domains/manage-sip-federated-domains-for-your-organization.md)的主题中所述配置设置。


**如果您已允许与 SIP 联盟域进行通信，是否要启用 SIP 联盟自动发现？**

[启用或禁用联盟伙伴的发现](access-edge/enable-or-disable-discovery-of-federation-partners.md)主题中所述配置设置。

**如果您已允许与 SIP 联盟域进行通信，是否要启用免责声明发送候审您使用存档和通信可能要存档的联盟联系人？**

按[启用或禁用发送存档免责声明向联盟伙伴中](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)的主题中所述配置设置。

**是否要允许用户与 SIP 联盟提供商启用与公共提供商进行通信？**

以下设置[配置策略以控制公共用户访问](external-access-policies/configure-policies-to-control-public-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，并[创建或编辑公共 SIP 联盟提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)的主题中详细介绍的配置


**是否要允许用户与 SIP 联盟提供程序的运行 Microsoft Office 365 和 Skype 业务联机宿主提供商进行通信？**

按[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)和[创建或编辑托管 SIP 联盟提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)的主题中所述配置设置。

**拆分 （也称为混合） 域，其中某些用户具有在内部部署中，其主服务器和其他用户的配置与 online 环境中的主服务器中配置您的部署？**

配置以下设置[配置策略以控制联盟的用户访问](external-access-policies/configure-policies-to-control-federated-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管 SIP 联盟提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)主题中所述。


您可以配置外部用户访问设置，包括您想要用于控制外部用户访问，即使您没有为组织启用外部用户访问的任何策略。 但是，策略和配置其他设置都生效仅当已为组织启用外部用户访问。 禁用外部用户访问，或没有外部用户访问策略配置为支持，外部用户无法与您的组织的用户进行通信。

边缘部署进行身份验证 （除了匿名用户，通过会议 ID 和密钥时创建的会议并邀请参与者发送给匿名参与者的身份验证） 的外部用户和控件的类型基于您如何配置边缘支持的访问。 豕通信，您可以配置一个或多个策略和配置设置，用于定义内部和外部部署的用户如何相互进行通信。 策略和设置包括外部用户访问，除了可创建和配置为启用一个或多个类型为特定站点或用户的外部用户访问的站点和用户策略的默认全局策略。

