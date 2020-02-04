---
title: Lync Server 2013：为 Lync Online 域配置联合身份验证支持
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
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>在 Lync Server 2013 中配置 Lync Online 域的联合身份验证支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

要与 Microsoft Lync Online 2010 客户进行联盟，您需要完成以下步骤：

  - 配置对 Lync Online 2010 客户的域的支持（例如，contoso.onmicrosoft.com）。 正如在本文档的 "Lync Server 2013" 部分中的 "[与 Lync Online 客户进行联盟](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)" 的先决条件中所指定，你应该已为你的组织启用联盟。 启用联盟需要指定用于控制联盟域的访问的方法。 如果将组织配置为使用发现，则将域添加到组织的允许列表是可选的。 如果未启用域发现，则必须将 Lync Online 客户的域名添加到 "允许的域" 列表。 你可以通过使用 Lync Server 控制面板或运行**CSAllowedDomain** cmdlet 来添加域名。 有关使用 Lync Server 控制面板（包括启用域发现）的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理您的组织的 SIP 联合提供商](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。 有关使用**CSAllowedDomain** cmdlet 添加域的详细信息，请参阅 "操作" 文档中的 "[新建-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) "。
    
    <div>
    

    > [!NOTE]  
    > Lync Online 客户可以有多个域。 如果你想要与多个域联盟，则必须为要对其支持联盟的每个单独域配置支持，并且 Lync Online 客户的管理员必须为要进行联盟的每个域启用联盟。

    
    </div>

  - 配置对要与其进行联盟的 Lync Online 2010 客户域的托管提供商的支持。 使用此部分中的过程配置对托管提供程序的支持。
    
    <div>
    

    > [!NOTE]  
    > 只有具有 Lync Online 客户的域的联盟才需要此步骤，而不是用于联盟伙伴位置上部署的任何域的联盟。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>为托管提供商配置支持

1.  从前端服务器，启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft lync server 2013**"，然后单击 " **Lync server Management Shell**"。

2.  运行**CsHostingProvider** cmdlet 以创建和配置托管提供程序。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述示例设置了以下参数：
    
      - **标识**为你创建的托管提供程序指定唯一的字符串值标识符。 请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。
    
      - **ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定域名 (FQDN)。 不能修改此值。 如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **VerificationLevel**指定如何验证从托管提供程序发送的消息（或 if）以确保它们是从该提供商处发送的。
    
      - **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 **True **，否则无法在这两个组织之间交换消息。
    
      - **EnabledSharedAddressSpace ** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers**指示托管提供程序是否用于托管 Lync Server 帐户。 如果设置为 **False **，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal**指示你的 Lync server 拓扑中是否包含托管提供程序使用的代理服务器。
    
    有关使用此 cmdlet 的详细信息，请参阅操作文档中的[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

