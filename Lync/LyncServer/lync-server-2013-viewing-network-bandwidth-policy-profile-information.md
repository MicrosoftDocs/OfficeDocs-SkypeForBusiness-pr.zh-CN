---
title: 查看网络带宽策略配置文件信息
TOCTitle: 查看网络带宽策略配置文件信息
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49888669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络带宽策略配置文件信息

 

_**上一次修改主题：** 2013-02-23_

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。在 Microsoft Lync Server 2013 中，只能为音频和视频形式指定带宽限制。您可以设置总体带宽限制和会话限制。可以使用 Lync Server 控制面板创建、修改或删除这些策略的容器配置文件。每个带宽策略配置文件都可以与一个或多个网络站点相关联。使用下列过程可查看带宽策略配置文件。要创建或修改带宽策略配置文件，请参阅[创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

## 修改带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。

4.  在“带宽策略”页上，单击要修改的带宽策略配置文件。

5.  在“编辑”菜单上，单击“显示详细信息”。

## 通过使用 Lync Server PowerShell Cmdlet 查看网络带宽策略配置文件信息

还可以通过使用 Lync Server PowerShell 和 Get-CsNetworkBandwidthPolicyProfile cmdlet 查看网络带宽配置文件。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络带宽策略配置文件信息

  - 要查看有关所有网络带宽策略配置文件的信息，请在 Lync Server 命令行管理程序中输入下列命令，然后按 Enter：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    这将返回与以下类似的信息：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

有关详细信息，请参阅[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### 其他资源

[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)

