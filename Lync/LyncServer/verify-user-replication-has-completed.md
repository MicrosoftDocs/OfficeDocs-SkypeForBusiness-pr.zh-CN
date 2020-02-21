---
title: 验证用户复制已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96e8df3cb77e6b53596ae17e15fed6b05243a99a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>验证用户复制已完成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

在运行**get-csuser** cmdlet 时，您可能会遇到故障，因为 Active Directory 域服务（AD DS）和 Lync Server 2013 数据库之间的用户信息因初始复制不完整而不同步。 成功完成 Lync Server 2013 用户复制程序服务的初始同步所需的时间取决于托管在承载 Lync Server 2013 池的 Active Directory 林中的域控制器数。 在首次启动 Lync Server 2013 前端服务器时，会发生 Lync Server 2013 用户复制程序服务初始同步过程。 此后，同步将基于用户复制程序间隔执行。 在运行 **Move-CsUser** cmdlet 之前，请先完成下列步骤以确认用户复制已完成。

<div>

## <a name="to-verify-user-replication-has-completed"></a>确认用户复制已完成

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  单击“开始”**** 菜单，然后单击“运行”****。

3.  输入 **eventvwr.exe**，然后单击“确定”****。

4.  在事件查看器中，单击“应用程序和服务日志”**** 将其展开，然后选择“Lync Server”。

5.  在“操作”**** 窗格中，单击“筛选当前日志”****。

6.  在“事件来源”**** 列表中，单击“LS 用户复制程序”****。

7.  在** \<所有事件 id\> **中输入**30024** ，然后单击 **"确定"**。

8.  在筛选的事件列表中的“常规”**** 选项卡上，查找表明用户复制已成功完成的条目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

