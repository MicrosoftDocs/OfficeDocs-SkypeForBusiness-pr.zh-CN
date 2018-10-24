---
title: 在 Lync Server 2013 中测试 SIP 中继配置设置
TOCTitle: 在 Lync Server 2013 中测试 SIP 中继配置设置
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49888606
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中测试 SIP 中继配置设置

 

_**上一次修改主题：** 2012-11-01_

SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置会执行如指定以下内容的操作：

  - 是否在中继上启用媒体旁路功能。

  - 发送实时传输控制协议 (RTCP) 数据包的条件。

  - 在每个中继上是否需要安全实时协议 (SRTP) 加密。

安装 Microsoft Lync Server 2013 时，将为您创建一个 SIP 中继配置设置的全局集合。此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。

只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 测试中继配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 测试中继配置设置

  - 以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

