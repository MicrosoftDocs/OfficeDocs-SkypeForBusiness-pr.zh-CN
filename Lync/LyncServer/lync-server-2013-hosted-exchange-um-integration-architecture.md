---
title: Lync Server 2013：托管 Exchange UM 集成体系结构
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
ms.openlocfilehash: 49fbb815514d9a338412b638bdf373a285ebf6f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange UM 集成体系结构

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-25_

Lync Server 2013 ExUM 路由应用程序支持与本地 Exchange 统一消息（UM）部署的集成，Exchange UM 由服务提供商托管，或两者的组合。 下图显示了所有三种可能性。

**与本地 Exchange UM 部署和两个托管的 Exchange 提供商的集成**

![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

支持下列模式：

  - **本地部署：** Lync Server 2013 和 Exchange UM 均部署在企业内的本地服务器上。

  - **跨内部部署：** Lync Server 2013 部署在你的企业内的本地服务器上，Exchange UM 托管在一个联机服务提供商的设备（如 Microsoft Exchange Online 数据中心）中。

  - **混合部署：** 您的 Lync Server 2013 部署将某些用户邮箱驻留在企业内的本地 Exchange 服务器上，而某些邮箱托管在托管 Exchange 服务数据中心。
    
    <div>
    

    > [!NOTE]  
    > 混合部署可用作在评估和分阶段迁移用户到托管 Exchange UM 的过程中的过渡解决方案，或者，如果你选择在转移其他用户的 Exchange UM 服务后选择保留某些用户的 Exchange UM 服务，则可将其用作过渡解决方案。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共享 SIP 地址空间

若要将 Lync Server 2013 与本地 Exchange UM 部署集成，请将 Lync Server 2013 权限授予读取 Exchange UM Active Directory 域服务对象的权限。 但是，此方法不适用于与托管 Exchange UM 集成，因为 Lync Server 2013 和 Exchange UM 安装在单独的林中，它们之间没有信任关系。

若要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置*共享 SIP 地址空间*。 在此配置中，Lync Server 2013 和托管 Exchange UM 服务提供商可以使用相同的 SIP 域地址空间。

<div>


> [!NOTE]  
> 使用共享 SIP 地址空间类似于跨本地 Lync Server 2013 环境中使用的方法，其中某些用户托管在本地部署中，而有些用户托管在托管部署（如 Lync Online）中。 SIP 域被拆分。 将 Lync Server 2013 与托管 Exchange UM 集成时，请确保在共享 SIP 地址空间中包含 Exchange UM 服务提供商。



</div>

若要配置与 Exchange UM 服务提供商集成的共享 SIP 地址空间，你需要配置 Edge 服务器，如下所示：

1.  通过运行**CsAccessEdgeConfiguration** cmdlet 设置以下参数，为联盟配置边缘服务器：
    
      - **UseDnsSrvRouting ** 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。
    
      - **AllowFederatedUsers ** 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。
    
      - **EnablePartnerDiscovery**指定 Lync Server 2013 是否将使用 DNS 记录来尝试发现未在 Active Directory 允许的域列表中列出的合作伙伴域。 如果为 False，则 Lync Server 2013 将仅与在 "允许的域" 列表中找到的域联合。 如果使用 DNS 服务路由，则需要此参数。 在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。

2.  将中央管理存储复制到边缘服务器并验证复制。 有关详细信息，请参阅[导出 Lync Server 2013 拓扑并将其复制到外部媒体，以便](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)在部署文档中进行边缘安装。

3.  通过运行**CsHostingProvider** cmdlet 设置以下参数，在 Edge 服务器上配置*托管提供商*：
    
      - **标识**为你创建的托管提供程序指定唯一的字符串值标识符，例如，**托管 Exchange UM**。
    
      - **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须设置为**True**。
    
      - **EnabledSharedAddressSpace** 指示是否将在共享的 SIP 地址空间方案中使用托管提供程序。 必须设置为**True**。
    
      - **HostsOCSUsers**指示托管提供商是否用于托管 Lync Server 2013 帐户。 必须设置为**False**。
    
      - **ProxyFQDN**为托管提供商使用的代理服务器指定完全限定的域名（FQDN），例如， **proxyserver.fabrikam.com**。 请与托管提供商联系以获取此信息。 不能修改此值。 如果托管提供程序更改了其代理服务器，你将需要删除该提供程序的条目，然后重新创建它。
    
      - **IsLocal**指示你的 Lync server 2013 拓扑中是否包含托管提供程序使用的代理服务器。 必须设置为**False**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

