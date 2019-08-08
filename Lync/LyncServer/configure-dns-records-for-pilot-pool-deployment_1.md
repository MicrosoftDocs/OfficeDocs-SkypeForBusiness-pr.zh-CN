---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c9bc007eda604ce4894497db4a6ef334315d28
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-24_

在部署 Lync Server 2013 试验池之前, 必须为试验池更新 DNS 主机的条目。 若要成功完成此过程, 你应至少以域管理员组的成员或 DnsAdmins 组的成员的身份登录到服务器或域。

**配置 DNS 主机 A 记录**

1.  在 "域名系统 (DNS)" 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。

2.  在您的域的控制台树中, 展开 "**正向查找区域**", 然后右键单击将安装 Lync Server 2013 的域。

3.  单击 "**新建主机 (A 或 AAAA)**"。

4.  单击 "**名称**", 键入池的主机名 (从在其中定义记录的区域中假定为域名, 并且不需要将其输入为 A 记录的一部分)。

5.  单击 " **IP 地址**", 键入前端池的 ip 地址。

6.  单击 "**添加主机**", 然后单击 **"确定"**。

7.  完成后, 单击 "**完成**"。

</div>

<span> </span>

</div>

</div>

</div>

