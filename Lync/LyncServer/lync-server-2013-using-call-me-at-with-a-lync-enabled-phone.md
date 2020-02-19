---
title: Lync Server 2013：在启用 Lync 的电话上使用呼叫我
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c91980655d6786a092856c454ce4d662fef56e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>将 "呼叫我" 与启用 Lync 的手机和 Lync Server 2013 一起使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-08-09_

Lync 中的 "呼叫我" 功能为用户提供了一种通过手机、"土地线" 或连接到公用电话交换网（PSTN）的其他设备加入会议的音频部分的方法。 当您尝试使用 Lync 加入会议时，通常会显示 "**加入会议音频**" 对话框：

![使用 Lync 加入会议音频窗口屏幕截图](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入会议音频窗口屏幕截图")

如果选择 "**呼叫我**"，则可以从下拉列表中选取一个电话号码。 Lync Server 2013 将向所选号码发出电话呼叫，然后你可以使用该电话参与会议的音频部分。

下拉列表由您在 " **Lync –选项**" 对话框中的 "**电话**" 选项卡上输入的电话号码（对于移动电话、家庭电话或其他电话）填充：

![Lync 电话设置选项屏幕截图](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 电话设置选项屏幕截图")

如果未在 "**电话**" 选项卡上输入任何电话号码，则下拉框中将不提供任何号码。 但是，您始终可以单击 "**新号码**"，让 Lync Server 拨出到您想要的任何电话号码：

![Lync 加入会议音频呼叫我窗口屏幕截图](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入会议音频呼叫我窗口屏幕截图")

如果你按预期方式使用此功能，则 "呼叫我" 功能会非常好地发挥作用：通过让 Lync Server 呼叫 PSTN 电话号码。 但是，如果要求 Lync Server 在启用 Lync 的终结点（例如，会议室中的电话）呼叫你，则可以运行到不到最佳的体验中。 下面是您可能遇到的问题，以及解决问题的两种方法。

若要开始，请在向支持 Lync 的电话号码提供电话号码时提供 "呼叫我" 功能。 假设 Ken Myer 尝试通过让 Lync Server 呼叫他（即启用 Lync Server 的电话号码）在1-206-555-1219 加入会议。 Ken 最初将连接到会议，但在几秒钟后，Lync 将显示消息**呼叫未完成或已结束**，并且 Ken 将显示为已从会议中删除：

![Lync 通话会议窗口的屏幕截图](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通话会议窗口的屏幕截图")

但请注意，Lync 对话窗口中存在差异。 Ken Myer 是在 "**参与者**" 标题下列出的唯一名称。 但是，如果您查看窗口的标题栏，将会看到会议总共包含4个参与者。

同样，如果您在 "对话" 窗口中查看任何其他会议参与者，将不会看到 "Ken Myer" 列于任何地方：

![Lync 参与者列表窗口屏幕截图](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参与者列表窗口屏幕截图")

同时，Ken Myer 将能够通过使用其启用 Lync 的电话参与呼叫的音频部分参与。 呼叫我的功能实际工作正常，但用户体验不是最佳的。

至少有两种方法可以解决此问题。 如果你已采用这种方式加入会议（如 Ken Myer），则通常可以通过使用不同的模态来解决此问题。 例如，如果发送即时消息，对话窗口现在将显示所有会议参与者，包括您自己：

![Lync 对话和参与者列表屏幕截图](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 对话和参与者列表屏幕截图")

此时，您应能够以预期方式参与会议。

或者，可以通过更改加入会议的方式来完全避免此问题。 如果需要让 Lync Server 呼叫启用 Lync Server 的电话，则应首先在不使用音频连接的情况下加入会议。 若要执行此操作，请选择 "加入会议音频" 对话框显示 "不加入音频"：

![Lync 不加入会议音频窗口屏幕截图](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入会议音频窗口屏幕截图")

成功连接到会议后，您现在可以 "邀请" 启用 Lync Server 的电话，也加入会议。 若要执行此操作，请将鼠标放在 "人员" 图标上，然后单击 "**邀请更多人**"：

![Lync 邀请更多参与者窗口屏幕截图](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀请更多参与者窗口屏幕截图")

这将显示 "**发送 IM** " 对话框。 忽略对话框标题（实际上并不是发送即时消息），并键入启用了 Lync 的手机的电话号码：

!["发送 IM" 对话框屏幕截图](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png ""发送 IM" 对话框屏幕截图")

单击 **"确定"** 后，Lync Server 将调用在对话框中输入的号码。 建立连接后，你将通过启用 Lync 的手机获得全音频功能，你将能够看到完整的会议名单并与之交互。

</div>

<span> </span>

</div>

</div>

</div>

