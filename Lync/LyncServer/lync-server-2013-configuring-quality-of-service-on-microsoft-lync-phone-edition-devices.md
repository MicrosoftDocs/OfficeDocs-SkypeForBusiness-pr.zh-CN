---
title: 在 Microsoft Lync Phone Edition 设备上配置服务质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

虽然默认情况下不为 Iphone 等设备启用服务质量 (QoS), 但对于运行 Lync Phone Edition 的设备, 默认情况下启用 QoS。 (这些设备通常称为 UC 或统一通信电话。)若要验证此内容, 请从 Lync Server 命令行管理程序中运行以下 Windows PowerShell 命令:

    Get-CsUCPhoneConfiguration

如果您未对 UC 手机配置设置进行任何更改, 则您将获得如下所示的信息:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

对于服务质量目的, 仅关注以下属性之一: VoiceDiffServTag。 VoiceDiffServTag 表示分配给 Lync Phone Edition 设备的语音流量 emanating 的 DSCP 值。

<div>


> [!NOTE]
> Lync Server 2013 不再支持 Voice8021p 参数。 该参数仍然有效, 可向后兼容 Microsoft Lync Server 2010;但是, 它对使用 Lync Server 2013 的设备不起作用。



</div>

在大多数网络中, 使用40的 VoiceDiffServTag 标记 Lync Phone Edition 数据包不会导致任何问题。 但是, 40 不是通常用于音频流量的值;相反, 音频流量几乎始终标有 DSCP 代码46。 为了保持整个网络的一致性, 您可能希望将您的 UC 手机的 VoiceDiffServTag 属性更改为46。

若要执行此操作, 您可以使用 Windows PowerShell 或 Lync Server "控制面板"。 若要使用 Windows PowerShell 修改 VoiceDiffServTag 值, 请从 Lync Server 命令行管理程序中运行以下命令:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上面的命令修改 UC 手机配置设置的全局集合。 但是请注意, UC 电话设置也可以分配给网站范围。 若要在网站范围内修改 UC 手机配置设置, 必须指定网站标识。 例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用以下命令同时修改您的所有 UC 手机配置设置:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您希望使用 Lync Server "控制面板" 进行此更改, 请启动 "控制面板", 然后完成以下过程:

1.  单击 "**客户端**", 然后单击 "**设备配置**"。

2.  在 "**设备配置**" 选项卡上, 双击要修改的设置集合 (例如, "**全局**")。

3.  在 "**编辑设备配置**" 对话框中, 将 "**语音服务质量 (QoS)** " 框的值设置为**46** , 然后单击 "**提交**"。

如果你有多个集合, 你将需要为每个 UC 电话设置集合重复此过程。 Lync Server "控制面板" 将不允许同时修改多个设置集合。

如果你的设备不是基于你组织中的 Windows 操作系统 (如 Iphone), 这些设备将不会受到更改 VoiceDiffServTag 设置的影响。 如果你想要在这些设备上更改 DSCP 值, 你需要参考每个设备类型的管理手册。

</div>

<span> </span>

</div>

</div>

</div>

