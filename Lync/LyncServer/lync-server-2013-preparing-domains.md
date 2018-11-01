---
title: Lync Server 2013：准备域
TOCTitle: 准备域
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398721(v=OCS.15)
ms:contentKeyID: 49313565
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 准备域

 

_**上一次修改主题：** 2012-10-29_

域准备是为 Lync Server 2013 准备 Active Directory 域服务 的最后一步。域准备步骤中将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程中将在域根和以下三个内置容器中创建 ACE：用户、计算机和域控制器。

可以在要部署 Lync Server 的域中的任何计算机上运行域准备。对每个要承载 Lync Server 或用户的域都必须进行准备。

如果在组织中禁用了权限继承，或者禁用了经过身份验证的用户权限，则在域准备期间还必须执行其他步骤。有关详细信息，请参阅 [在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

如果组织使用组织单位 (OU) 代替三个内置容器（即“用户”、“计算机”和“域控制器”），则必须为 Authenticated Users 组授予 OU 的读取权限。域准备需要具有容器的读取权限。如果 Authenticated Users 组没有对 OU 的读取权限，请按照以下代码示例中所示运行 **Grant-CsOuPermission** cmdlet，授予对每个 OU 的读取权限。

    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 

   &nbsp;

    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"

有关 **Grant-CsOuPermission** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

> [!TIP]
> 有关在域根上和在“用户”、“计算机”和“域控制器”这三个容器中创建的 ACE 的详细信息，请参阅<a href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的域准备所做的更改</a>。


## 本部分内容

  - [为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)

  - [使用 Cmdlet 为 Lync Server 2013 反向执行域准备](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

