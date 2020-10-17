---
title: Lync Server 2013：配置新的受信任应用程序服务器
description: Lync Server 2013：配置新的受信任应用程序服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552118"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>在 Lync Server 2013 中配置新的受信任应用程序服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

受信任的应用程序是一种基于 Microsoft Lync Server 2013 信任的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。 有关 UCMA 应用程序的详细信息，请参阅中的 "统一通信托管 API 3.0 核心 SDK 文档" [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) 。

有关配置 Microsoft Outlook Web Access (OWA) 和 Lync Server 2013 的详细信息，请参阅 Microsoft Exchange Server 2013 文档中的 "配置 Outlook Web App 和 Lync Server 2010 集成"。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 还可以委派用于添加服务器角色的相应管理员权限。 有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md) 。 对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

<div>

## <a name="to-configure-a-trusted-application-server"></a>配置受信任的应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

3.  选择“从现有部署下载拓扑”****，然后单击“确定”****。

4.  在 " **将拓扑另存为** " 对话框中，单击要使用的拓扑生成器文件，然后单击 " **保存**"。

5.  在左窗格中，右键单击 " **受信任的应用程序服务器**"，然后单击 " **新建受信任的应用程序池**"。

6.  输入受信任应用程序池的“池 FQDN”****，选择该池是单服务器池还是多服务器池，然后单击“下一步”****。

7.  在 " **选择下一个跃点** " 页上的列表中，选择 "Lync Server 2013 前端池"。

8.  单击“完成”****。

9.  选择顶级节点 **Lync Server 2013**，然后从 " **操作** " 菜单中单击 " **发布拓扑**"。
    
    应成功创建 **受信任的应用程序池** ，并将其与正确的前端池关联。

</div>

</div>

<span> </span>

</div>

</div>

</div>

