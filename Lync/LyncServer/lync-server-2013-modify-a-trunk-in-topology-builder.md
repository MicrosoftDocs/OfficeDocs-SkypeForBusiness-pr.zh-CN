---
title: 在 Lync Server 2013 中修改拓扑生成器中的中继
TOCTitle: 在 Lync Server 2013 中修改拓扑生成器中的中继
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49888485
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中修改拓扑生成器中的中继

 

_**上一次修改主题：** 2012-09-21_

按照以下过程修改中继的备用媒体 IP 地址和备用绕过标识符。

## 修改中继的备用媒体 IP 地址

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在 Lync Server 命令行管理程序中运行 Set-CsPstnGateway cmdlet 并修改 AlternateBypassId 字段。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## 修改中继的备用 BypassID

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在 Lync Server 命令行管理程序中运行 Set-CsPstnGateway cmdlet 并修改 AlternateBypassId 字段。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

