---
title: 将 Lync Server 计算机配置为参加 System Center Discovery
TOCTitle: 将 Lync Server 计算机配置为参加 System Center Discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204776(v=OCS.15)
ms:contentKeyID: 49312383
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 计算机配置为参加 System Center Discovery

 

_**上一次修改主题：** 2012-10-20_

若要确保新的 Lync Server 代理参与 System Center Operations Manager 的发现过程，您必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：

1.  在“管理”选项卡上，单击“代理托管”。

2.  右键单击计算机的名称，然后单击“属性”。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”，然后单击“确定”。

完成步骤 2 后，重新启动健康代理服务。（重新启动该服务将“强制”发现新计算机。如果您没有重新启动该服务，则 System Center Operations Manager 可能需要长达 4 小时的时间才能发现新计算机。）在重新启动该服务后，验证该计算机上的 Operations Manager 事件日志中是否记录了任何错误事件。

