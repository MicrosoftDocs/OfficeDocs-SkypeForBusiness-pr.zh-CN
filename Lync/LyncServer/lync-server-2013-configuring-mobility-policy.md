---
title: Lync Server 2013：配置移动策略
TOCTitle: 配置移动策略
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690018(v=OCS.15)
ms:contentKeyID: 49312940
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置移动策略

 

_**上一次修改主题：** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供了移动策略，这些策略确定谁可以使用移动功能、单位电话呼叫、IP 语音 (VoIP) 或视频以及 VoIP 或视频是否将需要 WiFi。单位电话呼叫功能使移动用户能够通过使用工作电话号码（而非移动电话号码）在移动电话上发出和接收呼叫。此功能阻止被呼叫方看到呼叫者的移动电话号码，并使用户能够避免出站呼叫费用。通过配置 VoIP 和视频，用户可以接收和发出 VoIP 呼叫和视频。WiFi 用法的设置定义用户的设备是否将需要使用 WiFi 网络而非蜂窝数据网络。

默认情况下，移动、单位电话呼叫以及 VoIP 和视频功能都已启用。禁用了 VoIp 和视频需要 WiFi 的设置。管理员可确定谁可以通过运行 cmdlet 访问这些功能。您可以按网站或用户全局禁用这些选项。

为了能够使用移动功能和单位电话呼叫功能，用户必须满足以下先决条件：

  - 用户必须启用 Lync Server 2013。

  - 用户必须启用 企业语音。

  - 必须为用户分配已将“EnableMobility”选项设置为 True 的移动策略。

对于希望能使用单位电话呼叫功能的用户，他们必须满足以下两个额外的先决条件：

  - 必须为用户分配已选择“允许多部电话同时响铃”选项的语音策略。

  - 必须为用户分配已将“EnableOutsideVoice”选项设置为 True 的移动策略。

> [!NOTE]  
> 未启用企业语音的用户可以使用其移动设备来发出 Lync 到 Lync IP 语音 (VoIP) 呼叫，也可以在其移动设备上使用“单击以加入”链接来加入会议（如果您为这些用户分配了语音策略的适当选项）。有关详细信息，请参阅<a href="lync-server-2013-defining-your-mobility-requirements.md">定义您的 Lync Server 2013 移动要求</a>。



有关为用户启用 Lync Server 2013 的详细信息，请参阅 [禁用或重新启用 Lync Server 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。有关为用户启用 企业语音的详细信息，请参阅 [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。有关设置语音策略选项的详细信息，请参阅 [在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

## 修改全局移动策略

1.  以 CsAdministrator 角色的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  全局禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    > [!NOTE]  
    > 您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。
    


## 按网站修改移动策略

1.  以 CsAdministrator 角色的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  创建网站级别策略，禁用 VoIP 和视频，并按网站为 IP 音频和 IP 视频启用“需要 WiFi”。在命令行中键入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## 通过用户修改移动策略

1.  以 CsAdministrator 角色的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  创建用户级别移动策略，然后按用户禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。
    
    例如：
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## 另请参阅

#### 任务

[禁用或重新启用 Lync Server 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### 概念

[定义您的 Lync Server 2013 移动要求](lync-server-2013-defining-your-mobility-requirements.md)  

#### 其他资源

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

