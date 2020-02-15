---
title: Lync Server 2013：测试控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1da9d365b42e0d8c78de48ac9ffa9a96c51ebc9f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中测试控制器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

在此阶段，您配置了控制器或控制器池，但您的域名系统（DNS） SRV 条目仍通过使用 pool 或 Standard Edition 服务器来指示要登录的客户端。 在将 DNS 记录更改为使 Lync 2013 客户端通过使用控制器自动登录之前，请通过将客户端手动指向控制器来测试该客户端。

<div>

## <a name="to-test-the-deployment"></a>测试部署

1.  使用属于**CSAdministrator**组的域帐户登录到已安装 Lync Server 控制面板的计算机上。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在导航窗格中，单击 "**拓扑**"，然后在 "**状态**" 列中确认是否存在带有箭头的绿色服务器（即，![带有绿色箭头的服务器图标](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "带有绿色箭头的服务器图标")），用于您的控制器或控制器池。

4.  将安装了 Lync Server 2013 客户端的两台客户端计算机连接，并使用为 Lync Server 2013 启用的不同用户帐户登录到每台计算机。

5.  在其中一台客户端计算机上，单击 "**选项**" 菜单，选择 "**个人**设置" 组，单击 "**高级**"，单击 "**手动配置**"，然后将**内部服务器名称或 IP 地址**设置为新控制器或控制器池的完全限定域名（FQDN）。

6.  登录到这两个客户端，并验证使用控制器登录的客户端是否能够成功登录、查看其他用户的状态以及他们是否可以 exchange 即时消息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

