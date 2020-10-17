---
title: Lync Server 2013 企业版语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39179f1db1c547081e059d9b3ee275c924621cab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533169"
---
# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企业语音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-04-08_

使用企业语音，Lync Server 可提供独立的 Internet 协议 (VoIP) 产品，以增强或替换传统专用交换机 (PBX) 系统。 企业语音用户可以呼叫组织的 VoIP 网络或 PBX 上的同事，也可以呼叫组织外部的传统电话号码。 企业语音解决方案包含常见的呼叫功能，如解答、转发、转移、保留、转移、释放和寄存以及增强的 9-1-1 (E9-1-1) 呼叫 (E9-1-1 仅适用于美国。 ) 的企业语音还支持各种当前和较旧的 IP 和 USB 设备。

<div>

## <a name="placing-and-receiving-calls"></a>发起和接收呼叫

通过使用 Lync，用户可以通过在其键盘上键入姓名或电话号码，或使用屏幕上显示的拨号垫来发出呼叫。 用户还可以直接从联系人列表中发起呼叫。 您还可以部署 Lync Phone Edition 设备，这是由 Microsoft 合作伙伴提供的独立 IP 电话设备。

用户可以使用 Lync Server 注册多个电话设备，并且可以轻松地在它们之间进行切换。

来电时将同时在用户的所有设备上通知用户，IP 电话设备上将播放可自定义的铃声，PC 上将显示类似即时消息的通知。

用户还可以设置与桌面电话、PC 和移动电话连接的单个电话号码，以便能够随时随地接听电话。

</div>

<div>

## <a name="basic-call-features"></a>基本呼叫功能

在通话过程中，用户可以应答其他传入呼叫或发起传出呼叫，现有的活动呼叫将自动置于保持状态。可以直接或在第一个用户与第二个用户私下通话后，将呼叫从一个用户转接至另一个用户。用户还可以将呼叫转接至其他设备；例如，用户在办公室外接听电话时可以将活动呼叫转接至移动电话。

</div>

<div>

## <a name="richer-communications"></a>更丰富的通信

当使用 Lync 与其他用户对话时，用户可以轻松地向呼叫中添加文本、视频或桌面共享。 "请勿打扰" 功能与 Lync 中的状态设置集成在一起。

使用 Exchange 统一消息 (UM) ，Lync 和 Lync Server 与 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013 集成。 用户可以查看他们的 Lync 窗口和电子邮件中是否有新的语音邮件。 在电子邮件中，用户可以通过单击播放电子邮件中的语音邮件音频，或查看语音邮件的脚本。

</div>

<div>

## <a name="advanced-calling-features"></a>高级呼叫功能

企业语音还包括几种高级呼叫功能，如 Lync 呼叫委派、团队呼叫、组呼叫应答和响应组。

通过 Lync 呼叫委派，用户可以将呼叫处理委派给一个或多个助理，方法是转到 " **工具**" \> **选项**" \> **呼叫转接设置**"。 代理人可以代表用户执行多项呼叫任务，包括筛选呼叫、发起呼叫和发起会议。

<div>


> [!IMPORTANT]  
> 您可能正在寻找其他名称相似的功能，即 Lync 日历委派。 它不需要企业语音功能，允许用户安排 Outlook 中的联机 Lync 会议。 如果你已经在这里查找此信息，我们建议检查 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-csclientpolicy</A> 以了解有关启用 Exchange 委派同步的信息。



</div>

团队呼叫使用户可以让传入呼叫同时拨打团队的电话，以便团队中的任何人都能接听呼叫。

组呼叫应答（Lync Server 2013 的累积更新中的新功能：2月2013）允许用户将传入呼叫从其自己的电话应答给其同事。 组内呼叫应答与团队呼叫的不同之处在于，在预期收件人的电话中，传入呼叫只会响铃，但任何其他用户都可以通过拨打呼叫应答组号码来选择应答。

可以对响应组进行设置，以便将呼叫排队并智能路由至指定的代理。常见用途包括 IT 技术支持、人力资源热线和其他内部联络中心。

</div>

<div>

## <a name="enterprise-voice-administration"></a>企业语音管理

Lync Server 使用标准和已发布的接口与现有的基础结构进行互操作。 它支持用于与 IP PBX 系统和 PSTN 网络进行互联的网关和 SIP 选项（如 SIP 中继），以便以后可以将用户迁移至企业语音，同时最大限度地减少中断。 Lync Server 支持传统的编解码器，如 g.711、g.722 和 g.723.1，以实现与传统 VoIP 解决方案的互操作性。

通过呼叫允许控制 (CAC) ，管理员可以对受约束的网络链接上传输的 Lync Server 语音和视频流量设置限制，并指定在新呼叫超过限制时要采取的操作。 这些操作包括使用备用路径路由或拒绝呼叫。

Lync Server 与第三方 Survivable 分支装置配合使用，以提供本地呼叫服务并连接到分支机构的 PSTN，以防 WAN 在中央站点出现故障。

</div>

</div>

<span> </span>

</div>

</div>

</div>

