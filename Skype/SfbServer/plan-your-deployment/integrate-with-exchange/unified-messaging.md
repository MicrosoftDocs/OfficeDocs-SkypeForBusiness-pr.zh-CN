---
title: 规划Exchange统一消息集成Skype for Business
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要：在计划将 2013 Skype for Business Server 2016 Exchange本主题。
ms.openlocfilehash: bc378579d9d01fe783baa96d5869b3d340588b42
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725671"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>规划Exchange统一消息集成Skype for Business

**摘要：** 在计划将 2013 Skype for Business Server 2016 Exchange本主题。

Skype for Business Server统一Exchange与统一 (UM) 集成，以将语音邮件和电子邮件合并到单个邮件基础结构中。 在 Exchange 中Exchange UM (um) 是您可以安装和配置的Exchange服务器角色之一。

在 Microsoft Exchange Server 2013 和 2016 中，Exchange UM 作为服务在 Exchange 服务器上运行。 对于Skype for Business Server 企业语音，统一消息将语音邮件和电子邮件合并到一个存储中，用户可以通过电话 (Outlook Voice Access) 访问该存储。 统一消息Skype for Business Server协同工作，为 Outlook 用户提供呼叫应答、Outlook Voice Access 和自动助理企业语音。

> [!NOTE]
> Exchange当您将 Skype for Business Server 2019 与 Skype for Business 2013 或 Exchange 2016 集成时，UM 在 Exchange 2019 中仍然可用。 由于 2019 年 Exchange 支持的变化，EXCHANGE UM 集成的重要性正在减少，以支持 云语音邮件 和云自动助理功能。  有关详细信息[，请参阅](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)规划 云语音邮件 服务和规划[Skype for Business Server 和 Exchange Server 迁移](../../../sfbhybrid/hybrid/plan-um-migration.md)。


若要在本地 UM 部署中支持这些功能Exchange，必须运行以下项之一：

- Microsoft Exchange Server 2010 (Skype for Business Server 2015 年最新 Service Pack) 
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016 年

> [!NOTE]
> Exchange以前已知的统一消息在 Skype for Business Server 2019 中不再可用，2019 使用 电话系统 录制语音邮件，然后将录制保留到用户的 Exchange 邮箱中。 有关详细信息[，请参阅云语音邮件](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)服务。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>集成统一消息和统一消息Skype for Business Server

Skype for Business Server，企业语音使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、呼叫通知、语音访问 (包括语音邮件) 和自动助理服务。

- **呼叫应答** 呼叫应答是代表呼叫未应答或忙碌的用户接收语音邮件。 这包括播放个人问候语、录制邮件以及提交要排队等待传递至用户邮箱（存储在 Exchange 服务器上）的邮件。

    如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。

- **Outlook Voice Access** Outlook Voice Access 使 企业语音 用户不仅能够访问语音邮件，还可以访问 Exchange 收件箱，包括电子邮件、日历和电话界面中的联系人。 订阅者访问号码由 UM 管理员Exchange分配。

- **自动助理** 自动助理是Exchange UM 功能，可用于配置外部用户可以拨打以联系公司代表的电话号码。 尤其是，它可以提供一系列语音提示来帮助外部呼叫者导航菜单系统。 可用选项列表由 UM 管理员在 Exchange UM 服务器上Exchange配置。

- **UM Exchange** 传真服务包括传真功能，使用户可以在传真邮箱中接收Exchange传真。 有关详细信息，请参阅统一[消息Microsoft Exchange Server](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80))文档。

    > [!NOTE]
    > Exchange UM 服务器提供的传真服务在与 Microsoft Exchange Server 2010、Exchange 2010 与最新的 Service Pack、Exchange 2013 或 Exchange 2016 集成的 Skype for Business Server 部署中不可用。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>内部部署统一消息的组件和Skype for Business Server

### <a name="exchange-server-components"></a>Exchange Server 组件

若要向贵组织的 企业语音 用户提供集成统一消息和[Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server)功能中所述的 Exchange UM 功能和服务，必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，以承载用户邮箱并为电子邮件和语音邮件提供单个存储位置。 ExchangeUM 作为服务在邮箱服务器Exchange客户端访问服务器上运行。

有关在 Exchange 2010 Microsoft Exchange Server UM 组件的详细信息，请参阅[Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) 。

### <a name="supported-topologies"></a>支持的拓扑

