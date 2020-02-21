---
title: Lync Server 2013：安装 Lync 会议室系统管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b475911da0e0508fecb53de533f75e9feb10155
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>在 Lync Server 2013 中安装 Lync 会议室系统管理 Web 门户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-04-09_

您可以从 Microsoft 下载中心下载 Microsoft Lync 会议室系统管理 Web 门户[https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044)。

若要安装 Lync 会议室系统管理 Web 门户，请执行以下步骤。

1.  在 Lync Server 命令行管理程序中运行以下 cmdlet，以配置受信任的应用程序端口：
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  若要安装会议室门户，请下载**LyncRoomAdminPortal** ，然后以管理员身份运行它。

3.  从以下位置打开 web.config 文件：
    
    % Program Files%\\Microsoft Lync Server 2013\\Web 组件\\会议室门户\\Int\\处理程序\\

4.  在 web.config 文件中，将 "PortalUserName" 更改为 "配置 Lync 会议室系统管理门户的必备组件" 一节中的步骤2中创建的用户名（步骤中推荐的名称为 "LRSApp"）：
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  由于 LRS 管理门户是一个受信任的应用程序，因此您无需在门户配置中提供密码。 如果此用户使用的是与本地注册器不同的注册器，则需要通过在 Web.config 文件中添加以下行来为其指定注册器：
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  如果使用的端口不是5061，则在 Web.config 文件中添加以下行：
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>验证 Lync 会议室系统管理 Web 门户的安装

若要验证 Lync 会议室系统管理 Web 门户的安装，请执行以下操作：


1.  在前端服务器上，浏览到以下 URL：
    
    https://\<fe-服务器\>/lrs
    
    您不应看到任何错误，如下图所示：
    
    ![Lync 会议室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 会议室系统管理门户登录屏幕")

2.  如果没有看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：
    
    https://\<fe-服务器\>/lrs
    
    若要访问该页面，你将需要添加 DNS 记录，如中的 "自动客户端登录所需的 DNS 记录" 中[https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

