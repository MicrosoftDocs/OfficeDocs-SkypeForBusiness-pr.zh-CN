---
title: Lync Server 2013：权限继承在计算机、用户或 InetOrgPerson 容器上被禁用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>在 Lync Server 2013 中的计算机、用户或 InetOrgPerson 容器上禁用权限继承

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-19_

在锁定的 Active Directory 域服务中，用户和计算机对象通常放在特定的组织单位（Ou）中，并禁用权限继承，以帮助保护管理委派和启用组策略对象（Gpo）的使用强制实施安全策略。

域准备和服务器激活设置 Lync Server 2013 所需的访问控制项（Ace）。 禁用权限继承后，Lync Server 安全组将无法继承这些 Ace。 如果不继承这些权限，Lync Server 安全组将无法访问设置，并且会出现以下两个问题：

  - 若要管理用户、InetOrgPersons 和联系人以及操作服务器，Lync Server 安全组需要对每个用户的属性集、实时通信（RTC）、RTC 用户搜索和公共信息进行域准备过程设置的 Ace. 如果禁用了权限继承，安全组就不会继承这些 ACE，因此无法管理服务器或用户。

  - 若要发现服务器和池，运行 Lync Server 的服务器依赖于在与计算机相关的对象（包括 Microsoft 容器和服务器对象）上激活时设置的 Ace。 如果禁用了权限继承，安全组、服务器和池将不会继承这些 ACE，因而也无法利用这些 ACE。

为解决这些问题，Lync Server 提供了**CsOuPermission** cmdlet。 此 cmdlet 直接在指定的容器和组织单位以及容器或组织单位中的对象上设置所需的 Lync Server Ace。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>在运行域准备之后为用户、InetOrgPerson 和联系人对象设置权限

在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中用户或 InetOrgPerson 对象的容器或组织单位设置必要的 ACE。 在这种情况下，必须对禁用了其权限继承的容纳用户或 InetOrgPerson 对象的每个容器或 OU 运行 **Grant-CsOuPermission** cmdlet。 如果拥有中央林拓扑，则还必须对容纳联系人对象的容器或 OU 执行此过程。 有关中央林拓扑的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的受支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。 ObjectType 参数指定对象类型。 OU 参数指定组织单位。

此 cmdlet 会在指定的容器或 OU 上以及该容器内的用户或 InetOrgPerson 对象上直接添加所需的 ACE。 如果执行此命令的 OU 具有包含 User 或 InetOrgPerson 对象的子 Ou，则不会对这些对象应用这些权限。 您需要分别在每个子 OU 上运行此命令。 这是 Lync 托管部署的常见方案，例如父 OU = OCS 租户、DC = CONTOSO、DC = 本地和子 OU = Tenant1、OU = OCS 租户、DC = CONTOSO、DC = LOCAL。

您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。 如果已在锁定环境中删除经过身份验证的用户 Ace，则必须在林根域的相关容器或 Ou 中授予此帐户读取访问 Ace，如在[Lync Server 2013 中删除了已验证用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述，或使用的帐户是 Enterprise Admins 组的成员。

**为用户、InetOrgPerson 和联系人对象设置所需的 ACE**

1.  以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到加入域的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数，则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在日志文件中，在每个任务的末尾查找 " ** \<成功\> **执行" 结果以验证是否设置了权限，然后关闭 "日志" 窗口。 或者，可以运行以下命令确定是否设置了权限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>在运行域准备之后为计算机对象设置权限

在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中计算机对象的容器或 OU 设置必要的 ACE。 在这种情况下，您必须在运行了禁用了权限继承的运行 Lync Server 的计算机的每个容器或 OU 上运行**CsOuPermission** cmdlet。 ObjectType 参数指定对象类型。

此过程将在指定的容器上直接添加所需的 ACE。

您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。 如果已删除经过身份验证的用户 Ace，则必须在林根域的相关容器上授予此帐户读取访问 Ace，如在[Lync Server 2013 中删除了已验证用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述，或使用的帐户是 Enterprise Admins 组的成员。

**为计算机对象设置所需的 ACE**

1.  以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到域计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果不指定 Domain 参数，则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  在示例日志文件 C：\\log\\OUPermissions 中，您将在每个任务的结尾处查找** \<成功\> **执行结果，并验证没有任何错误，然后关闭该日志。 您可以运行以下 cmdlet 来测试权限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 如果在锁定的 Active Directory 环境中对林根域运行域准备，请注意，Lync Server 需要访问 Active Directory 架构和配置容器。<BR>如果从 AD&nbsp;DS 中的架构或配置容器中删除了默认的经过身份验证的用户权限，则仅允许架构管理员组（针对架构容器）或 Enterprise admins 组（对于配置容器）的成员访问给定容器。 由于 setup.exe、Lync Server 命令行管理程序 cmdlet 和 Lync Server 控制面板需要访问这些容器，因此，除非运行安装的用户具有与架构等效的用户权限，否则管理工具的安装将会失败。管理员和企业管理员组成员身份。<BR>要解决此问题，必须向 RTCUniversalGlobalWriteGroup 组授予对“架构”和“配置”容器的读取和写入访问权限。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

