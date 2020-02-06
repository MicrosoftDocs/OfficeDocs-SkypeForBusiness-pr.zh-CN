---
title: 在 Skype for Business 中规划 Exchange 统一消息集成
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
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要：在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时，请查看本主题。
ms.openlocfilehash: 1ae6ad10f1e817b9ace0240c79d09251a23dd61c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815860"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>在 Skype for Business 中规划 Exchange 统一消息集成

**摘要：** 在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时，请查看此主题。

Skype for Business 服务器支持与 Exchange 统一消息（UM）集成，以将语音消息和电子邮件合并到单个消息传递基础结构中。 在 Exchange 中，Exchange 统一消息（UM）是你可以安装和配置的若干 Exchange 服务器角色之一。

在 Microsoft Exchange Server 2013 和2016中，Exchange UM 在 Exchange 邮箱服务器上作为服务运行。 对于 Skype for business 服务器企业语音部署，统一消息将语音消息和电子邮件合并到单个应用商店，用户可以从电话（Outlook Voice Access）或计算机访问该应用程序。 统一消息和 Skype for business 服务器协同工作，为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。

> [!NOTE]
> 将 Skype for business 2019 与 Exchange 2013 或 Exchange 2016 集成时，exchange UM 将在 Skype for business Server 2019 中保持可用。 由于 Exchange 2019 中的支持的更改，Exchange UM 集成已被取消重点，取而代之的是云语音邮件和云自动助理功能。  有关详细信息，请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)和[规划 Skype for Business 服务器和 Exchange Server 迁移](../../../sfbhybrid/hybrid/plan-um-migration.md)。


为了使这些功能在本地 Exchange UM 部署中受支持，必须运行下列操作之一：

- Microsoft Exchange Server 2010 或最新服务包（仅限 Skype for Business Server 2015）
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Skype for Business Server 2019 中不再提供 Exchange 统一消息，它使用电话系统录制语音邮件，然后将录制内容保留在用户的 Exchange 邮箱中。 有关详细信息，请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>集成统一消息和 Skype for business 服务器的功能

Skype for Business 服务器，企业语音使用 Exchange 统一消息（UM）基础结构提供呼叫应答、呼叫通知、语音访问（包括语音邮件）和自动助理服务。

- **呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。

    如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。

- **Outlook Voice Access**Outlook Voice Access 使企业语音用户不仅可以访问语音邮件，还可以访问 Exchange 收件箱，包括来自电话界面的电子邮件、日历和联系人。 订阅者访问号码由 Exchange UM 管理员分配。

- **自动助理**自动助理是一种 Exchange UM 功能，可用于配置外部用户可以拨打联系公司代表的电话号码。 尤其是，它提供一系列语音提示，帮助外部呼叫者导航菜单系统。 可用选项列表由 Exchange UM 管理员在 Exchange UM 服务器上配置。

- **传真服务**Exchange UM 包括传真功能，使用户能够接收其 Exchange 邮箱中的传入传真。 有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。

    > [!NOTE]
    > Exchange UM 服务器提供的传真服务在与 Microsoft Exchange Server 2010、exchange 2010 以及最新服务包、Exchange 2013 或 Exchange 2016 集成的 Skype for business 服务器部署中不可用。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Skype for Business Server 中的本地统一消息的组件和拓扑

### <a name="exchange-server-components"></a>Exchange Server 组件

