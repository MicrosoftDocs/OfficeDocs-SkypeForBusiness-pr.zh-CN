---
title: 查看网络区域信息
TOCTitle: 查看网络区域信息
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49888443
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络区域信息

 

_**上一次修改主题：** 2013-02-23_

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。您可以使用 Lync Server 控制面板查看网络区域。网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。使用本主题可查看现有网络区域。有关创建或修改现有网络区域的详细信息，请参阅[创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。

## 使用 Lync Server 控制面板查看有关网络区域的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域”。

4.  在“区域”页上，单击要查看的区域。
    
    > [!NOTE]
    > 您一次只能查看一个区域。


5.  在“编辑”菜单上，单击“显示详细信息”。

## 使用 Windows PowerShell Cmdlet 查看网络区域信息

通过使用 Windows PowerShell 和 **Get-CsNetworkRegion** cmdlet 可查看网络区域信息。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络区域信息

  - 若要查看有关所有网络区域的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsNetworkRegion
    
    这将返回与以下内容类似的信息：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

有关详细信息，请参阅 [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)  
[删除现有的网络区域](lync-server-2013-deleting-existing-network-regions.md)

