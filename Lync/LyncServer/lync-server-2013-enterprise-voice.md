---
title: Lync Server 2013 企业语音
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
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企业语音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-04-08_

使用企业语音，Lync 服务器提供一种独立的 Internet 协议（VoIP）产品，用于增强或更换传统专用分支 exchange （PBX）系统。 企业语音用户可以通过您的组织的 VoIP 网络或 PBX 呼叫同事，并且他们可以拨打您的组织外部的传统电话号码。 企业语音解决方案包括常见呼叫功能，如 "应答"、"转发"、"转移"、"保持"、"转移"、"发布和寄存" 以及 "增强9-1-1 （E9）" （E9-1-1 仅在美国可用）。）企业语音还支持一系列最新的和较旧的 IP 和 USB 设备。

<div>

## <a name="placing-and-receiving-calls"></a>拨打和接听电话

使用 Lync，用户可以通过在键盘上键入姓名或电话号码，或使用屏幕上显示的拨号盘来拨打电话。 用户也可以直接从其联系人列表中发起呼叫。 您也可以部署 Lync Phone 版设备，这些设备是由 Microsoft 合作伙伴提供的独立的 IP 电话设备。

用户可以有多个电话设备注册到 Lync 服务器，并且可以轻松地在它们之间进行切换。

使用 IP 电话设备上的可自定义铃声和类似于电脑上的即时消息的通知，用户同时收到对其所有设备的传入呼叫的通知。

用户还可以设置连接到其桌面电话、PC 和手机的单个电话号码，以便无论他们身在何处均可访问。

</div>

<div>

## <a name="basic-call-features"></a>基本呼叫功能

通话时，用户可以接听其他传入呼叫或发起拨出的通话，并且现有的活动通话将自动置于保持状态。 可以直接或在第一位用户与第二位用户进行私下通话时，将呼叫从一个用户转移到另一个用户。 用户还可以将呼叫转移到另一台设备;例如，他们可以将活动呼叫转移到其移动电话，因为他们将外出。

</div>

<div>

## <a name="richer-communications"></a>更丰富的通信

使用 Lync 与另一个用户交谈时，用户可以轻松地向呼叫添加文本、视频或桌面共享。 "请勿打扰" 功能与 Lync 中的状态设置集成。

通过 Exchange 统一消息（UM），Lync 和 Lync 服务器集成到 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013。 用户可以在其 Lync 窗口和电子邮件中查看是否有新的语音邮件。 在电子邮件中，他们可以单击以在电子邮件中播放语音邮件音频，或查看语音邮件的记录。

</div>

<div>

## <a name="advanced-calling-features"></a>高级通话功能

企业语音还包括多项高级通话功能，如 Lync 呼叫委派、团队呼叫、组呼叫分拣和响应组。

Lync 呼叫委派使用户可以通过 "**工具** \> **选项** \> **呼叫转接设置**" 将呼叫处理委派给一个或多个助理。 代理人可以代表用户执行多个呼叫任务，包括筛选呼叫、拨打电话和发起会议。

<div>


> [!IMPORTANT]  
> 您可能正在寻找另一个名称类似的功能，即 Lync 日历委派。 它不需要企业语音功能，并且允许用户从 Outlook 安排联机 Lync 会议。 如果你在此处查找此信息，我们建议签出<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-set-csclientpolicy</A>以了解有关启用 Exchange 委派同步的信息。



</div>

团队通话使用户可以让传入呼叫同时拨打团队成员的电话，以便团队中的任何人都可以接听呼叫。

组呼叫分拣，Lync Server 2013 的累积更新中的新功能：2月2013，允许用户通过其自己的电话应答传入呼叫。 组呼叫挑选与团队通话的不同之处在于：传入呼叫仅在预期收件人的电话上响铃，但任何其他用户都可以通过拨打呼叫装货组号码选择接听电话。

可以设置响应组，以便对指定的代理进行排队和智能地路由呼叫。 常见用途包括 IT 人员服务中心、人力资源 hotlines 和其他内部联系中心。

</div>

<div>

## <a name="enterprise-voice-administration"></a>企业语音管理

Lync 服务器使用标准和已发布接口与现有基础结构进行互操作。 它支持网关和 SIP 选项（如 SIP 中继），用于与 IP PBX 系统和 PSTN 网络的互连，以便你可以在一段时间内将用户迁移到企业语音，同时最大限度地减少中断。 Lync Server 支持传统的编解码器，如711、722和723.1，以实现与传统 VoIP 解决方案的互操作性。

使用呼叫许可控制（CAC），管理员可以对受约束的网络链接上的 Lync Server 语音和视频流量进行限制，并指定当新呼叫超过限制时要执行的操作。 操作可能包括通过备用路径路由，或者拒绝呼叫。

Lync Server 与第三方 Survivable 分支装置配合使用，以便在分支机构中提供本地呼叫服务和连接到 PSTN，以防 WAN 在中心站点出现故障。

</div>

</div>

<span> </span>

</div>

</div>

</div>