若要向组织中的企业语音用户提供[集成的统一消息和 Skype for Business 服务器功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所述的 Exchange UM 功能和服务，必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器（托管用户邮箱），并为电子邮件和语音邮件提供单个存储位置。 Exchange UM 在 Exchange 邮箱和客户端访问服务器上作为服务运行。

有关 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅[部署本地 EXCHANGE um 以提供 Lync Server 2013 预览版语音邮件](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。

### <a name="supported-topologies"></a>支持的拓扑

你可以在同一林中或多个林中部署 Skype for Business Server 和 Exchange 统一消息（UM）。 如果部署跨越多个林，则必须针对每个 Exchange UM 林执行 Exchange 集成步骤。 此外，你必须将每个 Microsoft Exchange 林配置为信任 Skype for business Server 林和 Skype for business 服务器林以信任每个 Exchange UM 林。 除了此林信任之外，所有用户的 Exchange UM 设置必须在 Skype for Business Server 林中的用户对象上设置。

Skype for Business 服务器支持 Exchange UM 集成的以下拓扑：

- 单林

- 单域（即具有单个域的单林）。 Skype for business 服务器、Microsoft Exchange 和用户都位于同一个域中。

- 多域（即具有一个或多个子域的根域）。 Skype for business 服务器和 Microsoft Exchange 服务器从你创建用户的域中的不同域进行部署。 Exchange UM 服务器可以从其支持的 Skype for business 服务器池所在的不同域进行部署。

- 多林（即资源林）。 Skype for business 服务器部署在单个林中，然后用户跨多个目录林分布。 用户的 Exchange UM 属性必须复制到 Skype for business 服务器林。

    > [!NOTE]
    > 可在多个林中部署 Exchange。 每个 Exchange 组织可以向其用户提供 Exchange UM，或者 Exchange UM 可以部署在 Skype for business 服务器所在的同一林中。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>集成本地统一消息和 Skype for Business 服务器指南

以下是部署企业语音时要考虑的准则和最佳做法：

> [!IMPORTANT]
> Exchange 统一消息（UM）仅在你也使用 UCMA 4 时才支持 IPv6。

- 部署 Skype for business Server Standard Edition server 或前端池。

- 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。

- 在要为 Exchange UM 启用用户的每个 Exchange 统一消息（UM）林中部署 Exchange 邮箱服务器角色。 有关安装 Exchange server 角色的详细信息，请参阅 Microsoft Exchange Server 文档。

    > [!IMPORTANT]
    > 当安装 Exchange 统一消息（UM）时，它将配置为使用自签名证书。 自签名证书不支持 Skype for business 服务器和 Exchange UM 相互信任，这就是为什么需要从两个服务器信任的证书颁发机构请求单独的证书的原因。

- 如果 Skype for business 服务器和 Exchange UM 安装在不同的林中，请将每个 Exchange 林配置为信任 Skype for business 服务器林和 Skype for business Server 林以信任每个 Exchange 林。 此外，在 Skype for Business Server 林中的用户对象上设置用户的 Exchange UM 设置，通常通过使用脚本或跨林工具（如 "身份生命周期管理器（ILM）"）。

- 必要时，安装 Exchange 管理控制台以管理统一消息服务器。

- 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。

- 如果你使用早于 Microsoft Exchange Server 2010 Service Pack 1 （SP1）的 Exchange UM 的版本，请调整 Exchange UM SIP URI 拨号计划和企业语音拨号计划的名称。

### <a name="deploying-redundant-exchange-um-servers"></a>部署冗余 Exchange UM 服务器

> [!IMPORTANT]
> 我们建议你为你的组织配置的每个 Exchange UM SIP URI 拨号计划至少部署两台 Exchange UM 服务运行的服务器。 除了提供扩展容量之外，部署冗余服务还可提供高可用性。 在服务器出现故障时，可以将 Skype for Business 服务器配置为故障转移到另一台服务器。

以下示例配置提供 Exchange UM 恢复能力。

**示例 1：Exchange UM 恢复能力**

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。

> [!NOTE]
> 例如，你还应在每个 Exchange UM 服务器上分配以下证书之一：在 "主题备用名称" （SAN）中使用带有通配符的证书，或将 SAN 中四个 Exchange UM 服务器中每个服务器的完全限定的域名（FQDN）放入其中。

**示例 2：Exchange UM 恢复能力**

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。

有关如何在 Exchange 2013 上启用或禁用统一消息的详细信息，请参阅将[Exchange 2013 UM 与 Lync Server 集成](https://go.microsoft.com/fwlink/p/?LinkId=265372)。 所提供的信息同样适用于 Skype for Business 服务器。

有关如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息的详细信息，请参阅：

- [在 Exchange 2010 上启用统一消息](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [禁用 Exchange 2010 上的统一消息](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 2019 中不再显示 exchange 统一消息，如果您有 Exchange 2019，并且您需要同等的功能，则需要使用[计划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述的云语音邮件服务。


## <a name="see-also"></a>另请参阅

[集成本地统一消息与 Skype for Business 的部署过程概述](deployment-overview.md)
