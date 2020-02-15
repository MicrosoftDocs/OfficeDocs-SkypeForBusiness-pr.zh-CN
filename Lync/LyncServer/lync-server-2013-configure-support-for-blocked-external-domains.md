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
ms.openlocfilehash: 2f34f620fe6f98053e40c5999bcde29d88b6371a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>在 Lync Server 2013 中配置对阻止的外部域的支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

如果您配置了对联盟伙伴的支持，则可通过与您的组织联盟来管理将阻止的域。 被阻止的域的列表将充当阻止名单（不允许使用的显式条目的列表）并将在联盟域发现中应用（如果您启用了此选项）。 有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联合合作伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。

阻止一个或多个外部域连接到您的组织。要执行此操作，请将相应的域添加到阻止域列表中。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>将外部域添加到阻止域列表中

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****。

4.  单击“联盟域”****，再单击“新建”****，然后单击“被阻止的域”****。

5.  在“新建联盟域”**** 中，执行下列操作：
    
      - 在“域名(或 FQDN)”**** 中，键入要阻止的联盟伙伴域的名称。
        
        <div>
        

        > [!NOTE]  
        > 该名称的长度不能超过 256 个字符。<BR>搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 <STRONG>contoso.com</STRONG>，搜索还将返回域 <STRONG>it.contoso.com</STRONG>。<BR>无法同时阻止和允许联盟合作伙伴域。 Lync Server 2013 阻止这种情况，因此您不必同步您的列表。

        
        </div>
    
      - （可选）在“注释”**** 中，键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“提交”****。

7.  对要阻止的每个联盟伙伴，重复步骤 4 至 6。

若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。 有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。 有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

