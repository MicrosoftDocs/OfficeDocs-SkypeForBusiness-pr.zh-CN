---
title: Lync Server 2013：配置对阻止的外部域的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中配置对阻止的外部域的支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

如果你已为联盟伙伴配置支持，你可以管理阻止哪些域与你的组织进行联盟。 被阻止域的列表将充当阻止列表（列出不允许的显式条目），并且将在联合域发现中应用（如果已启用此选项）。 有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联合合作伙伴的发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。

阻止一个或多个外部域连接到你的组织。 若要执行此操作，请将该域添加到阻止域的列表中。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>将外部域添加到阻止域的列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**外部用户访问**"。

4.  单击 "**联盟域**"，单击 "**新建**"，然后单击 "**阻止的域**"。

5.  在**新的联盟域**中，执行下列操作：
    
      - 在 "**域名（或 FQDN）**" 中，键入要阻止的联盟伙伴域的名称。
        
        <div>
        

        > [!NOTE]  
        > 名称长度不能超过256个字符。<BR>"联盟伙伴" 域名上的搜索执行后缀匹配。 例如，如果您键入 " <STRONG>contoso.com</STRONG>"，搜索也将返回域<STRONG>it.contoso.com</STRONG>。<BR>联盟伙伴域不能同时被阻止和允许。 Lync Server 2013 阻止这种情况，因此您不必同步您的列表。

        
        </div>
    
      - 可选在 "**批注**" 中，键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“**提交**”。

7.  对要阻止的每个联盟伙伴重复步骤4到步骤6。

若要启用联盟用户访问，还必须启用组织中的联合用户访问支持。 有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。 有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

