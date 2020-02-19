---
title: 在 Microsoft Lync Phone Edition 设备上配置服务质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2033e3a59684e2d551448e37cccb9be2d027313f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

虽然默认情况下不为 Iphone 等设备启用服务质量（QoS），但默认情况下为运行 Lync Phone Edition 的设备启用了 QoS。 （这些设备通常称为 "UC" 或 "统一通信电话"。）若要验证这一点，请在 Lync Server 命令行管理程序中运行以下 Windows PowerShell 命令：

    Get-CsUCPhoneConfiguration

如果尚未对 UC 电话配置设置进行任何更改，则将会得到看起来如下所示的信息：

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

针对服务质量，只有其中一个属性很重要：VoiceDiffServTag。 VoiceDiffServTag 表示分配给来自 Lync Phone Edition 设备的语音流量 emanating 的 DSCP 值。

<div>


> [!NOTE]
> Lync Server 2013 不再支持 Voice8021p 参数。 参数仍然有效，以与 Microsoft Lync Server 2010 保持向后兼容;但是，它对在 Lync Server 2013 中使用的设备没有影响。



</div>

在大多数网络中，使用 VoiceDiffServTag 40 标记 Lync Phone Edition 数据包不会导致出现任何问题。 但是，40 并不是通常用于音频流量的值；音频流量几乎始终用 DSCP 代码 46 进行标记。 为了在整个网络中保持一致性，您可能想要将 UC 电话的 VoiceDiffServTag 属性更改为 46。

若要执行此操作，可以使用 Windows PowerShell 或 Lync Server 控制面板。 若要使用 Windows PowerShell 修改 VoiceDiffServTag 值，请在 Lync Server 命令行管理程序中运行以下命令：

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上述命令会修改 UC 电话配置设置的全局集合。但请注意，也可以将 UC 电话设置分配给站点范围。要修改站点范围的 UC 电话配置设置，您必须指定站点 Identity。例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用以下命令同时修改所有 UC 电话配置设置：

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您更愿意使用 Lync Server 控制面板进行此更改，请启动 "控制面板"，然后完成以下过程：

1.  单击“客户端”****，然后单击“设备配置”****。

2.  在“设备配置”**** 选项卡上，双击要修改的设置集合（例如，“全局”****）。

3.  在“编辑设备配置”**** 对话框中，将“语音服务质量 (QoS)”**** 框的值设置为 **46**，然后单击“提交”****。

如果您拥有多个集合，则需要针对每个 UC 电话设置集合重复此过程。 Lync Server 控制面板将不允许同时修改多个设置集合。

如果您所拥有的设备并不是基于您组织中的 Windows 操作系统（如 iPhone），则更改 VoiceDiffServTag 设置不会对这些设备造成影响。如果您想要更改这些设备上的 DSCP 值，则需要参考管理手册，以了解每种设备类型。

</div>

<span> </span>

</div>

</div>

</div>

