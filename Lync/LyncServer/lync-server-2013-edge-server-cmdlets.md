---
title: 边缘服务器 Cmdlet
TOCTitle: 边缘服务器 Cmdlet
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg415635(v=OCS.15)
ms:contentKeyID: 49312153
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 边缘服务器 Cmdlet

 

_**上一次修改主题：** 2016-12-08_

边缘服务器提供了一种使未登录到内部网络的用户也可以使用 Microsoft Lync Server 2013 功能的方法。例如，如果有远程用户（已经过身份验证）通过 Internet 而不是内部网络登录 Lync Server 2013，则需要设置运行 Lync Server 访问边缘服务的边缘服务器。此外，如果要与另一个组织建立联盟，或要允许用户与具备公共即时消息服务（如 Yahoo\!、AOL 或 MSN）的帐户持有者进行通信，则需要边缘服务器。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>

## 边缘服务器 Cmdlet

以下是与管理边缘服务器直接相关的 cmdlet 列表：

**边缘服务器**

  -   
    [Get-CsAccessEdgeConfiguration](get-csaccessedgeconfiguration.md)

  -   
    [Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)

  -   
    [Get-CsAVEdgeConfiguration](get-csavedgeconfiguration.md)

  -   
    [New-CsAVEdgeConfiguration](new-csavedgeconfiguration.md)

  -   
    [Remove-CsAVEdgeConfiguration](remove-csavedgeconfiguration.md)

  -   
    [Set-CsAVEdgeConfiguration](set-csavedgeconfiguration.md)

  -   
    [Test-CsAVEdgeConnectivity](test-csavedgeconnectivity.md)

  -   
    [Set-CsEdgeServer](set-csedgeserver.md)

## 另请参阅

#### 其他资源

[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/?linkid=203150)

