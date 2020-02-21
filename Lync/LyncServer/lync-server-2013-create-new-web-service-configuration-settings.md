---
title: Lync Server 2013：创建新的 Web 服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fda1955fec03a259b71454ee0b65dc8e835c5e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建新的 Web 服务配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

您可以使用 " **Web 服务**" 页来配置用于访问 Lync Server 2013 相关 web 服务器和 web 服务的身份验证方法。

按照以下步骤创建新的 Web 服务策略。

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>创建新的 web 服务配置设置

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“安全性”****，然后单击“Web 服务”****。

4.  在“Web 服务”**** 页上，单击“新建”****，然后执行下列操作之一：
    
      - 要配置站点的 Web 服务，请单击“站点配置”****。在“选择站点”**** 中，单击将应用此 Web 服务策略的站点，然后单击“确定”****。
    
      - 要配置池的 Web 服务，请单击“池配置”****。在“选择服务”**** 中，单击将应用此 Web 服务策略的服务，然后单击“确定”****。

5.  在“新建 Web 服务设置”**** 的“集成的 Windows 身份验证”**** 中，选择“协商”****、“集成的 Windows 身份验证”**** 或“无”****。

6.  根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
      - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
      - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
      - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。

7.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

