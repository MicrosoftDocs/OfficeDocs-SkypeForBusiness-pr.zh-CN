---
title: 'Lync Server 2013: 管理对 Skype for Business 服务器的联盟和外部访问'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 启用和配置外部用户访问以控制受支持的外部用户是否可以与内部 Skype for Business 服务器用户进行协作。
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280101"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理对 Skype for Business 服务器的联盟和外部访问

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息, 请参阅[在 Skype For Business 服务器中部署 Edge 服务器](../../deploy/deploy-edge-server/deploy-edge-server.md)。

在安装并配置 Skype for business Server 的内部部署之后, 你组织中的内部用户可以与在你的 Active Directory 域服务 (AD DS) 中具有 SIP 帐户的其他内部用户进行协作。 协作可以包括发送和接收即时消息, 以及更新状态和参与会议 (也称为 "会议")。 启用和配置外部用户访问以控制受支持的外部用户是否可以与内部 Skype for Business 服务器用户进行协作。 外部用户可以包括部署的远程用户、联盟用户 (包括公共即时消息 (IM) 服务提供商的支持用户) 和会议中的匿名参与者。

如果你的部署包括安装 Skype for Business 服务器 Edge 服务器或边缘池, 则可能的通信类型的范围很大程度上与外部用户访问的各种选项 (与其他 SIP 联合成员的通信) 很大程度的扩展。域和 SIP 联合提供商。 在设置边缘服务器或边缘池后, 启用要提供的外部用户访问类型, 并配置策略以控制外部访问。 在 Skype for Business Server 中, 你可以使用 Skype for Business Server 控制面板、 [skype for Business Server Management Shell](../management-shell.md)或这两者 (基于任务要求) 启用和配置外部用户访问和策略。 



> [!IMPORTANT]  
> 为外部用户访问设计配置和策略时, 必须了解策略的优先级以及策略的应用方式。 在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。 Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


默认情况下, 未将任何策略配置为支持外部用户访问, 包括远程用户访问权限、联合用户访问, 即使你已启用组织的外部用户访问支持。 若要控制外部用户访问的使用, 必须配置一个或多个策略, 指定每个策略支持的外部用户访问类型。 这包括以下外部访问策略:

  - **全局策略**   当你部署 Edge 服务器时, 将创建全局策略。 默认情况下, 全局策略中未启用任何外部用户访问选项。 若要在全局级别支持外部用户访问, 请将全局策略配置为支持一种或多种类型的外部用户访问选项。 全局策略适用于组织中的所有用户, 但网站策略和用户策略替代全局策略。 如果您删除全局策略, 则不会将其删除。 而是将其重置为默认设置。

  - **网站策略**   您可以创建和配置一个或多个网站策略, 以限制对特定网站的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如, 如果在全局策略中启用 "远程用户访问", 则可以指定一个网站策略, 该策略可禁用特定网站的远程用户访问。 默认情况下, 网站策略应用于该网站的所有用户, 但你可以将用户策略分配给用户以替代网站策略设置。

  - **用户策略**   您可以创建和配置一个或多个用户策略, 以限制对特定用户的远程用户访问的支持。 用户策略中的配置替代全局和网站策略, 但仅适用于为其分配用户策略的特定用户。 例如, 如果在全局策略和网站策略中启用远程用户访问, 则可以指定禁用远程用户访问的用户策略, 然后将该用户策略分配给特定用户。 如果创建用户策略, 则必须将其应用于一个或多个用户, 然后它才会生效。

若要确定要创建或编辑哪些配置设置以及需要哪些策略, 请参阅以下决策点:

**您是否希望允许您的域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

按照主题[配置策略控制远程用户](external-access-policies/configure-policies-to-control-remote-user-access.md)访问和[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)中的详细信息配置设置。

**你是否希望允许匿名用户出席并邀请你的部署中的用户托管的会议？**

详细配置本主题中的详细设置[将会议策略分配给支持匿名用户](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)和[创建会议策略](../conferencing/create-policies.md)。

**是否希望允许用户与 SIP 联盟域联系人通信？**

配置这些设置, 详细信息请[配置策略来控制联盟用户访问](external-access-policies/configure-policies-to-control-federated-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), 以及[管理组织的 SIP 联盟域](sip-domains/manage-sip-federated-domains-for-your-organization.md)。


**如果已启用与 SIP 联盟域的通信, 是否要启用 SIP 联合自动发现？**

按主题[启用或禁用联合合作伙伴的发现](access-edge/enable-or-disable-discovery-of-federation-partners.md)中的详细说明配置设置。

**如果你已启用与 SIP 联合域的通信, 你是否希望允许将免责声明发送给联盟联系人, 通知他们你使用存档, 并且该通信可能已存档？**

按主题中的详细信息配置设置, 以便[在中启用或禁用向联盟合作伙伴发送存档免责声明](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

**是否希望允许用户与支持与公共提供商通信的 SIP 联合提供商进行通信？**

按主题中的详细信息配置设置,[以控制公共用户访问](external-access-policies/configure-policies-to-control-public-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)以及[创建或编辑公共 SIP 联合提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**是否希望允许用户与运行 Microsoft Office 365 和 Skype for business Online 的托管提供商的 SIP 联合提供商通信？**

按主题中的详细信息配置设置:[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), 以及[创建或编辑托管 SIP 联合提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**你的部署是在拆分 (也称为混合) 域中配置的, 其中某些用户在内部部署中拥有主服务器, 而其他用户在联机环境中配置了主服务器？**

配置这些设置, 详细信息请[配置策略来控制联盟用户访问](external-access-policies/configure-policies-to-control-federated-user-access.md)、[启用或禁用联盟和公共 IM 连接](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), 以及[创建或编辑托管 SIP 联合提供商](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。


你可以配置外部用户访问设置, 包括你希望用于控制外部用户访问的任何策略, 即使你未启用组织的外部用户访问权限也是如此。 但是, 你配置的策略和其他设置仅在你为你的组织启用外部用户访问时才有效。 当外部用户访问被禁用或者没有配置任何外部用户访问策略来支持它时, 外部用户无法与组织用户通信。

边缘部署对外部用户的类型进行身份验证 (匿名用户除外, 这些用户是通过会议 ID 进行身份验证的, 而在创建会议和邀请参与者时发送给匿名参与者) 和控件的密钥基于配置 edge 支持的方式进行访问。 为了控制通信, 你可以配置一个或多个策略, 并配置定义你的部署内部和外部的用户之间如何相互通信的设置。 除了可创建和配置以启用特定网站或用户的一种或多种类型的外部用户访问的网站和用户策略之外, 策略和设置包括外部用户访问的默认全局策略。

