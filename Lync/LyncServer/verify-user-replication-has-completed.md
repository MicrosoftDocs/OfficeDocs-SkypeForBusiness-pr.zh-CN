---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>确认用户复制已完成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-17_

运行**move-csuser** cmdlet 时, 你可能会遇到故障, 因为 Active Directory 域服务 (AD DS) 和 Lync Server 2013 数据库之间的用户信息不同步, 因为初始复制不完整。 成功完成 Lync Server 2013 用户复制器服务的初始同步所需的时间取决于托管在托管 Lync Server 2013 池的 Active Directory 林中托管的域控制器的数量。 Lync Server 2013 用户复制程序服务初始同步过程在 Lync Server 2013 前端服务器首次启动时出现。 之后, 同步将基于用户复制程序间隔。 在运行**move-csuser** cmdlet 之前, 请完成以下步骤以验证用户复制已完成。

<div>

## <a name="to-verify-user-replication-has-completed"></a>验证用户复制已完成

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  单击 "**开始**" 菜单, 然后单击 "**运行**"。

3.  输入**eventvwr.exe** , 然后单击 **"确定"**。

4.  在事件查看器中, 单击 "**应用程序和服务日志**" 以将其展开, 然后选择 "Lync Server"。

5.  在 "**操作**" 窗格中, 单击 "**筛选当前日志**"。

6.  从 "**事件源**" 列表中, 单击 "**用户复制**"。

7.  在** \<所有事件 id\> **中输入**30024** , 然后单击 **"确定"**。

8.  在 "筛选的事件" 列表的 "**常规**" 选项卡上, 查找指示 "用户复制已成功完成" 的条目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

