---
title: Lync Server 2013：为 Lync 会议室系统管理 Web 门户配置你的环境
description: Lync Server 2013：为 Lync 会议室系统管理 Web 门户配置你的环境。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542198"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>为 Lync 会议室系统管理 Web 门户配置 Lync Server 2013 环境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-22_

若要使用 Lync 会议室系统 (LRS) 管理 Web 门户，您将需要安装或配置以下必备组件。

<div>


> [!IMPORTANT]  
> 如果服务器配置了 Kerberos 和 NTLM 身份验证，并且 LRS 在未加入域的计算机上运行，则 Kerberos 身份验证将失败，并且用户将不会在管理门户中看到 LRS 的状态。 若要解决此问题，请将服务器配置为使用 NTLM 身份验证或 NTLM 和 TLS DSK 身份验证 (没有 Kerberos) ，或将 LRS 计算机加入域。



</div>

1.  Install Lync Server 2013 累积更新： Lync Server 拓扑中的7月2013。
    
    若要获取更新或查看它所包含的内容，请参阅 [Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=323959)。

2.  创建启用了 SIP 的 Active Directory 用户。
    
    LRS 管理 Web 门户使用这些凭据来查询 Lync Server 中的信息。 建议的用户名为 LRSApp。

3.  创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。
    
    创建组作用域为 "全局" 和 "组类型" 作为 "安全" 的组。 添加到此组的启用 SIP 的用户将被授权查看聊天室列表并执行某些命令，如收集日志。

4.  创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。
    
    创建组作用域为 "全局" 和 "组类型" 的组作为安全性。添加到此组的启用 SIP 的用户已被授权使用所有管理门户功能。
    
     
    
    ![具有安全组角色的管理员组的列表](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全组角色的管理员组的列表")  
    
     

5.  将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。
    
    ![LRSSupportAdminGroup 属性 "成员" 页](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 属性 "成员" 页")  
    
     

6.  创建具有名称 LRSSupport 的启用 SIP 的 Active Directory 用户。 将此用户添加到 LRSSupportAdminGroup。
    
    ![LRSSupportAdminGroup 属性 "成员" 页](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 属性 "成员" 页")  
    
     

7.  安装 ASP.NET MVC 4 for Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 （可从 Microsoft 下载中心处获取） [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) 。

</div>

<span> </span>

</div>

</div>

</div>

