---
title: Lync Server 2013：准备域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506939"
---
# <a name="preparing-domains-for-lync-server-2013"></a>准备 Lync Server 2013 的域

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

准备 Active Directory 域服务以获取 Lync Server 2013 的最后一个步骤是 "域准备"。 域准备步骤中将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。 域准备过程中将在域根和以下三个内置容器中创建 ACE：用户、计算机和域控制器。

您可以在要部署 Lync Server 的域中的任何计算机上运行域准备工作。 您必须准备将承载 Lync Server 或用户的每个域。

如果在组织中禁用了权限继承，或者禁用了经过身份验证的用户权限，则在域准备期间还必须执行其他步骤。 有关详细信息，请参阅 [在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

如果组织使用组织单位 (OU) 代替三个内置容器（即“用户”、“计算机”和“域控制器”），则必须为 Authenticated Users 组授予 OU 的读取权限。 域准备需要具有容器的读取权限。 如果 Authenticated Users 组没有对 OU 的读取权限，请按照以下代码示例中所示运行 **Grant-CsOuPermission** cmdlet，授予对每个 OU 的读取权限。

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

有关 CsOuPermission cmdlet 的详细信息，请参阅 Lync Server 命令行管理 **程序** 文档。

<div class="">


> [!TIP]  
> 有关在域根和用户、计算机和域控制器容器中创建的 Ace 的详细信息，请参阅 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的域准备所做的更改</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)

  - [使用 cmdlet 对 Lync Server 2013 执行反向域准备](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

