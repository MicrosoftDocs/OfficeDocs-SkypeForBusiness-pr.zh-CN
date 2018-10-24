---
title: 在 Lync Server 2013 中验证 Office Web Apps Server 的配置
TOCTitle: 验证 Office Web Apps Server 的配置
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205393(v=OCS.15)
ms:contentKeyID: 49314771
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证 Office Web Apps Server 的配置

 

_**上一次修改主题：** 2014-04-22_

在将 Office Web Apps Server 添加到拓扑并发布该拓扑后，您应该在 Lync Server 事件日志中看到两个新的事件日志事件。首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：

**已发现 Web 会议服务器 WAC，启用 PowerPoint 内容。**

例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：

**已成功发现 Web 会议服务器 WAC。**

**WAC 内部演示者页面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**WAC 内部与会者页面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**WAC 外部演示者页面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**WAC 内部与会者页面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

如果您看到 LS Data MCU 事件，事件 ID 为 41033，则意味着 Office Web Apps Server 发现已失败。在这种情况下，Microsoft Lync Server 2013 将尽量多次尝试发现新配置的 Office Web Apps Server。如果发现过程反复失败，则应该从拓扑文档删除 Office Web Apps Server，发布更新的拓扑，然后在已解决连接性问题后尝试将 Office Web Apps Server 添加回到该拓扑。

如果 Office Web Apps Server 显示为配置正确，并已由发现过程识别，则您可以通过共享 Microsoft Lync 2013 客户端对之间的 PowerPoint 演示文稿验证 Office Web Apps Server 是否按预期工作。如果用户 A 可加载并显示 PowerPoint 演示文稿，然后如果用户 B 可以加入会议，并看到该演示文稿，则 Office Web Apps Server 正在工作。

即使 Office Web Apps Server 显示为配置正确，但在尝试共享 PowerPoint 演示文稿时仍可能会收到错误消息“由于服务器连接性问题而使某些共享功能不可用”。如果收到该错误消息，您应该重新启动与新 Office Web Apps Server 关联的前面服务器（或服务器）。

