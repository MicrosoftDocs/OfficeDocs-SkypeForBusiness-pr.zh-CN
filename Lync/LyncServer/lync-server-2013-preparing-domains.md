---
title: Lync Server 2013：准备域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1f5693a14084627d20ae66fa6ec85f6b6c6c6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>为 Lync Server 2013 准备域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-29_

域准备是为 Lync Server 2013 准备 Active Directory 域服务的最后一步。 域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。 域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。

可以在要部署 Lync Server 的域中的任何计算机上运行域准备。 你必须准备将托管 Lync Server 或用户的每个域。

如果已禁用权限继承或已禁用身份验证用户权限在你的组织中被禁用, 则必须在域准备期间执行其他步骤。 有关详细信息, 请参阅[在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

如果您的组织使用组织单位 (OU) 而不是三个内置容器 (即用户、计算机和域控制器), 则必须为 "已验证用户" 组授予对 Ou 的读取访问权限。 域准备需要对容器的读取访问权限。 如果 "经过身份验证的用户组" 对 OU 没有 "读取" 访问权限, 请运行**CsOuPermission** cmdlet, 如下代码示例所示, 为每个 OU 授予读取权限。

   ```
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

有关**CsOuPermission** cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档。

<div class="">


> [!TIP]  
> 有关在域根和 "用户"、"计算机" 和 "域控制器" 容器中创建的 Ace 的详细信息, 请参阅<A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的域准备所做的更改</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)

  - [使用 Cmdlet 为 Lync Server 2013 反向执行域准备](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

