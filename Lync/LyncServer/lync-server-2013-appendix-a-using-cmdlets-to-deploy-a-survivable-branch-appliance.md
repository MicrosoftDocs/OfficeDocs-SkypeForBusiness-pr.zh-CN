---
title: Lync Server 2013：附录 A：使用 Cmdlet 部署 Survivable Branch Appliance
TOCTitle: 附录 A：使用 Cmdlet 部署 Survivable Branch Appliance
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398598(v=OCS.15)
ms:contentKeyID: 49313323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 附录 A：在 Lync Server 2013 中使用 Cmdlet 部署 Survivable Branch Appliance

 

_**上一次修改主题：** 2012-10-07_

本主题介绍如何使用 Lync Server 命令行管理程序部署 Survivable Branch Appliance。请在中央站点执行此过程。

## 远程部署 Survivable Branch Appliance

1.  使用 [在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)中的过程添加新的分支站点。

2.  将分支站点加入到域中。

3.  将 RTCUniversalSBATechnicians 组添加到本地 Administrators 组。

4.  重新启动服务器，并以 RTCUniversalSBATechnicians 组成员的身份登录到该服务器。

5.  在 Lync Server 命令行管理程序中，键入以下命令，将占位符替换为组织的正确信息：
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