可以在同Skype for Business Server Exchange林 (UM) 部署统一消息和统一消息。 如果部署跨多个林，则必须对 UM 林Exchange执行Exchange集成步骤。 此外，您必须将每个 Microsoft Exchange林配置为信任 Skype for Business Server 林，将 Skype for Business Server 林配置为信任每个 Exchange UM 林。 除了此林信任之外，还必须Exchange林中的用户对象上设置所有用户的 UM Skype for Business Server设置。

Skype for Business Server UM 集成支持Exchange拓扑：

- 单林

- 单域（即具有单个域的单林）。 Skype for Business Server、Microsoft Exchange 和用户都驻留在同一域中。

- 多域（即具有一个或多个子域的根域）。 Skype for Business Server和 Microsoft Exchange 服务器部署在不同于创建用户的域的域中。 ExchangeUM 服务器可以部署在不同于其支持的池Skype for Business Server域中。

- 多林（即资源林）。 Skype for Business Server部署在单个林中，然后用户分布在多个林中。 用户Exchange UM 属性必须复制到Skype for Business Server林。

    > [!NOTE]
    > 可在多个林中部署 Exchange。 每个Exchange组织都可以Exchange UM，Exchange UM 可以部署在同一个林中Skype for Business Server。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>集成本地统一消息和统一消息Skype for Business Server

以下是在部署新部署时要考虑的指南和企业语音：

> [!IMPORTANT]
> Exchange统一消息 (UM) 仅在也使用 UCMA 4 时支持 IPv6。

- 部署Skype for Business Server Standard Edition服务器或前端池。

- 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。

- 在每个Exchange统一消息Exchange UM () 林中部署邮箱服务器角色，以便Exchange UM。 有关安装服务器Exchange的详细信息，请参阅Microsoft Exchange Server文档。

    > [!IMPORTANT]
    > 安装Exchange统一 (UM) 时，会配置为使用自签名证书。 自签名证书不会使 Skype for Business Server 和 Exchange UM 相互信任，这就是需要从两台服务器信任的证书颁发机构请求单独证书的原因。

- 如果Skype for Business Server Exchange UM，请配置每个 Exchange 林以信任 Skype for Business Server 林，将 Skype for Business Server 林配置为信任每个 Exchange 林。 此外，通常使用脚本或跨林工具（如 Identity Lifecycle Manager (ILM) ）在 Skype for Business Server 林中的用户对象上设置用户的 UM 设置。 Exchange

- 必要时，安装 Exchange 管理控制台以管理统一消息服务器。

- 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。

- 如果使用早于 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 的 Exchange UM 版本，则 Exchange UM SIP URI 拨号计划和 企业语音 拨号计划的坐标名称。

### <a name="deploying-redundant-exchange-um-servers"></a>部署冗余 Exchange UM 服务器

> [!IMPORTANT]
> 我们建议您为为组织配置的每个 Exchange UM 服务Exchange至少部署两台运行 UM 服务的服务器。 除了提供扩展容量之外，部署冗余服务器还提供高可用性。 如果服务器发生故障，可以将Skype for Business Server配置为故障转移到另一台服务器。

以下示例配置提供 Exchange UM 恢复能力。

**示例 1：Exchange UM 恢复能力**

![ExchangeUM 恢复能力图。](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。 如果 Tukwila 发生 Exchange UM 中断，则应该将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。 如果 Dublin 发生 UM Exchange，则服务器 3 和 4 的 DNS A 记录应分别配置为指向服务器 1 和服务器 2。

> [!NOTE]
> 对于示例 1，还应在每个 Exchange UM 服务器上分配以下证书之一：使用主题备用名称 (SAN) 中带通配符的证书，或将四个 Exchange UM 服务器中每个服务器的完全限定域名 (FQDN) 放在 SAN 中。

**示例 2：Exchange UM 恢复能力**

![ExchangeUM 恢复能力图。](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。

若要详细了解如何在 Exchange 2013 上启用或禁用统一消息，请参阅将[Exchange 2013 UM](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help)与 Lync Server 集成。 提供的信息同样适用于Skype for Business Server。

若要详细了解如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息，请参阅：

- [在 2010 Exchange统一消息](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [在 Exchange 2010 上禁用统一消息](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange如果您拥有 Exchange 2019，并且希望获得等效功能，则需要使用 Plan[云语音邮件 service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述的 云语音邮件 服务，则 Exchange 2019 中不再提供统一消息。


## <a name="see-also"></a>另请参阅

[集成本地统一消息和统一消息的部署Skype for Business](deployment-overview.md)