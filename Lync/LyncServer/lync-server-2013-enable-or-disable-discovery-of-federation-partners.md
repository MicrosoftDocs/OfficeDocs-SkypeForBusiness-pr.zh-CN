---
title: Lync Server 2013：启用或禁用联合合作伙伴的发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ea73efafb912ad5c1e6dfa6b61b74eb9c817403
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用联盟伙伴发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否支持自动发现联盟伙伴域。使用本主题中的过程更改此配置。

<div>


> [!NOTE]  
> 以下过程假定您已为组织启用联盟。 有关启用联合的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A>。



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>为组织启用或禁用自动发现联盟域

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“访问边缘配置”****。

4.  在“访问边缘配置”**** 页上，单击“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑访问边缘配置”**** 的“启用与联盟用户的通信”**** 下，选中或清除“启用伙伴域发现”**** 复选框以启用或禁用自动发现伙伴域。

6.  单击“提交”****。

若要使联合用户能够与 Lync Server 部署中的用户进行协作，您还必须至少配置一个外部访问策略以支持联合用户访问。 有关详细信息，请参阅部署文档或操作文档中的[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。 有关控制对特定联盟域的访问权限的详细信息，请参阅在 lync server [2013 中管理组织的 sip 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、[在 lync server 2013 中管理组织的 sip 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)和在操作文档中[管理 LYNC server 2013 中的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用联盟伙伴发现

可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理联合合作伙伴的发现。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>启用联合合作伙伴的发现

  - 要启用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 True ($True)。请注意，必须启用 DNS SRV 路由才能更改此属性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>禁用联合合作伙伴的发现

  - 要禁用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

