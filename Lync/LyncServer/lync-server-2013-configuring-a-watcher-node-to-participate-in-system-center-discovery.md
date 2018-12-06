---
title: 将观察程序节点配置为参加 System Center Discovery
TOCTitle: 将观察程序节点配置为参加 System Center Discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204704(v=OCS.15)
ms:contentKeyID: 49312107
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将观察程序节点配置为参加 System Center Discovery

 

_**上一次修改主题：** 2012-10-22_

若要确保观察程序节点参与 System Center Operations Manager 的发现过程，必须在已安装 System Center Operations Manager 控制台的计算机上完成以下过程：

1.  在“管理”选项卡上，单击“代理托管”。

2.  右键单击观察程序节点计算机的名称，然后单击“属性”。在“属性”对话框的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”，然后单击“确定”。

在将观察程序节点配置为充当代理之后，重新启动观察程序节点计算机。在计算机重新启动后，确认该计算机上的 Operations Manager 事件日志中未记录任何错误事件。在计算机运行大约 15 分钟后，使用 Operations Manager 控制台验证 Lync Server 计算机是否列在“Lync”类别下。

