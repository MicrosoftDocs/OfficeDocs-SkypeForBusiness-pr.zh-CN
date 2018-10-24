---
title: 启用用户体验质量
TOCTitle: 启用用户体验质量
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182583(v=OCS.15)
ms:contentKeyID: 49314218
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用用户体验质量

 

_**上一次修改主题：** 2013-02-23_

用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)。

使用以下过程为整个组织或组织中的每个站点启用 QoE。

> [!NOTE]  
> 为了启用 QoE，必须首先配置监控和监控后端数据库。有关详细信息，请参阅<a href="lync-server-2013-deploying-monitoring.md">部署监控</a>。



## 使用 Lync Server 控制面板启用 QoE

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4.  在“用户体验质量数据”页上，单击表中相应的集合，再单击“操作”，然后单击“启用 QoE”。

## 使用 Windows PowerShell Cmdlet 启用 QoE

可以使用 Windows PowerShell和 **Set-CsQoEConfiguration** cmdlet 启用 QoE。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 对单个位置启用 QoE

  - 要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

## 对单个位置禁用 QoE

  - 要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## 使用单个命令在多个位置启用 QoE

  - 以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

有关详细信息，请参阅 [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration)。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)  
[部署监控](lync-server-2013-deploying-monitoring.md)

