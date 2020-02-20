---
title: 配置边缘服务器以与托管 Exchange UM 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91002410e4079abf62a3931f4fbbb3f5dadb3acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>配置边缘服务器以与托管 Exchange UM 集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-01-23_

若要在托管 Exchange 统一消息（UM）上为您的 Lync Server 2013 用户提供语音邮件功能，必须在边缘服务器上执行以下配置任务：

  - 配置边缘服务器以进行联盟。

  - 将中央管理存储数据复制到边缘服务器并验证复制。

  - 在边缘服务器上创建承载服务提供商。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> 在执行这些步骤之前，您必须先为托管 Exchange 服务创建一条外部 DNS SRV 记录。 有关详细信息，请参阅<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">创建 DNS SRV 记录以与托管 EXCHANGE UM 集成</A>。



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>为联盟配置边缘服务器

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 Set-CsAccessEdgeConfiguration cmdlet 为联盟配置服务器。例如，运行：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    上述示例设置了以下参数：
    
      - **UseDnsSrvRouting** 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。
    
      - **AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。
    
      - **EnablePartnerDiscovery**指定 Lync Server 是否将使用 DNS 记录来尝试发现未在 Active Directory 允许的域列表中列出的合作伙伴域。 如果为 False，Lync Server 2013 将仅与在允许的域列表中找到的域联盟。 如果使用 DNS 服务路由，则需要此参数。 在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>将数据复制到边缘服务器并验证复制

  - 验证到边缘服务器的复制是否已完成。 有关过程，请参阅[在 Lync Server 2013 中验证内部服务器与边缘服务器之间的连接](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)。

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上创建承载服务提供商

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 **New-CsHostingProvider** cmdlet 配置承载服务提供商。 例如，运行：
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    上述示例设置了以下参数：
    
      - **Identity** 为正在创建的承载服务提供商指定唯一的字符串值标识符，在此示例中为 **Fabrikam.com**。请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。
    
      - **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 **True**，否则无法在这两个组织之间交换消息。
    
      - **EnabledSharedAddressSpace** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
        
        <div>
        

        > [!NOTE]
        > 在设置<CODE>EnableSharedAddressSpace</CODE>为 True 之前，请尝试在内部解析联合 SRV 记录。 如果无法在内部解析此记录，则需要创建记录，_sipfederationtls _tcp。&lt;域&gt;和 _sip _tls。&lt;内部&gt; DNS 中的域。 这些记录应指向边缘服务器的访问接口的外部 IP 地址。

        
        </div>
    
      - **HostsOCSUsers**指示是否使用托管提供程序来承载 Lync Server 2013 帐户。 如果设置为 **False**，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **ProxyFQDN** 为承载服务提供商使用的代理服务器指定完全限定域名 (FQDN)，在此示例中为 **proxyserver.fabrikam.com**。不能修改此值。如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **IsLocal**指示由托管提供程序使用的代理服务器是否包含在 Lync server 2013 拓扑中。
    
      - **VerficationLevel** 指示在宿主提供程序中发送和接收的邮件所允许的验证级别。 指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。 如果未指定此级别，则消息将会由于被视为不可验证而遭拒绝。

</div>

<div>

## <a name="see-also"></a>另请参阅


[导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[验证 Lync Server 2013 中的内部服务器与边缘服务器之间的连接](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

