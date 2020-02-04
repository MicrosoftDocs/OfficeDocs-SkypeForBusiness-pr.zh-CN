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
ms.openlocfilehash: e00093859a6e252c019183617b4548dfc00218a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-29_

若要成功完成此过程，你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。

本主题介绍了迁移到 Lync Server 2013 后如何更新域名系统（DNS）记录。 将所有用户移到 Lync Server 2013 之后，但在取消旧版 Lync Server 2010 池或控制器之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。 此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。

**配置 DNS SRV 记录**

1.  在 DNS 服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。

2.  在 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Lync Server 2013 的 SIP 域，然后导航到** \_tcp**设置。

3.  在右窗格中，右键单击 " ** \_sipinternaltls** "，然后选择 "**属性**"。

4.  在**提供此服务的主机**中，更新主机 FQDN 以指向 Lync Server 2013 池。

5.  单击“**确定**”。

**验证是否可以解析前端池或标准版服务器的 FQDN**

1.  登录到域中的客户端计算机。

2.  单击 **“开始”**，然后单击 **“运行”**。

3.  在 "**打开**" 框中，键入**cmd**，然后单击 **"确定"**。

4.  在命令提示符处，键入 " **nslookup** \<FQDN" （标准版\>服务器\<\>的前端池或 fqdn），然后按 ENTER。

5.  验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。

</div>

<span> </span>

</div>

</div>

</div>

