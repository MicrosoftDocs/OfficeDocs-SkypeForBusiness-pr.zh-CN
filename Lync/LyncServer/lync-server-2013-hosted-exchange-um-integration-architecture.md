---
title: Lync Server 2013：托管 Exchange UM 集成体系结构
description: Lync Server 2013：托管 Exchange UM 集成体系结构。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552458"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange UM 集成体系结构

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-25_

Lync Server 2013 ExUM 路由应用程序支持与本地 Exchange 统一消息的集成 (UM) 部署，Exchange UM 由服务提供商托管，或二者的组合。 下图显示了所有这三种可能性。

**与一个本地 Exchange UM 部署和两个 Exchange 提供商托管的 Exchange UM 集成**

![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

支持以下模式：

  - **本地部署：** Lync Server 2013 和 Exchange UM 都部署在企业中的本地服务器上。

  - **跨界部署：** Lync Server 2013 部署在企业内的本地服务器上，Exchange UM 托管在联机服务提供商的设施中，如 Microsoft Exchange Online 数据中心。

  - **混合部署：** 你的 Lync Server 2013 部署将一些用户邮箱驻留在企业内的本地 Exchange 服务器上，而某些邮箱驻留在托管 Exchange 服务数据中心中。
    
    <div>
    

    > [!NOTE]  
    > 混合部署可以用作评估用户或将用户分阶段迁移至托管 Exchange UM 期间的过渡性解决方案，或者，如果选择在转移部分用户后将其他用户的 Exchange UM 服务保留在内部，则可以将混合部署用作永久性解决方案。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共享 SIP 地址空间

若要将 Lync Server 2013 与本地 Exchange UM 部署集成，请授予 Lync Server 2013 读取 Exchange UM Active Directory 域服务对象的权限。 但是，此方法不适用于与托管 Exchange UM 集成，因为 Lync Server 2013 和 Exchange UM 安装在单独的林中，它们之间没有任何信任关系。

若要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置 *共享 SIP 地址空间*。 在此配置中，同时对 Lync Server 2013 和托管 Exchange UM 服务提供商提供了相同的 SIP 域地址空间。

<div>


> [!NOTE]  
> 共享 SIP 地址空间的使用类似于跨界 Lync Server 2013 环境中使用的方法，其中某些用户驻留在本地部署中，一些用户驻留在托管部署 (如 Lync Online) 中。 在它们之间对 SIP 域进行了拆分。 将 Lync Server 2013 与托管 Exchange UM 集成时，请确保在共享 SIP 地址空间中包含 Exchange UM 服务提供程序。



</div>

要将共享 SIP 地址空间配置为与 Exchange UM 服务提供商集成，需要按下面所示配置边缘服务器：

1.  通过运行 **Set-CsAccessEdgeConfiguration** cmdlet 设置以下参数，为联盟配置边缘服务器：
    
      - **UseDnsSrvRouting** 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。
    
      - **AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。
    
      - **EnablePartnerDiscovery** 指定 Lync Server 2013 是否将使用 DNS 记录来尝试发现未在 Active Directory 允许的域列表中列出的合作伙伴域。 如果为 False，Lync Server 2013 将仅与在允许的域列表中找到的域联合。 如果使用 DNS 服务路由，则需要此参数。 在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。

2.  将中央管理存储复制到边缘服务器并验证复制。 有关详细信息，请参阅部署文档中的 [导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 。

3.  通过运行 **New-CsHostingProvider** cmdlet 设置以下参数，在边缘服务器上配置*托管服务提供商*：
    
      - **Identity** 为正在创建的托管服务提供商指定唯一的字符串值标识符，如 **Hosted Exchange UM**。
    
      - **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。必须设置为 **True**。
    
      - **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。必须设置为 **True**。
    
      - **HostsOCSUsers** 指示是否使用托管提供程序来承载 Lync Server 2013 帐户。 必须设置为 **False**。
    
      - **ProxyFQDN** 为承载服务提供商使用的代理服务器指定完全限定域名 (FQDN)，如 **proxyserver.fabrikam.com**。 有关此信息，请与承载服务提供商联系。 不能修改此值。 如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **IsLocal** 指示由托管提供程序使用的代理服务器是否包含在 Lync server 2013 拓扑中。 必须设置为 **False**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

