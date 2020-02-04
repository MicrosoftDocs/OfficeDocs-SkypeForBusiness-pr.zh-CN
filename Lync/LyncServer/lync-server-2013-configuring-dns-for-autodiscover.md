---
title: Lync Server 2013：配置用于自动发现的 DNS
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
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中配置自动发现的 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-12-12_

若要支持 Lync 客户端的自动发现，你需要创建以下域名系统（DNS）记录：

  - 支持从组织的网络中连接的 Lync 客户端的内部 DNS 记录

  - 支持从 Internet 连接的 Lync 客户端的外部 DNS 记录或公共 DNS 记录

必须为每个 SIP 域创建一个内部 DNS 记录和一个外部 DNS 记录。

DNS 记录可以是（主机）记录或 CNAME 记录，具体取决于使用其他主题备用名称（SAN）创建新证书的能力。 如果无法使用 lyncdiscover 请求和部署新的外部（公共）证书。\<域名\> SAN，请使用 HTTP/TCP 端口80的过程。 以下过程介绍了如何创建内部和外部 DNS 记录。

<div>

## <a name="to-create-dns-cname-records"></a>创建 DNS CNAME 记录

1.  按如下方式登录到 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以域管理员组的成员或 DnsAdmins 组的成员身份登录到您的网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供商。

2.  打开 "DNS 管理" 管理单元：单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。

3.  请执行下列操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 Active Directory 域的 "**正向查找区域**" （例如，"contoso"）。
        
        <div>
        

        > [!NOTE]  
        > 此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。

        
        </div>
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 SIP 域的 "**正向查找区域**" （例如，contoso.com）。

4.  验证主机 A 是否存在针对你的控制器池的记录，如下所示：
    
      - 对于内部 DNS 记录，你的控制器池的内部 Web 服务完全限定的域名（FQDN）应存在主机 A 记录（例如，lyncwebdir01）。
    
      - 对于外部 DNS 记录，你的控制器池的外部 web 服务 FQDN 应存在主机 A 记录（例如，lyncwebextdir.contoso.com）。

5.  验证主机 A 是否存在用于你的前端池的记录，如下所示：
    
      - 对于内部 DNS 记录，你的前端池的内部 Web 服务 FQDN 应存在主机 A 记录（例如，lyncwebpool01）。
    
      - 对于外部 DNS 记录，你的前端池的外部 Web 服务 FQDN 应存在主机 A 记录（例如，lyncwebextpool01.contoso.com）。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 SIP 域的 "**正向查找区域**" （例如，contoso.com）。
    
    <div>
    

    > [!NOTE]  
    > 如果你要创建外部 DNS 记录，则已为你的 SIP 域在步骤3中展开了 "<STRONG>正向查找区域</STRONG>"。

    
    </div>

7.  右键单击 SIP 域名称，然后单击 "**新建别名（CNAME）**"。

8.  在 "**别名名称**" 中，键入下列内容之一：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。

9.  **对于目标主机的完全限定的域名（FQDN）**，请执行下列操作之一：
    
      - 对于内部 DNS 记录，请键入或浏览到你的控制器池的内部 Web 服务 FQDN （例如，lyncwebdir01），然后单击 **"确定"**。
    
      - 对于外部 DNS 记录，请键入或浏览到你的控制器池的外部 Web 服务 FQDN （例如，lyncwebextdir.contoso.com），然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 如果不使用 Director，请对前端池使用内部和外部 Web 服务 FQDN，或者对于单个服务器，使用前端服务器或标准版服务器的 FQDN。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 必须在 Lync Server 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>创建 DNS 记录

1.  按如下方式登录到 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以域管理员组的成员或 DnsAdmins 组的成员身份登录到您的网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供商或外部 DNS 服务器。

2.  打开 "DNS 管理" 管理单元：单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。

3.  请执行下列操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 Active Directory 域的 "**正向查找区域**" （例如，"contoso"）。
        
        <div>
        

        > [!NOTE]  
        > 此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。

        
        </div>
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 SIP 域的 "**正向查找区域**" （例如，contoso.com）。

4.  验证控制器池的主机 A （for IPv6、AAAA）记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，你的控制器池的内部 Web 服务 FQDN 应存在主机 A （for IPv6，AAAA）记录（例如，lyncwebdir01）。
    
      - 对于外部 DNS 记录，你的控制器池的外部 Web 服务 FQDN 应存在主机 A （for IPv6，AAAA）记录（例如，lyncwebextdir.contoso.com）。

5.  验证你的前端池的主机 A （适用于 IPv6、AAAA）记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，你的前端池（例如，lyncwebpool01）的内部 Web 服务 FQDN 应存在主机 A （for IPv6，AAAA）记录。
    
      - 对于外部 DNS 记录，你的前端池的外部 Web 服务 FQDN 应存在主机 A （for IPv6，AAAA）记录（例如，lyncwebextpool01.contoso.com）。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开您的 SIP 域的 "**正向查找区域**" （例如，contoso.com）。
    
    <div>
    

    > [!NOTE]  
    > 如果你要创建外部 DNS 记录，则已为你的 SIP 域在步骤3中展开了 "<STRONG>正向查找区域</STRONG>"。

    
    </div>

7.  右键单击 SIP 域名称，然后单击 "**新建主机（A 或 AAAA）**"。

8.  在 "**名称**" 中，键入主机名，如下所示：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。
    
    <div>
    

    > [!NOTE]  
    > 从定义记录的区域中假定域名，因此不需要将其作为 A 记录的一部分输入。

    
    </div>

9.  在 " **Ip 地址**" 中，键入 IP 地址，如下所示：
    
      - 对于内部 DNS 记录，请键入 Director 的内部 Web 服务 IP 地址（或者，如果使用负载平衡器，请键入控制器负载平衡器的虚拟 IP （VIP））。
        
        <div>
        

        > [!NOTE]  
        > 如果不使用 Director，请键入前端服务器或标准版服务器的 IP 地址，或者，如果使用负载平衡器，请键入前端池负载平衡器的 VIP。

        
        </div>
    
      - 对于外部 DNS 记录，请键入反向代理的外部或公共 IP 地址。

10. 单击 "**添加主机**"，然后单击 **"确定"**。

11. 若要创建另一条记录，请重复步骤8到步骤10。
    
    <div>
    

    > [!IMPORTANT]  
    > 必须在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的 lyncdiscover 和 lyncdiscoverinternal 记录。

    
    </div>

12. 完成创建（适用于 IPv6、AAAA）记录后，单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

