---
title: Lync Server 2013：启用呼叫详细信息录制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b033827600fc962ab5ea9df5c8848ed1533c75e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a>在 Lync Server 2013 中启用呼叫详细记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。

使用以下过程为整个组织或组织中的每个站点启用 CDR。

<div>


> [!NOTE]  
> 为了启用 CDR，必须配置监控和监控数据库。 有关详细信息，请参阅<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监视</A>。



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>使用 Lync Server "控制面板" 启用 CDR

1.  从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**监控和存档**”，然后单击“**呼叫详细信息记录**”。

4.  在“**呼叫详细信息记录**”页上，单击表中的相应站点，再单击“**操作**”，然后单击“**启用 CDR**”。
    
    <div>
    

    > [!NOTE]  
    > 默认情况下，CDR 处于启用状态。

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用 CDR

你可以使用 Windows PowerShell 和**CsCdrConfiguration** CMDLET 启用 CDR。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>在单个位置启用 CDR

  - 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>在单个位置禁用 CDR

  - 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。禁用 CDR 不会卸载监控。而只会暂停 CDR 数据的收集和存储。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用单个命令在多个位置启用 CDR

  - 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

有关详细信息，请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)  
[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

