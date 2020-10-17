---
title: Lync Server 2013：为 Lync Online 域配置联合支持
description: Lync Server 2013：为 Lync Online 域配置联合支持。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553298"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>在 Lync Server 2013 中为 Lync Online 域配置联合支持

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

与 Microsoft Lync Online 2010 客户联盟要求您完成以下步骤：

  - 配置对 Lync Online 2010 客户 (的域的支持例如，contoso.onmicrosoft.com) 。 如本文档中的 " [与 Lync Online 2013 客户进行联盟的先决条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) " 一节中所述，您应该已为您的组织启用了联盟。 启用联盟要求指定联盟的域用于控制访问的方法。 如果将组织配置为使用发现，则可以选择将域添加到组织的允许列表。 如果未启用域发现，则必须将 Lync Online 客户的域名添加到允许的域列表中。 您可以通过使用 Lync Server 控制面板或运行 **CSAllowedDomain** cmdlet 来添加域名。 有关使用 Lync Server 控制面板（包括启用域发现）的详细信息，请参阅操作文档中的在 [Lync server 2013 中管理组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 。 有关使用 **CSAllowedDomain** cmdlet 添加域的详细信息，请参阅操作文档中的 [CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 。
    
    <div>
    

    > [!NOTE]  
    > Lync Online 客户可以有多个域。 如果要与多个域联盟，则必须为要支持联合的每个单独域配置支持，并且 Lync Online 客户必须为要进行联合的每个域启用联合。

    
    </div>

  - 配置对要与之联合的 Lync Online 2010 客户域的承载提供程序的支持。 请使用本节中的步骤配置托管服务提供商支持。
    
    <div>
    

    > [!NOTE]  
    > 此步骤仅适用于与 Lync Online 客户的域联盟，而不是用于与在联合合作伙伴的位置部署本地部署的任何域的联盟。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>要从前端服务器

1.  在前端服务器中，启动 Lync Server 命令行管理程序：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

2.  运行 **New-CsHostingProvider** cmdlet 以创建和配置托管服务提供商。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    前一个示例将设置以下参数：
    
      - **Identity** 为您创建的托管服务提供商指定唯一的字符串值标识符。请注意，如果已使用该 Identity 对现有的提供商进行配置，该命令将无法运行。
    
      - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。该值不能修改。如果托管服务提供商更改了其代理服务器，则需要为该提供商删除并重新创建项目。
    
      - **VerificationLevel** 指定如何（或是否）验证邮件是从托管服务提供商发送，以确保这些邮件是从该提供商发送。
    
      - **Enabled** 指示是否已启用您的域和托管服务提供商之间的网络连接。只有将该值设置为 **True**，才能在这两个组织之间交换邮件。
    
      - **EnabledSharedAddressSpace** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers** 指示承载提供程序是否用于承载 Lync Server 帐户。 如果设置为 **False**，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal** 指示承载提供程序使用的代理服务器是否包含在你的 Lync server 拓扑中。
    
    有关使用此 cmdlet 的详细信息，请参阅操作文档中的 [CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

