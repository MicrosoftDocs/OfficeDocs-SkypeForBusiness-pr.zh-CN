---
title: Lync Server 2013：为自动发现配置 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff6e72d13ddfb80369a0a522abc14a1de459536
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中配置用于自动发现的 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-12_

若要支持 Lync 客户端的自动发现，您需要创建以下域名系统（DNS）记录：

  - 支持从组织网络内部进行连接的 Lync 客户端的内部 DNS 记录

  - 支持从 Internet 连接的 Lync 客户端的外部或公共 DNS 记录

您必须为每个 SIP 域创建一条内部 DNS 记录和一条外部 DNS 记录。

DNS 记录可以是（主机）记录或 CNAME 记录，这取决于您使用其他主题备用名称（SAN）创建新证书的能力。 如果无法向 lyncdiscover. 请求和部署新的外部（公用）证书。\<域名\> SAN，请使用 HTTP/TCP 端口80的过程。 以下过程介绍如何创建内部和外部 DNS 记录。

<div>

## <a name="to-create-dns-cname-records"></a>创建 DNS CNAME 记录

1.  按如下方式登录 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供程序。

2.  打开 DNS 管理单元：依次单击“开始”****、“管理工具”**** 和“DNS”****。

3.  执行以下操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 Active Directory 域（例如，contoso.local）所对应的“正向查找区域”****。
        
        <div>
        

        > [!NOTE]  
        > 此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。

        
        </div>
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。

4.  验证主机 A 的控制器池是否存在记录，如下所示：
    
      - 对于内部 DNS 记录，您的控制器池的内部 Web 服务完全限定域名（FQDN）应存在主机 A 记录（例如，lyncwebdir01）。
    
      - 对于外部 DNS 记录，您的控制器池的外部 web 服务 FQDN 应存在主机 A 记录（例如，lyncwebextdir.contoso.com）。

5.  验证主机是否为您的前端池提供了记录，如下所示：
    
      - 对于内部 DNS 记录，前端池的内部 Web 服务 FQDN 应存在主机 A 记录（例如，lyncwebpool01）。
    
      - 对于外部 DNS 记录，前端池的外部 Web 服务 FQDN 应存在主机 A 记录（例如，lyncwebextpool01.contoso.com）。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。
    
    <div>
    

    > [!NOTE]  
    > 如果您创建的是外部 DNS 记录，则从第三步开始，已为 SIP 域展开“正向查找区域”<STRONG></STRONG>。

    
    </div>

7.  右键单击 SIP 域名，然后单击“新建别名(CNAME)”****。

8.  在“别名”**** 中，键入以下内容之一：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。

9.  在“目标主机的完全限定的域名(FQDN)”**** 中，执行以下操作之一：
    
      - 对于内部 DNS 记录，请键入或浏览到您的控制器池的内部 Web 服务 FQDN （例如，lyncwebdir01），然后单击 **"确定"**。
    
      - 对于外部 DNS 记录，请键入或浏览到您的控制器池的外部 Web 服务 FQDN （例如，lyncwebextdir.contoso.com），然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 如果不使用控制器，请对前端池使用内部和外部 Web 服务 FQDN，或者对于单个服务器，为前端服务器或 Standard Edition server 使用 FQDN。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 您必须在您在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>创建 DNS A 记录

1.  按如下方式登录 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供商或外部 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”****、“管理工具”**** 和“DNS”****。

3.  执行以下操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 Active Directory 域（例如，contoso.local）所对应的“正向查找区域”****。
        
        <div>
        

        > [!NOTE]  
        > 此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。

        
        </div>
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。

4.  验证控制器池的主机 A （for IPv6，AAAA）记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，您的控制器池的内部 Web 服务 FQDN （例如，lyncwebdir01）应存在主机 A （for IPv6，AAAA）记录。
    
      - 对于外部 DNS 记录，应为控制器池的外部 Web 服务 FQDN （例如，lyncwebextdir.contoso.com）提供主机 A （for IPv6，AAAA）记录。

5.  验证您的前端池的主机 A （for IPv6，AAAA）记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，对于前端池的内部 Web 服务 FQDN （例如，lyncwebpool01）应存在主机 A （针对 IPv6、AAAA）记录。
    
      - 对于外部 DNS 记录，对于适用于前端池的外部 Web 服务 FQDN （例如，lyncwebextpool01.contoso.com），主机 A （针对 IPv6，AAAA）记录应存在。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。
    
    <div>
    

    > [!NOTE]  
    > 如果您创建的是外部 DNS 记录，则从第三步开始，已为 SIP 域展开“正向查找区域”<STRONG></STRONG>。

    
    </div>

7.  右键单击 SIP 域名，然后单击“新建主机(A 或 AAAA)”****。

8.  在“名称”**** 中，键入主机名，如下所示：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。
    
    <div>
    

    > [!NOTE]  
    > 假定域名来自在其中定义记录的区域，因此无需将域名作为 A 记录的一部分输入。

    
    </div>

9.  在“IP 地址”**** 中，键入 IP 地址，如下所示：
    
      - 对于内部 DNS 记录，请键入 Director 的内部 Web 服务 IP 地址（或者，如果使用负载平衡器，请键入控制器负载平衡器的虚拟 IP （VIP））。
        
        <div>
        

        > [!NOTE]  
        > 如果不使用控制器，请键入前端服务器或 Standard Edition Server 的 IP 地址，或者，如果使用负载平衡器，请键入前端池负载平衡器的 VIP。

        
        </div>
    
      - 对于外部 DNS 记录，请键入反向代理的外部或公用 IP 地址。

10. 单击“添加主机”****，然后单击“确定”****。

11. 若要创建另一条 A 记录，请重复步骤 8 至 10。
    
    <div>
    

    > [!IMPORTANT]  
    > 必须在您在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建一个新的 lyncdiscover. 和 lyncdiscoverinternal. A 记录。

    
    </div>

12. 创建完 A 记录（对于 IPv6 为 AAAA）后，请单击“完成”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

