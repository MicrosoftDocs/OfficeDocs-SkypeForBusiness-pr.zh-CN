---
title: 在 Lync Server 2013 中查看中继配置信息
TOCTitle: 在 Lync Server 2013 中查看中继配置信息
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49888668
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看中继配置信息

 

_**上一次修改主题：** 2013-02-22_

SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：

  - 是否在中继上启用媒体旁路功能。

  - 发送实时传输控制协议 (RTCP) 数据包的条件。

  - 在每个中继上是否需要安全实时协议 (SRTP) 加密。

当安装 Microsoft Lync Server 2013 时，就会为您创建 SIP 中继配置设置的全局集合。另外，管理员可在站点作用域或在服务作用域（仅适用于 PSTN 网关服务）创建自定义设置集合。

## 通过使用 Lync Server 控制面板查看 SIP 中继配置信息

1.  在 Lync Server 控制面板 中，单击“语音路由”，然后单击“Trunk 配置”。

2.  在“Trunk 配置”选项卡上，您将看到一个所有 Trunk 配置设置集合的列表；对于每个集合，您将看到“名称”、“范围”、“状态”和“媒体旁路”属性的值及与该集合关联的“PSTN 用法”、“呼叫号码规则”和“已呼叫号码规则”的数量。要查看有关中继配置设置集合的其他详细信息，请单击有兴趣的集合，单击“编辑”，再单击“显示详细信息”。请注意，一次仅可查看中继配置设置的一个集合的详细信息。

## 通过使用 Lync Server PowerShell Cmdlet 可查看 SIP 中继配置信息

还可以通过使用 Lync Server PowerShell 和 Get-CsTrunkConfiguration cmdlet 查看 SIP 中继配置设置。此 cmdlet 可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看 SIP 中继配置信息

  - 要查看有关所有 SIP 中继配置设置的信息，在 Lync Server 命令行管理程序中输入下列命令，然后按 Enter：
    
        Get-CsTrunkConfiguration
    
    这将返回与以下类似的信息：
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

有关详细信息，请参阅[Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。

