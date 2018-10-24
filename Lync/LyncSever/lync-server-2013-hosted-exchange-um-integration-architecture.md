---
title: Lync Server 2013：托管 Exchange UM 集成体系结构
TOCTitle: 托管 Exchange UM 集成体系结构
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398067(v=OCS.15)
ms:contentKeyID: 49311799
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管 Exchange UM 集成体系结构

 

_**上一次修改主题：** 2012-09-25_

Lync Server 2013 ExUM Routing 应用程序支持与本地 Exchange 统一消息 (UM) 部署、服务提供商托管的 Exchange UM 或两者的组合进行集成。下图显示了所有三种可能的情况。

**与一个本地 Exchange UM 部署和两个托管 Exchange 提供商的集成**

![内部 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "内部 Lync Server Exchange UM 部署")

支持以下模式：

  - **本地部署：** Lync Server 2013 和 Exchange UM 均部署在企业内部的本地服务器上。

  - **交叉部署 ：** Lync Server 2013 部署在企业内部的本地服务器上，Exchange UM 托管在联机服务提供商的设施上，如 Microsoft Exchange Online 数据中心。

  - **混合部署 ：** Lync Server 2013 部署中的某些用户邮箱驻留在企业内部的本地 Exchange 服务器上，另外一些则驻留在托管 Exchange 服务数据中心。
    
    > [!NOTE]  
    > 混合部署可以用作评估用户或将用户分阶段迁移至托管 Exchange UM 期间的过渡性解决方案，或者，如果选择在转移部分用户后将其他用户的 Exchange UM 服务保留在内部，则可以将混合部署用作永久性解决方案。
    


## 共享 SIP 地址空间

要将 Lync Server 2013 与本地 Exchange UM 部署集成，应授予 Lync Server 2013 读取 Exchange UM Active Directory 域服务对象的权限。但是，由于 Lync Server 2013 和 Exchange UM 安装在单独的林中，且它们之间不存在信任关系，因此不能使用此方法与托管 Exchange UM 集成。

要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置 *共享 SIP 地址空间* 。在此配置中， Lync Server 2013 和托管 Exchange UM 服务提供商可使用相同的 SIP 域地址空间。

> [!NOTE]  
> 共享 SIP 地址空间的使用类似于交叉 Lync Server 2013 环境中使用的方法，即，一些用户驻留在本地部署中，一些用户则驻留在托管部署中（如 Lync Online）。在它们之间对 SIP 域进行了拆分。将 Lync Server 2013 与托管 Exchange UM 集成时，应确保将 Exchange UM 服务提供商包括在共享 SIP 地址空间中。



要将共享 SIP 地址空间配置为与 Exchange UM 服务提供商集成，需要按下面所示配置边缘服务器：

1.  通过运行 **Set-CsAccessEdgeConfiguration** cmdlet 来设置以下参数，将边缘服务器配置为可加入联盟：
    
      - **UseDnsSrvRouting** 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。
    
      - **AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。
    
      - **EnablePartnerDiscovery** 指定 Lync Server 2013 是否将使用 DNS 记录来尝试发现未列在 Active Directory 允许域列表中的伙伴域。如果为 False，则 Lync Server 2013 将仅与允许域列表中的域联盟。如果使用 DNS 服务路由，则需要此参数。在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。

2.  将 中央管理存储复制到边缘服务器并验证复制。有关详细信息，请参阅部署文档中的 [导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

3.  通过运行 **New-CsHostingProvider** cmdlet 来设置以下参数，在边缘服务器上配置*托管提供者*：
    
      - **Identity** 为您要创建的托管提供者指定唯一的字符串值标识符，如**托管 Exchange UM**。
    
      - **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。必须设置为 **True** 。
    
      - **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。必须设置为 **True** 。
    
      - **HostsOCSUsers** 指示承载服务提供商是否用于承载 Lync Server 2013 帐户。必须设置为 **False** 。
    
      - **ProxyFQDN** 为承载服务提供商使用的代理服务器指定完全限定域名 (FQDN)，如 **proxyserver.fabrikam.com** 。有关此信息，请与承载服务提供商联系。不能修改此值。如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **IsLocal** 指示承载服务提供商使用的代理服务器是否包含在 Lync Server 2013 拓扑中。必须设置为 **False**。

