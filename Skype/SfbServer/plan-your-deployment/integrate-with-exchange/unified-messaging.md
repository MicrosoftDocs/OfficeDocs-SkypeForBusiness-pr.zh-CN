---
title: 在 Skype for Business 中规划 Exchange 统一消息集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要： 查看 while planning to Exchange 2013 或 2016年业务服务器集成 Skype 本主题。
ms.openlocfilehash: f560df43ab6347890cc5a3b956d43ed37a55bdf3
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263898"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>在 Skype for Business 中规划 Exchange 统一消息集成

**摘要：** While planning to Exchange 2013 或 2016年业务服务器集成 Skype 查看以下主题。

Skype 业务服务器支持的组合语音消息传递和电子邮件到单个消息传递基础结构与 Exchange 统一消息 (UM) 集成。 在 Exchange 中，Exchange 统一消息 (UM) 是可安装和配置多个 Exchange 服务器角色之一。

在 Microsoft Exchange Server 2013 和 2016年，Exchange UM 作为服务运行在 Exchange 邮箱服务器上。 Skype 的业务 Server 企业语音部署，为语音消息传递和电子邮件消息到一个存储的用户可以从 (Outlook Voice Access) 的电话或计算机访问结合统一消息。 统一消息和企业服务器的 Skype 协同工作来向企业语音用户提供呼叫应答、 Outlook Voice Access 和自动助理服务。

> [!NOTE]
> Exchange UM 仍可在 Skype 的业务服务器 2019年与 Exchange 2013 或 Exchange 2016 集成 for Business 2019 Skype 时。 由于 Exchange 2019 中支持的变化，Exchange UM 集成正在注销 emphasised 支持云语音邮件和云自动助理功能。  有关详细信息，请参阅[规划云语音邮件服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)和[Plan for Business Server 和 Exchange Server 迁移的 Skype](../../../SfBServer2019/hybrid/plan-um-migration.md) 。


内部部署 Exchange UM 部署中支持这些功能，您必须运行下列选项之一：

- Microsoft Exchange Server 2010 或最新 service pack (Skype 的业务服务器 2015 仅)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (仅业务服务器 2019 Skype)

