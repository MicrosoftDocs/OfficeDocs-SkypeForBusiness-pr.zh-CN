---
title: Lync Server 2013：配置对允许的外部域的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中配置对允许的外部域的支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

如果您已为联盟伙伴配置支持, 则可以管理哪些特定域可以与您的组织联盟。 将一个或多个特定外部域配置为 "允许的联盟域"。 若要执行此操作, 请将每个域添加到允许的域列表中。 即使为你的组织启用了合作伙伴发现, 如果域是联盟伙伴, 并且可能需要与超过1000的用户通信, 或者可能需要每秒发送20个以上的消息, 请执行此操作。 如果你的组织未启用合作伙伴发现, 则只有你添加到 "允许的域" 列表中的外部域用户才可以与你的组织中的用户参与 IM 和会议。 如果你想要将联盟域的访问权限限制为运行联盟伙伴的访问边缘服务的特定服务器, 你可以为允许的域列表中的每个域指定运行 "访问边缘" 服务的服务器的域名。

<div>


> [!NOTE]  
> 此过程介绍如何为特定域配置支持, 但实现对联合用户的支持还要求你为组织启用联合用户支持, 以及配置和应用策略以控制哪些用户可以协作处理联盟用户。 有关为联盟用户启用支持的详细信息, 请参阅<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。 有关配置控制联盟的策略的详细信息, 请参阅<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联盟用户访问的策略</A>。



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>将外部域添加到允许的域列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**联盟域**"。

4.  在 "**联盟域**" 页面上, 单击 "**新建**", 然后单击 "**允许的域**"。

5.  在**新的联盟域**中, 执行下列操作:
    
      - 在 "**域名 (或 FQDN)**" 中, 键入联盟伙伴域的名称。
        
        <div>
        

        > [!NOTE]  
        > 此名称必须是唯一的, 并且不能作为运行 Access Edge 服务的此服务器的允许域存在。 名称长度不能超过256个字符。<BR>"联盟伙伴" 域名上的搜索执行后缀匹配。 例如, 如果您键入 " <STRONG>contoso.com</STRONG>", 搜索也将返回域<STRONG>it.contoso.com</STRONG>。<BR>联盟伙伴域不能同时被阻止和允许。 Lync Server 2013 阻止这种情况, 因此您不必同步您的列表。

        
        </div>
    
      - 如果要将此联盟域的访问权限限制为运行 Access Edge 服务的特定服务器的用户, 请在 "**访问边缘服务 (FQDN)**" 中, 键入运行 access Edge 服务的联盟域服务器的 FQDN。
    
      - 如果要提供其他信息, 请在 "**评论**" 中键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“**提交**”。

7.  对要允许的每个联盟伙伴域重复步骤4到步骤6。

若要启用联盟用户访问, 还必须启用组织中的联合用户访问支持。 有关详细信息, 请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外, 你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。 有关详细信息, 请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

