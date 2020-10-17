---
title: Lync Server 2013：数据收集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516569"
---
# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 中的数据收集

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

在 Microsoft Lync Server 2013 通信软件中，可以运行 Microsoft Lync Server 2013、规划工具，而无需将现有和建议的 IP 地址和边缘服务器完全限定的域名 (Fqdn) ，但这样做很难，而不会导致配置错误。 例如，如果一段时间内需要共存，则一个常见错误是为 Lync Server 2013 Edge 部署重用现有边缘部署中的 Fqdn。 通过将现有和建议的 IP 地址和 FQDN 记录到电子表格、表或其他虚拟表单中，可有助于防止在安装期间出现设置问题。

<div>


> [!WARNING]  
> 如果您使用的是规划工具的早期版本，则可能已使用该工具创建了拓扑，并导出了要在拓扑生成器中使用的拓扑文档以发布拓扑。 从规划工具中删除了导出拓扑的功能。 强烈建议使用早期版本的规划工具为 Lync Server 2013 创建拓扑文档，并将产生意外的结果。



</div>

因此，建议的方法是使用以下与您的边缘拓扑相对应的数据收集模板，以收集您需要在规划工具中输入的各种 FQDN 和 IP 地址。 通过记录当前和建议的配置，可在生产环境的适当上下文中输入值。 并且，您还必须思考应如何配置共存和功能，例如简单 URL、文件共享和负载平衡。

若要成功部署 Microsoft Lync Server 2013，您需要了解各个组件的交互和依赖项。 通过收集现有网络和服务器基础结构中的数据，并在这些部分中应用规划指南，可以将 Lync Server 2013 边缘服务器组件集成到您的基础结构中。

在 [Lync Server 2013 中选择拓扑](lync-server-2013-choosing-a-topology.md)时引入，有三个主要体系结构，有两种变体，共五种可能的部署方案。 这些方案中的某个方案将是数据收集的起点。 IP 地址、服务器名称和域名是与匹配的证书、防火墙和 DNS 关系图（详述完整的规划解决方案所需信息）一致的示例。 关系图的填充所需证书、DNS 和防火墙值，在跨团队交流中十分重要，证书颁发机构、防火墙配置和 DNS 的管理在跨团队交流中由规划部署的团队之外的团队进行管理。 此关系图提供有关可用于沟通跨团队协作的要求的所需组件的信息。

提供的图表专供通用，但允许用于所有相关数据的集合，这些数据是整个团队方案中通信要求所需的，其中网络、防火墙、证书创建和管理、服务器部署及服务器管理由不同的组进行处理。 在部署 Lync Server 时，有必要的网络、防火墙、端口和协议、证书和服务器配置的详细信息非常有用。

**边缘服务器和边缘池**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**反向代理**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**控制器或控制器池**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

