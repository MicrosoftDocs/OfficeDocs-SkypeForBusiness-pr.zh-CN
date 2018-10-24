---
title: 在 Lync Server 2013 中配置语音电子邮件转义
TOCTitle: 在 Lync Server 2013 中配置语音电子邮件转义
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49888539
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置语音电子邮件转义

 

_**上一次修改主题：** 2013-02-22_

如果用户为移动电话配置同时响铃，则当移动电话关机、没电或没信号时，呼叫者通常将路由到用户的个人语音邮件。利用 Microsoft Lync Server 2013，用户可以选择将工作相关的呼叫路由到其企业语音邮件系统。具体而言，可以配置计时器，如果在定义的时间范围内通过运营商的语音邮件应答呼叫，则 Lync Server 2013 将从运营商的语音邮件系统（以及用户的个人语音邮件）断开连接，而企业系统中的用户剩余终结点将继续响铃。这样以来，呼叫者将自动路由到用户的企业语音邮件。

通过在语音策略级别将 Lync Server 命令行管理程序 cmdlet Set-CsVoicePolicy 与以下参数结合使用来执行此配置。

## 配置语音邮件转义

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  指定 **Set-CsVoicePolicy** 的以下参数：
    
      - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。
    
      - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。

## 示例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

