---
title: 在 Lync Server 2013 中查看有关各个 SIP 中继的信息
TOCTitle: 在 Lync Server 2013 中查看有关各个 SIP 中继的信息
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49888561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看有关各个 SIP 中继的信息

 

_**上一次修改主题：** 2013-02-21_

SIP 中继用来将 Microsoft Lync Server 2013 IP 语音电话网络与公用电话交换网进行连接。在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。因此，PSTN 网关和 SIP 中继基本上完全相同。对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。

但是，在 Lync Server 2013 中，现在可以将多个中继分配给一个 PSTN 网关；这意味着网关和中继不再是一个并且相同。而这意味着管理员必须使用新的 [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet，才能查看有关个别 SIP 中继的信息。

可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行 Get-CsTrunk cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看所有 SIP 中继的信息

  - 以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：
    
        Get-CsTrunk

## 查看特定 SIP 中继的信息

  - 此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## 查看分配给池的所有 SIP 中继的信息

  - 在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

