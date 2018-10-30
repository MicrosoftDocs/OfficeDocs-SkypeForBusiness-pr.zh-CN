---
title: 查看有关设备更新规则的信息
TOCTitle: 查看有关设备更新规则的信息
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994077(v=OCS.15)
ms:contentKeyID: 52061140
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看有关设备更新规则的信息

 

_**上一次修改主题：** 2013-02-23_

查看有关已导入的设备更新规则的详细信息，包括更新适用于的设备的类型、型号和品牌；更新的版本和类型；更新的区域设置和池。信息可用于所有已导入的设备更新规则：等待批准、已部署（已批准）、已撤消（已恢复）的规则，以及已决定不使用（重置）的规则。可从 Lync Server 控制面板或 Windows PowerShell 中访问此信息。

> [!NOTE]  
> 有关如何导入、批准、重置、恢复以及删除规则的详细信息，请参阅<a href="lync-server-2013-device-update-rules.md">Lync Server 2013 中的设备更新规则</a>中所列的主题。


## 使用 Lync Server 控制面板查看设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备更新”导航按钮。已导入规则在“设备更新”页上列出。

## 使用 Windows PowerShell Cmdlet 查看设备更新规则

还可以使用 Windows PowerShell 和 **Get-CsDeviceUpdateRule** cmdlet 查看有关您的所有设备更新规则的详细信息。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。


## 查看您的所有设备更新规则

  - 以下命令返回有关配置为在组织中使用的所有设备更新规则的信息：
    
        Get-CsDeviceUpdateRule
    
    该命令为您的每个设备更新规则返回如下信息：
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## 查看特定 Web 服务器上的所有设备更新规则

  - 若要查看特定计算机上的设备更新规则，请使用 Filter 参数后跟服务器标识和通配符 (\*)。例如：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

有关详细信息，请参阅 [Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet 的帮助主题。

