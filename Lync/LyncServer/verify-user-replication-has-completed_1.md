---
title: 确认用户复制已完成
TOCTitle: 确认用户复制已完成
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204712(v=OCS.15)
ms:contentKeyID: 49312146
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确认用户复制已完成

 

_**上一次修改主题：** 2012-09-28_

运行 **Move-CsLegacyUser** cmdlet 时，可能会由于 Active Directory 域服务 (AD DS) 和 Lync Server 2013 数据库之间的用户信息不同步而遇到错误，原因是初始复制未完成。成功完成 Lync Server 2013 用户复制程序服务的初始同步所需的时间取决于承载 Lync Server 2013 池的 Active Directory 林中承载的域控制器数量。 Lync Server 2013 用户复制程序服务初始同步过程在 Lync Server 2013 前端池首次启动时发生。此后，同步将基于用户复制程序间隔执行。在运行 **Move-CsLegacyUser** cmdlet 之前，请先完成下列步骤以确认用户复制已完成。

## 确认用户复制已完成

1.  从 Lync Server 2013 前端服务器上，单击“开始”菜单，然后单击“运行”。

2.  输入 **eventvwr.exe** ，然后单击“确定”。

3.  在事件查看器中，单击“应用程序和服务日志”将其展开，然后选择 Lync Server。

4.  在“操作”窗格中，单击“筛选当前日志”。

5.  在“事件来源”列表中，单击“LS 用户复制程序”。

6.  在“\<所有事件 ID\>”中，输入 **30024** ，然后单击“确定”。

7.  在筛选的事件列表中的“常规”选项卡上，查找表明用户复制已成功完成的条目。

