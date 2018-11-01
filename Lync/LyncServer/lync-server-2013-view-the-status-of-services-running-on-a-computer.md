---
title: 在 Lync Server 2013 中查看计算机上运行的服务的状态
TOCTitle: 在 Lync Server 2013 中查看计算机上运行的服务的状态
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182606(v=OCS.15)
ms:contentKeyID: 49314735
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看计算机上运行的服务的状态

 

_**上一次修改主题：** 2013-02-22_

可以使用 Lync Server 2013 控制面板查看 Lync Server 拓扑中特定计算机上运行的所有服务并查看每种服务的状态。

## 查看计算机上运行的服务的状态

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”。

4.  在“状态”页上，根据需要对列表进行分类或搜索以查找您感兴趣的计算机，然后单击该计算机的名称。

5.  执行下列任意操作：
    
      - 要查看计算机上运行的服务的最新状态，请单击“获取服务状态”。
    
      - 要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”，然后单击“关闭”返回到列表。

## 通过使用 Lync Server 命令行管理程序 Cmdlet 查看服务状态

还可以通过使用 Lync Server 命令行管理程序和 **Get-CsWindowsService** cmdlet 查看服务状态。可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看服务状态

  - 要在计算机上查看服务状态，在 Lync Server 命令行管理程序中键入类似下列命令，然后按 Enter 键：
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    此命令会返回类似下列信息：
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

有关详细信息，请参阅[Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

