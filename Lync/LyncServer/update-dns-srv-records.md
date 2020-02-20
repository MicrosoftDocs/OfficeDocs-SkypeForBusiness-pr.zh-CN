---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 894fac5341af8882db8ba4bb5fdbbc16b2a19dd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。

本主题介绍了如何在迁移到 Lync Server 2013 之后更新域名系统（DNS）记录。 在将所有用户移动到 Lync Server 2013 之后，但在取消旧版 Lync Server 2010 池或控制器之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。 此过程假定内部 DNS 具有 SIP 用户域的区域。

**配置 DNS SRV 记录**

1.  在 DNS 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。

2.  在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Lync Server 2013 的 SIP 域，然后导航到 " ** \_tcp** " 设置。

3.  在右侧窗格中，右键单击 " ** \_sipinternaltls** "，然后选择 "**属性**"。

4.  在**提供此服务的主机**中，将主机 FQDN 更新为指向 Lync Server 2013 池。

5.  单击“确定”。

**验证是否可以解析前端池或 Standard Edition Server 的 FQDN**

1.  登录到域中的一台客户端计算机。

2.  单击“开始”****，然后单击“运行”****。

3.  在“打开”**** 框中，键入 **cmd**，然后单击“确定”****。

4.  在命令提示符处，键入**nslookup** \<FQDN 的前端池\>或\<Standard Edition 服务器\>的 FQDN，然后按 enter。

5.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

</div>

<span> </span>

</div>

</div>

</div>

