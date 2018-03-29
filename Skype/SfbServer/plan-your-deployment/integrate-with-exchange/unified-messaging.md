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
description: 摘要： 计划集成为 Exchange 2013 具有的业务服务器 2015 Skype 时仔细阅读本主题。
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>在 Skype for Business 中规划 Exchange 统一消息集成
 
**摘要：**计划为 Exchange 2013 具有的业务服务器 2015年集成 Skype 时仔细阅读本主题。
  
Skype 的业务服务器 2015年组合语音邮件和电子邮件消息到一个消息基础结构支持集成与 Exchange 统一消息 (UM)。 在 Exchange 中，Exchange 统一消息 (UM) 是的您可以安装和配置多个 Exchange 服务器角色之一。 
  
在 Microsoft Exchange Server 2013，UM Exchange 作为服务运行的 Exchange 邮箱服务器上。 对于业务服务器 2015年企业语音部署 Skype，语音邮件和电子邮件消息到一个用户可从电话 (Outlook Voice Access) 或计算机访问的单个存储区结合统一消息。 统一消息传送、 业务服务器 2015年的 Skype 协同工作以提供企业语音的用户的呼叫应答、 Outlook Voice Access 和自动助理服务。
  
有关 Microsoft Exchange Server 2013年的体系结构更改的详细信息，请参阅 Microsoft Exchange Server 2013年文档中的[语音体系结构更改](https://go.microsoft.com/fwlink/p/?LinkId=266730)。
  
对于内部部署 UM Exchange 部署中必须支持这些功能，您必须运行以下任一项：
  
- Microsoft Exchange Server 2010年上，或者新的服务包
    
- Microsoft Exchange Server 2013
    
-  Microsoft Exchange Server 2016
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a>集成统一消息和 Skype for Business Server 2015 的功能

Skype 的业务服务器 2015，企业语音使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、 电话通知、 语音访问 （包括语音邮件），并自动助理服务。
  
- **呼叫应答** 呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。
    
    如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。
    
- **Outlook Voice Access**Outlook Voice Access 使企业语音用户访问而不仅仅是语音邮件，但也的 Exchange 收件箱，包括电子邮件、 日历和联系人电话接口。 由 UM Exchange 管理员分配订阅者访问号码。
    
- **自动助理**自动助理是 UM 交换功能，可用于配置了电话号码，外部用户可以拨通公司代表。 特别是，它提供了一系列帮助外部呼叫者导航菜单系统的语音提示。 可用选项的列表由 UM Exchange 管理员配置 Exchange UM 服务器上。
    
- **传真服务**嗯交换包括使用户能够在其 Exchange 邮箱中接收传入传真的传真功能。 有关详细信息，请参阅 Microsoft Exchange Server 文档中的[统一消息](https://go.microsoft.com/fwlink/p/?linkId=135652)。
    
    > [!NOTE]
    > 由 Exchange UM 服务器提供传真服务在中不可用 Skype 与 Microsoft Exchange Server 2010年、 Exchange 2010 与最新的 service pack 或 Exchange 2013 集成的业务服务器部署。 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的本地统一消息的组件和拓扑

### <a name="exchange-server-components"></a>Exchange Server 组件

若要提供的 UM Exchange 功能和服务[功能的集成统一消息和 Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx)中所述到您组织中的企业语音用户，您必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器其中驻留用户邮箱，并提供电子邮件和语音邮件的单个存储位置。 嗯交换作为一种服务将运行 Exchange 邮箱服务器和客户端访问服务器。
  
有关 Exchange UM 在 Microsoft Exchange Server 2010年中的组件的详细信息，请参阅[部署内部 Exchange UM 提供 Lync 服务器 2013年预览语音邮件到](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)部署文档中。
  
### <a name="supported-topologies"></a>支持的拓扑

您可以为业务服务器 2015年和 Exchange 统一消息 (UM) 在同一个林中或多个目录林部署 Skype。 如果部署跨多个目录林，则必须为每个 UM Exchange 林执行交换集成步骤。 此外，您还必须配置每个 Microsoft Exchange 目录林信任业务服务器 2015年林 Skype 和 Skype 业务服务器 2015年林信任每个 UM Exchange 目录林。 除了此目录林信任，必须在中为业务服务器 2015年林 Skype 用户对象设置所有用户的 Exchange UM 设置。 
  
Skype 的业务服务器 2015 UM 交换集成支持下列拓扑：
  
- 单林
    
- 单域（即具有单个域的单林）。 Skype 业务服务器 2015年、 Microsoft Exchange 和全部位于同一个域中的用户。
    
- 多域（即具有一个或多个子域的根域）。 Skype 业务服务器 2015，和 Microsoft Exchange 服务器部署在不同的域，您可在其中创建用户的域中。 可以在不同的域，从它们所支持的业务服务器 2015年池 Skype 部署 Exchange UM 服务器。
    
- 多林（即资源林）。 Skype 的业务服务器 2015年部署单个目录林，然后用户分布在多个目录林。 交换 UM 的用户的属性必须通过复制到企业服务器 2015年林 Skype。
    
    > [!NOTE]
    > 可在多个林中部署 Exchange。 每个 Exchange 组织可以交换 UM 提供给它的用户，或 UM Exchange 可以部署在同一个林中 Skype 业务服务器 2015年个。 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a>集成本地统一消息与 Skype for Business Server 2015 的指南

以下是部署企业语音时要考虑的准则和最佳做法：
  
> [!IMPORTANT]
> Exchange 统一消息 (UM) 支持 IPv6，仅当您同时还使用 UCMA 4。 
  
- 部署业务服务器 2015年标准版服务器或前端池的 Skype。 有关安装的详细信息，请参阅部署文档中的[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md) 。
    
- 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。
    
- 将每个想要启用用户的 Exchange UM 的 Exchange 统一消息 (UM) 目录林中的 Exchange 邮箱服务器角色的部署。 有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013年文档。
    
    > [!IMPORTANT]
    > 安装 Exchange 统一消息 (UM) 后，它被配置为使用自签名的证书。 自签名的证书不支持 Skype 业务服务器 2015年和 UM 交换要相互信任，因此，有必要从两个服务器信任的证书颁发机构请求一个单独的证书。 
  
- 如果 Skype 业务服务器 2015年和 UM Exchange 安装在不同的目录林中，配置每个 Exchange 目录林信任业务服务器 2015年林 Skype 和 Skype 业务服务器 2015年林信任每个 Exchange 目录林。 此外，Exchange UM 的用户的设置中业务服务器 2015年林，Skype 的用户对象通常使用设置脚本或跨目录林的工具，如身份生命周期管理器 (ILM)。
    
- 必要时，安装 Exchange 管理控制台以管理统一消息服务器。
    
- 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。
    
- 如果您使用的 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 比早期版本的 Exchange UM，坐标交换 UM SIP 的 URI 名称拨号计划和企业语音拨号计划。 
    
### <a name="deploying-redundant-exchange-um-servers"></a>部署冗余 Exchange UM 服务器

> [!IMPORTANT]
> 我们建议您部署最少的两个服务器的 Exchange UM 服务运行您为您的组织配置每个 Exchange UM SIP 的 URI 拨号计划。 除了提供扩展容量之外，部署冗余服务还可提供高可用性。 发生服务器故障时，可以配置业务服务器 2015年的 Skype 为故障转移到另一台服务器。 
  
以下示例配置提供 Exchange UM 恢复能力。
  
**示例 1: Exchange UM 复原**

![Exchange UM 复原能力图](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。
  
> [!NOTE]
> 对于示例 1 中，您还应分配下列每个 UM Exchange 服务器上的证书之一： 使用者备用名称 (SAN) 中的通配符证书或四个 Exchange UM 服务器 SAN 中的每个放置的完全合格的域名称 (FQDN)。 
  
**示例 2: Exchange UM 复原**

![Exchange UM 复原能力图](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。
  
有关如何启用或禁用统一邮件在 Exchange 2013 的详细信息，请参阅[集成交换 2013 UM 使用 Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372)。 提供的信息同样适用于 Skype 业务服务器 2015年个。
  
有关如何启用或禁用 Microsoft Exchange Server 2010年上的统一消息的详细信息，请参阅：
  
- [启用统一邮件在 Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [禁用统一邮件在 Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a>另请参阅

#### 

[部署过程概述用于集成内部统一消息和 Skype 业务](deployment-overview.md)

