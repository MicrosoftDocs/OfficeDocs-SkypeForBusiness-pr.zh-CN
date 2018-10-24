---
title: 在 Microsoft Lync Phone Edition 设备上配置服务质量
TOCTitle: 在 Microsoft Lync Phone Edition 设备上配置服务质量
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205137(v=OCS.15)
ms:contentKeyID: 49313844
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Microsoft Lync Phone Edition 设备上配置服务质量

 

_**上一次修改主题：** 2012-11-01_

虽然默认情况下不会针对 iPhone 等设备启用服务质量 (QoS)，但是会默认针对运行 Lync Phone Edition 的设备（这些设备通常称为 UC 或统一通信电话）启用 QoS。要对此进行验证，请从 Lync Server 命令行管理程序中运行以下 Windows PowerShell 命令：

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

针对服务质量，只有其中一个属性很重要：VoiceDiffServTag。VoiceDiffServTag 代表分配给来自于 Lync Phone Edition 设备的语音流量的 DSCP 值。

> [!NOTE]  
> Lync Server 2013 中不再支持 Voice8021p 参数。该参数仍适用于与 Microsoft Lync Server 2010 的向后兼容；但是，它对与 Lync Server 2013 一起使用的设备没有影响。



在大多数网络中，标记 VoiceDiffServTag 为 40 的 Lync Phone Edition 数据包不应造成任何问题。但是，40 并不是通常用于音频流量的值；音频流量几乎始终用 DSCP 代码 46 进行标记。为了在整个网络中保持一致性，您可能想要将 UC 电话的 VoiceDiffServTag 属性更改为 46。

为此，您可以使用 Windows PowerShell 或 Lync Server 控制面板。要使用 Windows PowerShell 修改 VoiceDiffServTag 值，请从 Lync Server 命令行管理程序中运行以下命令：

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上述命令会修改 UC 电话配置设置的全局集合。但请注意，也可以将 UC 电话设置分配给站点范围。要修改站点范围的 UC 电话配置设置，您必须指定站点 Identity。例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用以下命令同时修改所有 UC 电话配置设置：

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您倾向于使用 Lync Server 控制面板进行此项更改，请启动“控制面板”，然后完成以下过程：

1.  单击“客户端”，然后单击“设备配置”。

2.  在“设备配置”选项卡上，双击要修改的设置集合（例如，“全局”）。

3.  在“编辑设备配置”对话框中，将“语音服务质量 (QoS)”框的值设置为 **46**，然后单击“提交”。

如果您拥有多个集合，则需要针对每个 UC 电话设置集合重复此过程。Lync Server 控制面板不允许您同时修改多个设置集合。

如果您所拥有的设备并不是基于您组织中的 Windows 操作系统（如 iPhone），则更改 VoiceDiffServTag 设置不会对这些设备造成影响。如果您想要更改这些设备上的 DSCP 值，则需要参考管理手册，以了解每种设备类型。

