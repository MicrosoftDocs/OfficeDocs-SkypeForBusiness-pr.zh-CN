---
title: Lync Server 2013：搜索 Lync Server 用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665d8bbb0f3409de62565c25dfdb494fd140d636
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>在 Lync Server 2013 中搜索 Lync Server 用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-14_

您可以使用搜索查询的结果为 Lync Server 2013 配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。

您可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。 以下过程介绍如何使用 Lync Server 控制面板搜索用户。

<div>


> [!NOTE]  
> 在包括中央林拓扑的环境中，按照用户的电子邮件地址搜索用户时，搜索结果可能不准确。 可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 <STRONG>Get-CSUser</STRONG> cmdlet。



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>搜索一个或多个用户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的全部或第一部分，然后单击“查找”****。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“搜索结果”**** 上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”****。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。
    
    3.  在“等于”**** 列表中，单击“等于”**** 或“不等于”****。
    
    4.  在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击“查找”****。

6.  搜索结果将显示在“搜索结果”**** 下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。

</div>

<div>

## <a name="see-also"></a>另请参阅


[查看有关为 Lync Server 2013 启用的用户帐户的信息](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[为 Lync Server 2013 启用和禁用用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

