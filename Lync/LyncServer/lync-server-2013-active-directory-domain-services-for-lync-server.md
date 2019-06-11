---
title: 'Lync Server 2013: Lync Server 的 Active Directory 域服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 域服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-13_

Active Directory 域服务充当 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还用作构建 Microsoft Lync Server 2013 安全基础结构的基础。 本部分的目的是介绍 Lync Server 2013 如何使用 Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信环境。 有关 Active Directory 域服务的 Lync Server 扩展以及如何为 Active Directory 域服务准备环境的详细信息, 请参阅在部署中[为 Lync server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)文档. 有关 Windows Server 网络中 Active Directory 域服务的角色的详细信息, 请参阅你正在使用的操作系统版本的文档。

Lync Server 2013 使用 Active Directory 域服务存储:

  - 在目录林中运行 Lync Server 2013 的所有服务器都需要的全局设置。

  - 标识林中运行 Lync Server 2013 的所有服务器的角色的服务信息。

  - 一些用户设置。

<div>

## <a name="active-directory-infrastructure"></a>Active Directory 基础结构

Active Directory 的基础结构要求包括以下内容:

  - 域控制器的操作系统要求

  - 域和林的功能级别要求

  - 全局编录域要求

有关详细信息, 请参阅部署文档中[Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory 域服务准备

<div>


> [!NOTE]  
> 我们建议你将全局设置部署到配置容器, 而不是系统容器。 这不会增强安全性, 但可为某些 Active Directory 域服务拓扑带来可伸缩性改进。 如果从 Microsoft Office 通信服务器2007迁移并使用系统容器, 但计划使用配置容器, 则必须先移动系统容器中的设置, 然后再执行任何升级准备。 若要将系统容器设置迁移到配置容器, 请参阅 Office 通信服务器2007中的全局设置<A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>迁移工具。



</div>

部署 Lync Server 2013 时, 第一步是准备 Active Directory 域服务。 为 Lync Server 2013 准备 Active Directory 域服务包括以下三个步骤:

  - **准备架构**。 此任务将在 Active Directory 域服务中扩展架构, 以包括特定于 Lync Server 2013 的类和属性。 有关准备架构的详细信息, 请参阅部署文档中的[在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)。 有关详细信息, 请参阅[从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。

  - **准备林**。 此任务将在林根域中创建全局设置和对象, 以及控制访问这些设置和对象的通用服务和管理组。 有关准备林的详细信息, 请参阅部署文档中的[运行 Lync Server 2013 的林准备](lync-server-2013-running-forest-preparation.md)。

  - **准备域**。 此任务将必要的访问控制项 (Ace) 添加到通用组, 以便授予托管和管理域内用户的权限。 必须在要在其中部署运行 Lync Server 2013 的服务器以及 Lync Server 用户所驻留的任何域的所有域中完成此任务。 有关准备域的详细信息, 请参阅部署文档中的[运行 Lync Server 2013 的域准备](lync-server-2013-running-domain-preparation.md)。

有关准备 Active Directory 的完整过程以及执行每个步骤所需的权限和权限的概述, 请参阅部署文档中[Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="universal-groups"></a>通用组

在准备林期间, Lync Server 2013 在具有访问和管理全局设置和服务的权限的 Active Directory 域服务中创建各种通用组。 这些通用组包括：

  - **管理组**。 这些组定义了 Lync Server 网络的基本管理员角色。 在林准备期间, 这些管理员组将添加到 Lync Server 基础结构组。

  - **服务组**。 这些组是访问 Lync Server 提供的各种服务所需的服务帐户。

  - **基础结构组**。 这些组提供访问 Lync Server 基础结构的特定区域的权限。 这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。 在林的准备过程中，会将特定的服务组和管理组添加到适当的基础结构组。

有关在为 Lync Server 准备广告时创建的特定通用组以及添加到基础结构组的服务和管理组的详细信息, 请参阅[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)部署文档。

<div>


> [!NOTE]  
> Lync Server 2013 支持 Windows Server 2012 中的通用组, 适用于运行 Lync Server 2013 的服务器以及适用于域控制器的 Windows Server 2003 操作系统。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持, 与管理员委派结合使用, 简化了 Lync 服务器部署的管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。



</div>

</div>

<div>

## <a name="role-based-access-control"></a>基于角色的访问控制

除创建通用服务组和管理组以及将服务组和管理组添加到适当的通用组之外，林准备还创建基于角色的访问控制 (RBAC) 组。 有关林准备创建的特定 RBAC 组的详细信息, 请参阅部署文档中[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。 有关 RBAC 组的详细信息, 请参阅[Lync Server 2013 的基于角色的访问控制 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)。

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。 它在 Lync Server 使用的全局设置容器上创建特定的专用 Ace。 此容器仅由 Lync Server 使用, 并且位于配置容器或根域中的系统容器中, 具体取决于你存储全局设置的位置。

域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。

有关由林准备和域准备创建和添加的公共 Ace 的详细信息, 请参阅[Lync server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)以及部署中[由 lync server 2013 中的域准备进行的更改](lync-server-2013-changes-made-by-domain-preparation.md)文档.

组织通常会锁定 Active Directory 域服务 (AD DS) 以帮助降低安全风险。 但是, 锁定的活动目录环境可以限制 Lync Server 2013 所需的权限。 这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。 在锁定的活动目录环境中, 必须在需要它们的容器和 Ou 上手动设置权限。 有关详细信息, 请参阅在部署文档中的[Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

<div>

## <a name="server-information"></a>服务器信息

在激活期间, Lync Server 2013 将服务器信息发布到 Active Directory 域服务中的三个以下位置:

  - 每个 Active Directory 计算机对象上的服务连接点 (SCP), 对应于安装了 Lync Server 2013 的物理计算机。

  - 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。

  - 拓扑生成器中指定的受信任服务器。

</div>

<div>

## <a name="service-connection-points"></a>服务连接点

Active Directory 域服务中的每个 Lync Server 2013 对象都具有一个名为 RTC 服务的 SCP, 后者又包含许多属性, 这些属性标识每台计算机并指定它所提供的服务。 在这些 SCP 属性中，比较重要的 SCP 属性为 *serviceDNSName *、*serviceDNSNameType *、*serviceClassname * 和 *serviceBindingInformation *。 第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory 服务器对象

每个 Lync Server 2013 服务器角色都具有相应的 Active Directory 对象, 该对象的属性定义了该角色提供的服务。 此外, 在激活标准版服务器或创建企业版池时, Lync Server 2013 将在**msRTCSIP**容器中创建一个新的**msRTCSIP**对象。 **MsRTCSIP**类指定池的完全限定的域名 (FQDN), 以及池的前端和后端组件之间的关联。 (标准版服务器被视为一种逻辑池, 其前端和后端在一台计算机上 collocated。)

</div>

<div>

## <a name="trusted-servers"></a>受信任的服务器

在 Lync Server 2013 中, 受信任的服务器是运行拓扑生成器和发布拓扑时指定的服务器。 发布的拓扑（包括所有服务器信息）存储在中央管理存储中。 只有中央管理存储中定义的服务器是受信任的。 在 Lync Server 2013 中, 受信任的服务器是符合以下条件的服务器:

  - 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。

  - 服务器提供了来自受信任的 CA 的有效证书。 有关详细信息, 请参阅[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。

如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。此双重要求可防止未授权服务器可能通过尝试接管有效服务器的 FQDN 来发起攻击（虽然出现此情况的可能性不大）。

此外, 若要启用 Microsoft Office 通信服务器 2007 R2 和 Microsoft Office 通信服务器2007部署以与 Lync Server 2013 服务器通信, Lync Server 2013 将在林准备期间创建容器, 以保留列表以前版本的受信任服务器。 下表介绍为了与早期部署兼容而创建的容器。

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>受信任服务器列表及其 Active Directory 容器与以前版本的兼容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>受信任的服务器列表</th>
<th>Active Directory 容器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server 和企业版池前端服务器</p></td>
<td><p>RTC 服务/全局设置</p></td>
</tr>
<tr class="even">
<td><p>会议服务器</p></td>
<td><p>RTC 服务/受信任的 MCU</p></td>
</tr>
<tr class="odd">
<td><p>Web 组件服务器</p></td>
<td><p>RTC 服务/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）</p></td>
<td><p>RTC 服务/受信任的服务</p></td>
</tr>
<tr class="odd">
<td><p>代理服务器</p></td>
<td><p>Lync Server 2013 不支持代理服务器的向后兼容性</p></td>
</tr>
</tbody>
</table>


若要支持以前版本的受信任服务器, 必须运行最佳做法分析器工具。 有关运行最佳做法分析器的详细信息, 请[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)参阅。

</div>

</div>

<span> </span>

</div>

</div>

</div>

