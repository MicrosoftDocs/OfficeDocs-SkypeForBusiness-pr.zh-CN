---
title: Lync Server 2013：配置公共提供商的媒体加密
TOCTitle: 配置公共提供商的媒体加密
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205149(v=OCS.15)
ms:contentKeyID: 49313897
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置公共提供商的媒体加密

 

_**上一次修改主题：** 2014-12-12_

有关许可要求以及如何完成设置过程的详细信息，请参阅“Microsoft Lync Server、Office Communications Server 和 Live Communications Server 的公共 IM 连接设置指南”，网址为 <http://go.microsoft.com/fwlink/?linkid=155970>

如果要实现 Windows Live Messenger 与音频/视频 (A/V) 联盟，则必须修改以下两个参数： Lync Server 加密级别和 EnablePublicCloudAccess 策略。默认情况下，加密级别为“必需”。必须将此设置更改为“支持”。如果 nablePublicCloudAccess 策略设置为 False，则需要将其设置为“True”。可以通过 Lync Server 命令行管理程序执行此操作。

> [!IMPORTANT]  
> Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域连接。与 Windows Messenger 联盟除了 Lync 标准客户端访问许可证 (CAL) 之外不需要任何其他用户/设备许可证。明年，Skype 联盟将添加到此列表中，届时 Lync 用户将能够通过 IM 和语音与数以亿计的人联系。


## 为 Windows Live 配置联合

1.  在前端服务器上启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

2.  从命令提示符处，键入以下命令：
    
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption

       &nbsp;
    
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    > [!NOTE]  
    > 上述步骤是必需步骤，因为 Windows Live Messenger 不支持音频/视频加密。该命令会将您的全局策略设置为支持加密设置，而不会设置为要求音频/视频数据加密。支持加密的客户端（如 Lync 2013）将仍使用加密。
    

