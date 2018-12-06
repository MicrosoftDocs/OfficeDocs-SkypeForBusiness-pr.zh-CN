---
title: 查看网络接口信息
TOCTitle: 查看网络接口信息
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49888652
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络接口信息

 

_**上一次修改主题：** 2013-02-23_

## 使用 Lync Server 命令行管理程序 Cmdlet 查看网络接口信息

通过使用 Lync Server 命令行管理程序和 **Get-CsNetworkInterface** cmdlet 可查看网络接口信息。可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络接口信息

  - 要查看网络接口信息，请在 Lync Server 命令行管理程序中键入下列命令，然后按 Enter：
    
        Get-CsNetworkInterface
    
    对于每个网络接口，此命令返回的信息类似于以下内容：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

有关详细信息，请参阅 [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface)。

