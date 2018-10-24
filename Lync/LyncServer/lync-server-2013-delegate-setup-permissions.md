---
title: Lync Server 2013：委派安装权限
TOCTitle: 委派安装权限
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412735(v=OCS.15)
ms:contentKeyID: 49313755
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的委派安装权限

 

_**上一次修改主题：** 2014-02-05_

如果不希望向部署 Lync Server 2013 的用户或组授予 Domain Admins 组的成员身份，则可使 RTCUniversalServerAdmins 组的成员能够在运行 Lync Server 2013 的服务器上运行 **Enable-CsTopology**  Windows PowerShell cmdlet。默认情况下，RTCUniversalServerAdmins 组的成员无法运行此 cmdlet。您可以授予在运行 Lync Server 的服务器上运行 **Enable-CsTopology** 的管理员权利和权限，方法是使用 **Grant-CsSetupPermission** cmdlet 并指定运行 Lync Server 2013 的服务器的计算机对象所在的组织单位 (OU)。

安装 Lync Server 时所执行的域准备工作不会自动添加可使 RTCUniversalServerAdmins 组的成员运行 Enable-CsTopology cmdlet 的权限。这意味着，默认情况下，只有域管理员才能启用拓扑。要授予 RTCUniversalServerAdmins 组的成员启用拓扑的权限，必须运行 Grant-CsSetupPermissions cmdlet。此外，您将需要针对托管运行 Lync Server 的计算机的每个 Active Directory 容器运行此 cmdlet。

请记住，此 cmdlet 仅向 RTCUniversalServerAdmins 组授予权限；此 cmdlet 不能用于向其他安全组或向单个用户授予权限。

> [!NOTE]  
> <strong>Enable-CsTopology</strong> 是允许 RTCUniversalServerAdmins 组成员设置和部署 Lync Server 2013 的关键 cmdlet。



## 向 RTCUniversalServerAdmins 组添加运行 Enable-CsTopology 的权限

1.  以委派用户将在其上运行 **Enable-CsTopology** 的域的 Domain Admins 组成员身份登录服务器。

2.  打开 Lync Server 2013 命令行管理程序。 Lync Server 2013 命令行管理程序会自动在每台 前端服务器或已安装 Lync Server 2013 管理工具的任何计算机上安装。有关 Lync Server 2013 命令行管理程序的详细信息，请参阅操作文档中的 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)。

3.  从 Lync Server 2013 命令行管理程序中运行以下 cmdlet：
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    > [!NOTE]  
    > 如果 OU 不是最高级别，则必须提供完整的域名。
    
    
    在以下示例中，OU 是位于 contoso.com 域中的“Lync Servers”。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

