---
title: 确认用户复制已完成
TOCTitle: 确认用户复制已完成
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204680(v=OCS.15)
ms:contentKeyID: 49312046
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确认用户复制已完成

 

_**上一次修改主题：** 2012-09-17_

运行 **Move-CsUser** cmdlet 时，可能会由于 Active Directory 域服务 (AD DS) 和 Lync Server 2013 数据库之间的用户信息不同步而遇到错误，原因是初始复制未完成。成功完成 Lync Server 2013 用户复制程序服务的初始同步所需的时间取决于承载 Lync Server 2013 池的 Active Directory 林中承载的域控制器数量。 Lync Server 2013 用户复制程序服务初始同步过程在 Lync Server 2013 前端池首次启动时发生。此后，同步将基于用户复制程序间隔执行。在运行 **Move-CsUser** cmdlet 之前，请先完成下列步骤以确认用户复制已完成。

## 确认用户复制已完成

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  单击“开始”菜单，然后单击“运行”。

3.  输入 **eventvwr.exe** ，然后单击“确定”。

4.  在事件查看器中，单击“应用程序和服务日志”将其展开，然后选择“Lync Server”。

5.  在“操作”窗格中，单击“筛选当前日志”。

6.  在“事件来源”列表中，单击“LS 用户复制程序”。

7.  在“\<所有事件 ID\>”中，输入 **30024**，然后单击“确定”。

8.  在筛选的事件列表中的“常规”选项卡上，查找表明用户复制已成功完成的条目。

