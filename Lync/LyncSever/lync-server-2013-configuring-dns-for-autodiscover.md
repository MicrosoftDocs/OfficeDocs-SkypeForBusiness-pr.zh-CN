---
title: 为自动发现配置 DNS
TOCTitle: 为自动发现配置 DNS
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945656(v=OCS.15)
ms:contentKeyID: 52061169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为自动发现配置 DNS

 

_**上一次修改主题：** 2012-12-12_

若要对 Lync 客户端支持自动发现，您需要创建以下域名系统 (DNS) 记录：

  - 支持从您的组织网络中进行连接的 Lync 客户端的内部 DNS 记录

  - 支持从 Internet 进行连接的 Lync 客户端的外部或公共 DNS 记录

您必须为每个 SIP 域创建一条内部 DNS 记录和一条外部 DNS 记录。

DNS 记录可以是 A（主机）记录，也可以是 CNAME 记录，取决于您能否创建采用其他使用者替代名称 (SAN) 的新证书。如果您无法请求和部署采用 lyncdiscover.\<域名\> SAN 的新外部（公共）证书，请使用采用 HTTP/TCP 端口 80 的过程。以下过程介绍如何创建内部和外部 DNS 记录。

## 创建 DNS CNAME 记录

1.  按如下方式登录 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供程序。

2.  打开 DNS 管理单元：依次单击“开始”、“管理工具”和“DNS”。

3.  执行以下操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 Active Directory 域（例如，contoso.local）所对应的“正向查找区域”。
        
        > [!NOTE]  
		> 此域是安装 Lync Server 2013控制器池和前端池的 Active Directory 域。
        
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。

4.  请验证对应于控制器池的主机 A 记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，控制器池的内部 Web 服务完全限定的域名 (FQDN)（例如，lyncwebdir01.contoso.local）应存在主机 A 记录。
    
      - 对于外部 DNS 记录，控制器池的外部 Web 服务 FQDN（例如，lyncwebextdir.contoso.com）应存在主机 A 记录。

5.  请验证对应于前端池的主机 A 记录是否存在，如下所示：
    
      - 对于内部 DNS 记录，前端池的内部 Web 服务 FQDN（例如，lyncwebpool01.contoso.local）应存在主机 A 记录。
    
      - 对于外部 DNS 记录，前端池的外部 Web 服务 FQDN（例如，lyncwebextpool01.contoso.com）应存在主机 A 记录。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。
    
    > [!NOTE]  
    > 如果您创建的是外部 DNS 记录，则从第三步开始，已为 SIP 域展开“正向查找区域”。
    


7.  右键单击 SIP 域名，然后单击“新建别名(CNAME)”。

8.  在“别名”中，键入以下内容之一：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。

9.  在“目标主机的完全限定的域名(FQDN)”中，执行以下操作之一：
    
      - 对于内部 DNS 记录，键入或浏览到控制器池的内部 Web 服务 FQDN（例如，lyncwebdir01.contoso.local），然后单击“确定”。
    
      - 对于外部 DNS 记录，键入或浏览到控制器池的外部 Web 服务 FQDN（例如，lyncwebextdir.contoso.com），然后单击“确定”。
    
    > [!NOTE]  
    > 如果您未使用控制器，则使用前端池的内部和外部 Web 服务 FQDN，或者，对于单台服务器，使用前端服务器或 Standard Edition Server 的 FQDN。
    
    
    > [!IMPORTANT]
    > 您必须在您的 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的自动发现 CNAME 记录。


## 创建 DNS A 记录

1.  按如下方式登录 DNS 服务器：
    
      - 若要创建内部 DNS 记录，请以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录网络中的 DNS 服务器。
    
      - 若要创建外部 DNS 记录，请连接到您的公共 DNS 提供程序或外部 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”、“管理工具”和“DNS”。

3.  执行以下操作之一：
    
      - 对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 Active Directory 域（例如，contoso.local）所对应的“正向查找区域”。
        
        > [!NOTE]  
		> 此域是安装 Lync Server 2013控制器池和前端池的 Active Directory 域。
        
    
      - 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。

4.  按以下方式验证控制器池是否存在主机 A 记录（对于 IPv6 为 AAAA）：
    
      - 对于内部 DNS 记录，控制器池的内部 Web 服务 FQDN（例如，lyncwebdir01.contoso.local）应存在主机 A 记录（对于 IPv6 为 AAAA）。
    
      - 对于外部 DNS 记录，控制器池的外部 Web 服务 FQDN（例如，lyncwebextdir.contoso.com）应存在主机 A 记录（对于 IPv6 为 AAAA）。

5.  按以下方式验证前端池是否存在主机 A 记录（对于 IPv6 为 AAAA）：
    
      - 对于内部 DNS 记录，前端池的内部 Web 服务 FQDN（例如，lyncwebpool01.contoso.local）应存在主机 A 记录（对于 IPv6 为 AAAA）。
    
      - 对于外部 DNS 记录，前端池的外部 Web 服务 FQDN（例如，lyncwebextpool01.contoso.com）应存在主机 A 记录（对于 IPv6 为 AAAA）。

6.  对于内部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。
    
    > [!NOTE]  
    > 如果您创建的是外部 DNS 记录，则从第三步开始，已为 SIP 域展开“正向查找区域”。
    


7.  右键单击 SIP 域名，然后单击“新建主机(A 或 AAAA)”。

8.  在“名称”中，键入主机名，如下所示：
    
      - 对于内部 DNS 记录，请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
      - 对于外部 DNS 记录，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。
    
    > [!NOTE]  
    > 假定域名来自在其中定义记录的区域，因此无需将域名作为 A 记录的一部分输入。
    


9.  在“IP 地址”中，键入 IP 地址，如下所示：
    
      - 对于内部 DNS 记录，键入控制器的内部 Web 服务 IP 地址（或者，如果您使用的是负载平衡器，则键入控制器负载平衡器的虚拟 IP (VIP)）。
        
        > [!NOTE]  
		> 如果您未使用控制器，请键入前端服务器或 Standard Edition Server 的 IP 地址，或者，如果您使用的是负载平衡器，则键入前端池负载平衡器的 VIP。
        
    
      - 对于外部 DNS 记录，请键入反向代理的外部或公用 IP 地址。

10. 单击“添加主机”，然后单击“确定”。

11. 若要创建另一条 A 记录，请重复步骤 8 至 10。
    
    > [!IMPORTANT]
    > 您必须在您的 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的 lyncdiscover 和 lyncdiscoverinternal A 记录。


12. 创建完 A 记录（对于 IPv6 为 AAAA）后，请单击“完成”。

