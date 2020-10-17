---
title: Lync Server 2013：验证 Office Web Apps Server 的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a33a5e9bb93371bdccac3c88b7a1c080e3efaa8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503679"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>在 Lync Server 2013 中验证 Office Web Apps Server 的配置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-22_

将 Office Web Apps Server 添加到拓扑，并在该拓扑发布之后，您应该会在 Lync Server 事件日志中看到两个新的事件日志事件。 首先，应添加一个 LS 数据 MCU 事件 (事件 ID 41034) ;此事件将报告已发现 Office Web Apps Server：

**已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**

例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：

**Web 会议服务器 Office Web Apps Server 发现已成功。**

**Office Web Apps Server 内部演示者页面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps Server 内部与会者页面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps Server 外部演示者页面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps Server 内部与会者页面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

如果您看到 LS Data MCU 事件，事件 ID 为 41033，则意味着 Office Web Apps Server 发现已失败。 在这种情况下，Microsoft Lync Server 2013 将根据需要尝试多次，以发现新配置的 Office Web Apps 服务器。 如果发现过程反复失败，则应该从拓扑文档删除 Office Web Apps Server，发布更新的拓扑，然后在已解决连接性问题后尝试将 Office Web Apps Server 添加回到该拓扑。

如果 Office Web Apps Server 看起来已正确配置且已被发现过程识别，则可以通过在一对 Microsoft Lync 2013 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps Server 是否按预期方式工作。 如果用户 A 可加载并显示 PowerPoint 演示文稿，然后如果用户 B 可以加入会议，并看到该演示文稿，则 Office Web Apps Server 正在工作。

即使 Office Web Apps Server 显示为配置正确，但在尝试共享 PowerPoint 演示文稿时仍可能会收到错误消息“由于服务器连接性问题而使某些共享功能不可用”。如果收到该错误消息，您应该重新启动与新 Office Web Apps Server 关联的前面服务器（或服务器）。

</div>

<span> </span>

</div>

</div>

</div>

