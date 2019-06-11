---
title: 'Lync Server 2013: 在启用 Lync 的电话上使用呼叫我'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>在启用 Lync 的电话和 Lync Server 2013 上使用 "呼叫我"

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-08-09_

Lync 中的 "呼叫我" 功能为用户提供了一种使用手机、"土地线" 或其他连接到公共交换电话网络 (PSTN) 的设备加入会议音频部分的方式。 当您尝试使用 Lync 加入会议时, 通常会显示 "**加入会议音频**" 对话框:

![使用 Lync 加入会议音频窗口屏幕截图](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入会议音频窗口屏幕截图")

如果选择 "**呼叫我**", 则可以从下拉列表中选择电话号码。 Lync Server 2013 将拨打所选号码的电话, 然后您可以使用该电话参与会议的音频部分。

下拉列表由您在 " **Lync-选项**" 对话框中的 "**电话**" 选项卡上输入的电话号码 (用于移动电话、家庭电话或其他电话) 填充:

![Lync 手机设置选项屏幕截图](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 手机设置选项屏幕截图")

如果您未在 "**电话**" 选项卡上输入任何电话号码, 则下拉框中将没有任何可用号码。 但是, 您始终可以单击 "**新号码**", 让 Lync Server 拨出到您想要的任何电话号码:

![Lync 加入会议音频呼叫我窗口屏幕截图](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入会议音频呼叫我窗口屏幕截图")

在功能上, "呼叫我" 功能非常有用, 因为它的使用方式如下: 让 Lync 服务器呼叫 PSTN 电话号码。 但是, 如果你让 Lync 服务器在启用 Lync 的终结点 (例如, 会议室中的电话) 呼叫你, 则可以运行到低于最佳的体验。 下面是你可能遇到的问题, 以及解决此问题的两种方法。

若要开始, 请在使用支持 Lync 的手机的电话号码向 "呼叫我" 提供功能时执行的操作。 假设 Ken Myer 尝试通过让 Lync Server 在 1-206-555-1219 (启用 Lync 服务器的电话号码) 上呼叫他来加入会议。 Ken 最初将连接到会议, 但在几秒钟后, Lync 将显示消息**通话未完成或已结束**, 并且 Ken 将显示为已从会议中删除:

![Lync 呼叫会议窗口的屏幕截图](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 呼叫会议窗口的屏幕截图")

但是请注意, Lync 对话窗口中存在差异。 Ken Myer 是 "**参与者**" 标题下列出的唯一名称。 但是, 如果你查看窗口的标题栏, 你将看到该会议总共包含4个参与者。

同样, 如果你查看任何其他会议参与者的对话窗口, 你将看不到任何地方列出的 Ken Myer:

![Lync 参与者列表窗口屏幕截图](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参与者列表窗口屏幕截图")

同时, Ken Myer 还将能够使用其支持 Lync 的手机参与呼叫的音频部分的会议。 "呼叫我" 功能实际上已起作用, 但用户体验不是最佳的。

至少有两种方法可以解决此问题。 如果您已以这种方式加入会议 (如 Ken Myer), 则通常可以通过使用不同的模态来解决该问题。 例如, 如果发送即时消息, 则对话窗口现在将显示所有会议参与者, 包括你:

![Lync 对话和参与者列表屏幕截图](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 对话和参与者列表屏幕截图")

此时, 你应该能够以预期的方式参与会议。

或者, 您可以通过更改加入会议的方式来完全避免此问题。 如果您需要让 Lync Server 呼叫支持 Lync 服务器的手机, 则应首先在没有音频连接的情况下加入会议。 若要执行此操作, 请在显示 "加入会议音频" 对话框时选择 "不加入音频":

![Lync 不加入会议音频窗口屏幕截图](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入会议音频窗口屏幕截图")

成功连接到会议后, 您现在可以 "邀请" Lync Server 启用的手机加入会议。 若要执行此操作, 请将鼠标放在 "人员" 图标上, 然后单击 "**邀请更多人**":

![Lync 邀请更多参与者窗口屏幕截图](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀请更多参与者窗口屏幕截图")

将弹出 "**发送 IM** " 对话框。 忽略对话框标题 (实际上不是发送即时消息), 然后键入启用 Lync 的手机的电话号码:

!["发送 IM" 对话框屏幕截图](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "\"发送 IM\" 对话框屏幕截图")

单击 **"确定**" 后, Lync Server 将呼叫在对话框中输入的号码。 建立连接后, 您将能够通过启用 Lync 的手机获得全音频功能, 您将能够看到完整的会议名单并与之交互。

</div>

<span> </span>

</div>

</div>

</div>

