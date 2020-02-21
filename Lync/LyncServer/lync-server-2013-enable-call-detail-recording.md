---
title: Lync Server 2013：启用呼叫详细记录
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
ms.openlocfilehash: 1d9227c1b3486ea20d6a1dc9c82311bfd17633bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a>在 Lync Server 2013 中启用呼叫详细信息记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。

使用以下过程为整个组织或组织中的每个站点启用 CDR。

<div>


> [!NOTE]  
> 为了启用 CDR，必须配置监控和监控数据库。 有关详细信息，请参阅<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监控</A>。



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>使用 Lync Server 控制面板启用 CDR

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“呼叫详细信息记录”****。

4.  在“呼叫详细信息记录”**** 页上，单击表中的相应站点，再单击“操作”****，然后单击“启用 CDR”****。
    
    <div>
    

    > [!NOTE]  
    > 默认情况下，CDR 处于启用状态。

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用 CDR

您可以使用 Windows PowerShell 和**set-cscdrconfiguration** CMDLET 启用 CDR。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>在单个位置启用 CDR

  - 若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>在单个位置禁用 CDR

  - 若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。 禁用 CDR 不会卸载监控。 它暂停了 CDR 数据的收集和存储。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用单个命令在多个位置启用 CDR

  - 此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

有关详细信息，请参阅[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划监视](lync-server-2013-planning-for-monitoring.md)  
[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

