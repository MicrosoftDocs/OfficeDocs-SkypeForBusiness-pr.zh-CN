---
title: 为 Lync Online 域配置联盟支持
TOCTitle: 为 Lync Online 域配置联盟支持
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202166(v=OCS.15)
ms:contentKeyID: 49312155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Online 域配置联盟支持

 

_**上一次修改主题：** 2012-11-01_

与 Microsoft Lync Online 2010 客户联盟需要完成以下步骤：

  - 配置 Lync Online 2010 客户的域的支持（例如 contoso.onmicrosoft.com）。如本文档的[与 Lync 联机客户联盟的先决条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)一节中规定，您应该已经为您的组织启用联盟。启用联盟要求指定联盟的域用于控制访问的方法。如果将组织配置为使用发现，则可以选择将域添加到组织的允许列表。如果没有启用域发现，则必须将 Lync Online 客户的域名添加到允许的域列表。可以使用 Lync Server 控制面板或运行 **New-CSAllowedDomain** cmdlet 来添加域名。有关使用 Lync Server 控制面板的详细信息，其中包括启用域发现，请参阅操作文档中的[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。有关使用 **New-CSAllowedDomain** cmdlet 添加域的详细信息，请参阅操作文档中的 [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)。
    
    > [!NOTE]  
    > Lync Online 客户可以拥有多个域。如果想要与一个以上的域联盟，必须对要支持联盟的每个单独的域配置支持，Lync Online 客户的管理员必须为要联盟的每个域启用联盟。
    


  - 配置对想要联盟的 Lync Online 2010 客户域的托管服务提供商的支持。请使用本节中的步骤配置托管服务提供商支持。
    
    > [!NOTE]  
    > 只有与 Lync Online 客户的域联盟才需要该步骤，而与在联盟的合作伙伴位置本地部署的任何域联盟不需要该步骤。
    


## 要从前端服务器

1.  从前端服务器中，启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 **New-CsHostingProvider** cmdlet 以创建和配置托管服务提供商。例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    前一个示例将设置以下参数：
    
      - **Identity** 为您创建的托管服务提供商指定唯一的字符串值标识符。请注意，如果已使用该 Identity 对现有的提供商进行配置，该命令将无法运行。
    
      - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。该值不能修改。如果托管服务提供商更改了其代理服务器，则需要为该提供商删除并重新创建项目。
    
      - **VerificationLevel** 指定如何（或是否）验证邮件是从托管服务提供商发送，以确保这些邮件是从该提供商发送。
    
      - **Enabled** 指示是否已启用您的域和托管服务提供商之间的网络连接。只有将该值设置为 **True**，才能在这两个组织之间交换邮件。
    
      - **EnabledSharedAddressSpace** 指示托管服务提供商是否用于共享的 SIP 地址空间（拆分域）应用场景。
    
      - **HostsOCSUsers** 指示托管服务提供商是否用于托管 Lync Server 帐户。如果为 **False**，提供商将托管其他帐户类型，如 Microsoft Exchange 帐户。
    
      - **IsLocal** 指示托管服务提供商使用的代理服务器是否包含在您的 Lync Server 拓扑中。
    
    有关使用此 cmdlet 的详细信息，请参阅操作文档中的 [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)。

