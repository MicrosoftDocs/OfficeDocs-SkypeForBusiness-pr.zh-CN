---
title: 向公共区域电话分配策略
TOCTitle: 向公共区域电话分配策略
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994082(v=OCS.15)
ms:contentKeyID: 52061152
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向公共区域电话分配策略

 

_**上一次修改主题：** 2013-02-20_

在为公用区域电话创建您的策略（有关详细信息，请参阅[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)）后，您可以使用 Windows PowerShell 和适当的 **Grant-Cs** cmdlet 向公用区域电话分配该策略。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。


## 向单个公用区域电话分配策略

  - 以下命令向具有 Identity Building 14 Lobby 的公用区域电话分配每用户语音策略 RedmondVoice。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## 向多个公用区域电话分配策略

  - 在此示例中，会向配置为在组织中使用的所有公用区域电话分配每用户语音策略 RedmondVoice。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

有关详细信息，请参阅 [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy) 的帮助主题。

## 另请参阅

#### 其他资源

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

