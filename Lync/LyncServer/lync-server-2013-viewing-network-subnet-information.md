---
title: 查看网络子站点信息
TOCTitle: 查看网络子站点信息
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49888399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络子站点信息

 

_**上一次修改主题：** 2013-02-23_

您可使用以下过程查看网络子网。从 Lync Server 控制面板中，您可创建、修改或删除网络子网。有关创建或修改网络子网的详细信息，请参阅[创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。

## 查看网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“子网”。

4.  在“子网”页上，单击要查看的子网。
    
    > [!NOTE]
    > 一次只能查看一个子网。


5.  在“编辑”菜单上，单击“显示详细信息…”。

## 使用 Lync Server PowerShell Cmdlet 查看网络子网配置信息

还可使用 Lync Server PowerShell 和 Get-CsNetworkSubnet cmdlet 查看网络子网信息。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络子网信息

  - 若要查看有关所有网络子网的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsNetworkSubnet
    
    这将返回与以下内容类似的信息：
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

有关详细信息，请参阅 [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)  
[删除网络子网](lync-server-2013-deleting-network-subnets.md)

