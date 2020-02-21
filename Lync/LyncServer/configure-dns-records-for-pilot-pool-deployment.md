---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89481d26c964d7b436e45f708e5fa9f4a6afc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

在部署 Lync Server 2013 试点池之前，必须为引导池更新 DNS 主机的条目。 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。

**配置 DNS 主机 A 记录**

1.  在域名系统 (DNS) 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。

2.  在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的域。

3.  单击“新建主机(A 或 AAAA)”****。

4.  单击 "**名称**"，键入 Lync Server 2013 池的主机名（假定该域名来自定义该记录的区域，并且无需输入为 A 记录的一部分）。

5.  单击 " **IP 地址**"，键入前端池的 ip 地址。

6.  单击“添加主机”****，然后单击“确定”****。

7.  完成后，单击“完成”****。

</div>

<span> </span>

</div>

</div>

</div>

