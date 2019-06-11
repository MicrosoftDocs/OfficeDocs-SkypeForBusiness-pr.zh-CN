---
title: Lync Server 2013：权限继承在计算机、用户或 InetOrgPerson 容器上被禁用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013 中权限继承在计算机、用户或 InetOrgPerson 容器上被禁用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-12-19_

在锁定的 Active Directory 域服务中, 用户和计算机对象通常位于特定的组织单位 (Ou) 中, 并且禁用权限继承以帮助保护管理委派和启用组策略对象 (Gpo) 的使用。强制实施安全策略。

域准备和服务器激活设置 Lync Server 2013 所需的访问控制条目 (Ace)。 禁用权限继承后, Lync 服务器安全组无法继承这些 Ace。 如果这些权限不是继承的, 则 Lync Server 安全组无法访问设置, 并且出现以下两个问题:

  - 若要管理用户、InetOrgPersons 和联系人以及操作服务器, Lync Server 安全组需要由每个用户的属性集、实时通信 (RTC)、RTC 用户搜索和公共信息的域准备过程设置的 Ace。. 当禁用权限继承时, 安全组不会继承这些 Ace, 也不能管理服务器或用户。

  - 若要发现服务器和池, 运行 Lync Server 的服务器依赖于计算机相关对象 (包括 Microsoft 容器和服务器对象) 上的激活设置的 Ace。 当禁用权限继承时, 安全组、服务器和池不会继承这些 Ace, 也不能利用这些 Ace。

为了解决这些问题, Lync Server 提供了**CsOuPermission** cmdlet。 此 cmdlet 直接在指定的容器、组织单位和容器或组织单位中的对象上设置所需的 Lync Server Ace。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>在运行域准备后设置用户、InetOrgPerson 和联系人对象的权限

在禁用了权限继承的已锁定的活动目录环境中, 域准备不会在域中保存用户或 InetOrgPerson 对象的容器或组织单元上设置必需的 Ace。 在这种情况下, 你必须在具有禁用权限继承的用户或 InetOrgPerson 对象的每个容器或 OU 上运行**CsOuPermission** cmdlet。 如果您有一个中央林拓扑, 则还必须对持有联系人对象的容器或 Ou 执行此过程。 有关中央林拓扑的详细信息, 请参阅支持文档中的[Lync Server 2013 中支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。 ObjectType 参数指定对象类型。 OU 参数指定组织单位。

此 cmdlet 直接在指定的容器或容器中的用户或 InetOrgPerson 对象上添加所需的 Ace。 如果执行此命令的 OU 具有包含用户或 InetOrgPerson 对象的子 Ou, 则不会对这些对象应用权限。 你将需要单独对每个子 OU 运行该命令。 这是 Lync 托管部署的常见方案, 例如父 OU = OCS 租户、DC = CONTOSO、DC = 本地和子 OU = Tenant1, OU = local 租户, DC = CONTOSO, DC = LOCAL。

你需要与域管理员组成员身份等效的用户权限才能运行此 cmdlet。 如果已在锁定环境中删除了经过身份验证的用户 Ace, 则必须按照在[Lync 中删除的已验证用户权限中所述, 在林根域中的相关容器或 ou 上授予此帐户读取访问 ace服务器 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)或使用属于企业管理员组成员的帐户。

**为用户、InetOrgPerson 和联系人对象设置所需的 Ace**

1.  使用域管理员组的成员或具有同等用户权限的帐户登录加入域的计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 参数, 则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在日志文件中, 查找每个任务末尾的** \<成功\> **执行结果以验证是否设置了权限, 然后关闭 "日志" 窗口。 或者, 你可以运行以下命令来确定是否已设置权限:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>在运行域准备后设置计算机对象的权限

在禁用了权限继承的锁定的活动目录环境中, 域准备不会在包含域中的计算机对象的容器或 Ou 上设置必要的 Ace。 在这种情况下, 你必须在具有禁用了权限继承的运行 Lync Server 的计算机的每个容器或 OU 上运行**CsOuPermission** cmdlet。 ObjectType 参数指定对象类型。

此过程直接在指定的容器上添加所需的 Ace。

你需要与域管理员组成员身份等效的用户权限才能运行此 cmdlet。 如果已删除经过身份验证的用户 Ace, 则必须按照在[Lync Server 2013 中删除的身份验证用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述, 在林根域的相关容器上授予此帐户读取访问 ace 或使用一个帐户企业管理员组的成员。

**为计算机对象设置所需的 Ace**

1.  使用域管理员组的成员或具有同等用户权限的帐户登录到域计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果不指定 Domain 参数, 则默认值为本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  在示例日志文件 C:\\.log\\OUPermissions 中, 你将在每个任务的结尾处查找** \<成功\> **执行结果并验证没有错误, 然后关闭日志。 你可以运行以下 cmdlet 来测试权限:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 如果在锁定的活动目录环境中对林根域运行域准备, 请注意 Lync 服务器需要访问 Active Directory 架构和配置容器。<BR>如果从 AD&nbsp;DS 中的架构或配置容器中删除默认的经过身份验证的用户权限, 则仅允许架构管理员组 (针对架构容器) 或企业管理员组 (对于配置容器) 的成员访问给定容器。 由于 setup.exe、Lync Server Management Shell cmdlet 和 Lync Server 控制面板需要访问这些容器, 因此除非运行安装的用户具有等效于架构的用户权限, 否则管理工具的安装将失败。管理员和企业管理员组成员身份。<BR>若要解决此问题, 必须授予 RTCUniversalGlobalWriteGroup 组对架构和配置容器的读取、写入访问权限。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

