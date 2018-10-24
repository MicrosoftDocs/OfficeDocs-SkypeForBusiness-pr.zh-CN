---
title: 启用呼叫详细信息记录
TOCTitle: 启用呼叫详细信息记录
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520980(v=OCS.15)
ms:contentKeyID: 49312554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用呼叫详细信息记录

 

_**上一次修改主题：** 2013-02-23_

呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。

使用以下过程为整个组织或组织中的每个站点启用 CDR。

> [!NOTE]  
> 为了启用 CDR，必须配置监控和监控数据库。有关详细信息，请参阅<a href="lync-server-2013-deploying-monitoring.md">部署监控</a>。



## 使用 Lync Server 控制面板启用 CDR

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。

4.  在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“操作”，然后单击“启用 CDR”。
    
    > [!NOTE]  
    > 默认情况下，CDR 处于启用状态。
    


## 使用 Lync Server 命令行管理程序 cmdlet 启用 CDR

您还可以使用 Windows PowerShell 和 **Set-CsCdrConfiguration** cmdlet 启用 CDR。可从 Lync Server 2013 命令行管理程序运行此 cmdlet，也可以从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 在单个位置启用 CDR

  - 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## 在单个位置禁用 CDR

  - 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。这不会卸载监控，而只会暂停 CDR 数据的收集和存储。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## 使用单个命令在多个位置启用 CDR

  - 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

有关详细信息，请参阅 [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)  
[部署监控](lync-server-2013-deploying-monitoring.md)

