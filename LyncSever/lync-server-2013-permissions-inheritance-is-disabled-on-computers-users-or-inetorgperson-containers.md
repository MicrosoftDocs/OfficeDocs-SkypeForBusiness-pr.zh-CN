---
title: Lync Server 2013：权限继承在计算机、用户或 InetOrgPerson 容器上被禁用
TOCTitle: 权限继承在计算机、用户或 InetOrgPerson 容器上被禁用
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412970(v=OCS.15)
ms:contentKeyID: 49314155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中权限继承在计算机、用户或 InetOrgPerson 容器上被禁用

 

_**上一次修改主题：** 2014-12-19_

在锁定的 Active Directory 域服务 中，通常将用户对象和计算机对象放置在禁用了权限继承的特定组织单位 (OU) 中，以帮助确保管理委派的安全以及允许使用组策略对象 (GPO) 实施安全策略。

域准备和服务器激活过程中将设置 Lync Server 2013 所需的访问控制项 (ACE)。如果禁用了权限继承， Lync Server 安全组就无法继承这些 ACE。如果不继承这些权限， Lync Server 安全组就无法访问设置，并会产生以下两个问题：

  - 为了管理用户、InetOrgPersons 和联系人以及对服务器进行操作， Lync Server 安全组要求域准备过程对每个用户的属性集（实时通信 (RTC)、RTC 用户搜索和公用信息）设置 ACE。如果禁用了权限继承，安全组就不会继承这些 ACE，因此无法管理服务器或用户。

  - 为了发现服务器和池，运行 Lync Server 的服务器依赖于对计算机相关对象（包括 Microsoft 容器和服务器对象）的激活操作所设置的 ACE。如果禁用了权限继承，安全组、服务器和池将不会继承这些 ACE，因而也无法利用这些 ACE。

为了解决这些问题， Lync Server 提供了 **Grant-CsOuPermission** cmdlet。该 cmdlet 直接在指定的容器和组织单位以及容器或组织单位内的对象中设置所需的 Lync Server ACE。

## 在运行域准备之后为用户、InetOrgPerson 和联系人对象设置权限

在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中用户或 InetOrgPerson 对象的容器或组织单位设置必要的 ACE。在这种情况下，必须对禁用了其权限继承的容纳用户或 InetOrgPerson 对象的每个容器或 OU 运行 **Grant-CsOuPermission** cmdlet。如果拥有中央林拓扑，则还必须对容纳联系人对象的容器或 OU 执行此过程。有关中央林拓扑的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。ObjectType 参数指定对象类型。OU 参数指定组织单位。

此 cmdlet 会在指定的容器或 OU 上以及该容器内的用户或 InetOrgPerson 对象上直接添加所需的 ACE。

您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。如果在锁定的环境中还删除了经过身份验证的用户的 ACE，则必须向此帐户授予对目录林根级域中相关容器或 OU 的读取访问 ACE（如 [在 Lync Server 2013 中删除经过身份验证的用户的权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述），或使用 Enterprise Admins 组成员的帐户。

**为用户、InetOrgPerson 和联系人对象设置所需的 ACE**

1.  以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到加入域的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在日志文件中，在每项任务结束时查找“\<成功\>”执行结果，以确认设置了权限，然后关闭日志窗口。或者，可以运行以下命令确定是否设置了权限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"


## 在运行域准备之后为计算机对象设置权限

在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中计算机对象的容器或 OU 设置必要的 ACE。在这种情况下，必须对禁用了其权限继承的容纳运行 Lync Server 的计算机的每个容器或 OU 运行 **Grant-CsOuPermission** cmdlet。ObjectType 参数指定对象类型。

此过程将在指定的容器上直接添加所需的 ACE。

您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。如果还删除了经过身份验证的用户的 ACE，则必须向此帐户授予对目录林根级域中相关容器的读取访问 ACE（如 [在 Lync Server 2013 中删除经过身份验证的用户的权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述），或使用 Enterprise Admins 组成员的帐户。

**为计算机对象设置所需的 ACE**

1.  以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到域计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果不指定 Domain 参数，则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  在示例日志文件 C:\\Logs\\OUPermissions.xml 中，在每项任务结束时查找“\<成功\>”执行结果，并确认没有错误，然后关闭日志。您可以运行以下 cmdlet 来测试权限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    > [!NOTE]  
	> 请注意，如果在锁定的 Active Directory 环境中的目录林根级域上运行域准备，则 Lync Server 需要具有对 Active Directory 的“架构”和“配置”容器的访问权限。<br />
    > 如果从 AD DS 中的“架构”或“配置”容器中删除了经过身份验证的默认用户权限，则只允许 Schema Admins 组（适用于“架构”容器）或 Enterprise Admins 组（适用于“配置”容器）的成员访问给定的容器。由于 Setup.exe、 Lync Server 命令行管理程序 cmdlets 和 Lync Server 控制面板需要具有对这些容器的访问权限，因此除非运行安装的用户具有与 Schema Admins 和 Enterprise Admins 组成员身份等效的用户权限，否则管理工具的设置和安装将失败。<br />
    > 要解决此问题，必须向 RTCUniversalGlobalWriteGroup 组授予对“架构”和“配置”容器的读取和写入访问权限。
    



