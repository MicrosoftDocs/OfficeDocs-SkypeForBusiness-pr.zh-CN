---
title: Lync Server 2013：查看计算机上运行的服务的状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea9c30dc8a02088c0a02baa9c6d877131360df3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>在 Lync Server 2013 中查看计算机上运行的服务的状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

您可以使用 Lync Server 2013 控制面板查看在 Lync Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>查看计算机上运行的服务的状态

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“拓扑”****。

4.  在“状态”**** 页上，根据需要对列表进行分类或搜索以查找您感兴趣的计算机，然后单击该计算机的名称。

5.  执行下列任意操作：
    
      - 要查看计算机上运行的服务的最新状态，请单击“获取服务状态”****。
    
      - 要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”****，然后单击“关闭”**** 返回到列表。

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看服务状态

您还可以使用 Windows PowerShell 和**start-cswindowsservice** cmdlet 查看服务状态。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-service-status"></a>查看服务状态

  - 若要在计算机上查看服务状态，请在 Lync Server 命令行管理程序中键入类似于以下的命令，然后按 Enter：
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    此命令返回与以下内容类似的信息：
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

有关详细信息，请参阅[start-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