> [!NOTE]
> Exchange 统一消息为以前已知不再可用的业务服务器 2019，使用电话系统来记录中的语音邮件，然后用户的 Exchange 邮箱中保留录制的 Skype 中。 有关详细信息，请参阅[规划语音邮件云服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>集成的统一消息和 Skype 业务服务器的功能

对于业务 Server，企业语音的 Skype 使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、 呼叫通知、 语音访问 （包括语音邮件） 和自动助理服务。

- **呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。

    如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。

- **Outlook Voice Access**Outlook Voice Access 使企业语音用户访问而不仅仅是语音邮件，但还 Exchange 收件箱，其中包括电子邮件、 日历和联系人通过电话界面。 由 Exchange UM 管理员分配订阅者访问号码。

- **自动助理**自动助理是 Exchange UM 功能，可以用来配置的外部用户访问公司代表可拨打的电话号码。 具体而言，它提供了一系列语音提示来帮助外部呼叫者导航菜单系统。 可用选项的列表由 Exchange UM 管理员配置 Exchange UM 服务器上。

- **传真服务**Exchange UM 包括传真功能，它使用户能够在其 Exchange 邮箱中接收传入的传真。 有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。

    > [!NOTE]
    > 由 Exchange UM 服务器提供的传真服务不与 Microsoft Exchange Server 2010、 最新的 service pack 的 Exchange 2010、 Exchange 2013 或 Exchange 2016 集成的业务服务器部署 Skype 适用。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>在本地统一消息中的业务服务器 Skype 的组件和拓扑

### <a name="exchange-server-components"></a>Exchange Server 组件

若要提供的 Exchange UM 功能和服务[集成的统一消息和 Skype 业务服务器的功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所述向您的组织中的企业语音用户，必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，用于托管用户邮箱，并提供单一的存储位置的电子邮件和语音邮件。 Exchange UM 作为服务运行在 Exchange 邮箱和客户端访问服务器上。

有关 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅[部署内部部署 Exchange UM 提供 Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) 。

### <a name="supported-topologies"></a>支持的拓扑

您可以部署 Skype Business Server 和 Exchange 统一消息 (UM) 中同一个林或多个林。 如果部署跨越多个林，您必须为每个 Exchange UM 林执行 Exchange 集成步骤。 此外，您必须配置每个 Microsoft Exchange 林信任 Business Server 林 Skype 和 Skype Business Server 林信任 Exchange UM 的每个林。 除了该林信任，所有用户的 Exchange UM 设置必须设置中为 Business Server 林 Skype 的用户对象。

Skype 业务服务器支持 Exchange UM 集成的以下拓扑：

- 单林

- 单域（即具有单个域的单林）。 Skype 业务服务器、 Microsoft Exchange、 和都位于同一域的用户。

- 多域（即具有一个或多个子域的根域）。 从您在其中创建用户的域的不同域中部署 Business Server 和 Microsoft Exchange 服务器的 Skype。 可以从它们支持的业务服务器池的 Skype 的不同域中部署 Exchange UM 服务器。

- 多林（即资源林）。 Skype 业务服务器部署在单个林中，且用户然后分配跨多级林。 必须将用户的 Exchange UM 属性通过复制到 Business Server 林 Skype。

    > [!NOTE]
    > 可在多个林中部署 Exchange。 每个 Exchange 组织可以为其用户，Exchange UM 提供或 Exchange UM 可以部署在同一个林中 Skype 业务服务器。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>集成的指南在本地统一消息和 Skype 业务服务器

以下是部署企业语音时要考虑的准则和最佳做法：

> [!IMPORTANT]
> Exchange 统一消息 (UM) 支持 IPv6，仅当您也使用 UCMA 4。

- 部署 Skype 业务 Server Standard Edition server 或前端池。

- 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。

- 部署中每个要为用户启用 Exchange UM 的 Exchange 统一消息 (UM) 林的 Exchange 邮箱服务器角色。 有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013 文档。

    > [!IMPORTANT]
    > 安装 Exchange 统一消息 (UM) 时，它被配置为使用自签名的证书。 自签名的证书不启用 Skype 的业务 Server 和 Exchange UM 以相互信任，这是需要单独的证书请求从两台服务器信任的证书颁发机构的原因。

- 如果在不同的林中安装了 Business Server 和 Exchange UM 的 Skype，配置每个 Exchange 林信任 Business Server 林 Skype 和 Skype Business Server 林信任每个 Exchange 林。 此外，用户的 Exchange UM 上设置设置中为 Business Server 林 Skype 用户对象通常使用脚本或跨林工具，例如 Identity Lifecycle Manager (ILM)。

- 必要时，安装 Exchange 管理控制台以管理统一消息服务器。

- 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。

- 如果您使用 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 以前版本的 Exchange UM，坐标名称 Exchange UM SIP 的 URI 拨号计划和企业语音拨号计划。

### <a name="deploying-redundant-exchange-um-servers"></a>部署冗余 Exchange UM 服务器

> [!IMPORTANT]
> 我们建议您部署至少两台服务器的 Exchange UM 服务正在运行的每个为组织配置的 Exchange UM SIP 的 URI 拨号计划。 除了提供扩展容量之外，部署冗余服务还可提供高可用性。 发生服务器故障时，可以配置 Skype 业务服务器故障转移到另一台服务器。

以下示例配置提供 Exchange UM 恢复能力。

**示例 1：Exchange UM 恢复能力**

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。

> [!NOTE]
> 示例 1 中，您还应分配下列每台 Exchange UM 服务器上的证书之一： 用于在使用者替代名称 (SAN) 的通配符证书或每个四台 Exchange UM 服务器 SAN 中放置的完全限定的域名 (FQDN)。

**示例 2：Exchange UM 恢复能力**

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。

有关如何启用或禁用 Exchange 2013 上的统一消息的详细信息，请参阅[Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)。 提供的信息同样适用于 Skype 业务服务器。

有关如何启用或禁用 Microsoft Exchange Server 2010 统一消息的详细信息，请参阅：

- [启用 Exchange 2010 统一消息](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [禁用 Exchange 2010 统一消息](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 统一消息不再存在于在 Exchange 2019，如果您具有 Exchange 2019 并希望将需要使用云语音邮件服务[规划云语音邮件服务](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)中所述的等效功能。


## <a name="see-also"></a>另请参阅

[集成本地统一消息与 Skype for Business 的部署过程概述](deployment-overview.md)