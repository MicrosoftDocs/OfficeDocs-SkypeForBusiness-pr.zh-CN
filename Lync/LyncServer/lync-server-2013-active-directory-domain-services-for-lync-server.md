---
title: Lync Server 2013 的 Active Directory 域服务
TOCTitle: Lync Server 2013 的 Active Directory 域服务
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59679360
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 Active Directory 域服务

 

_**上一次修改主题：** 2016-12-08_

Active Directory 域服务 充当 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。Active Directory 域服务 还可用作构建 Microsoft Lync Server 2013 安全基础结构的基础。本节旨在介绍 Lync Server 2013 如何使用 Active Directory 域服务 为 IM、Web 会议、媒体和语音创建可信的环境。有关 Active Directory 域服务 的 Lync Server 扩展和针对 Active Directory 域服务 准备您的环境的详细信息，请参阅部署文档中的[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。有关 Windows Server 中 Active Directory 域服务 的角色的详细信息，请参阅文档了解您所使用的操作系统的版本。

Lync Server 2013 使用 Active Directory 域服务 存储：

  - 林中所有运行 Lync Server 2013 的服务器所需的全局设置。

  - 标识林中所有运行 Lync Server 2013 的服务器的角色的服务信息。

  - 一些用户设置。

## Active Directory 基础结构

Active Directory 的基础结构要求包括以下各项：

  - 域控制器的操作系统要求

  - 域和林的功能级别要求

  - 全局编录域要求

有关详细信息，请参阅部署文档中的 [Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md)。

## Active Directory 域服务 准备

> [!NOTE]  
> 建议您对“配置”容器而非“系统”容器部署全局设置。这不会增强安全性，但是可提高一些 Active Directory 域服务 拓扑的可伸缩性。如果从 Microsoft Office Communications Server 2007 进行迁移并且使用的是“系统”容器（而计划使用的是“配置”容器），则必须先移动“系统”容器中的设置，然后再进行任何升级准备。若要将“系统”容器设置迁移到“配置”容器中，请参阅 Office Communications Server 2007 全局设置迁移工具，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</a>。



在部署 Lync Server 2013 时，第一个步骤是准备 Active Directory 域服务。为 Lync Server 2013 准备 Active Directory 域服务 包含以下三个步骤：

  - **准备架构**。此任务将扩展 Active Directory 域服务 中的架构，以包括特定于 Lync Server 2013 的类和属性。有关准备架构的详细信息，请参阅部署文档中的[在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)。有关详细信息，请参阅[从 Office Communications Server 2007 R2 迁移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。

  - **准备林**。此任务将在林根级域中创建全局设置和对象，并创建用于管理针对这些设置和对象的访问的通用服务和管理组。有关准备林的详细信息，请参阅部署文档中的[为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)。

  - **准备域**。此任务会向通用组添加必要的访问控制项 (ACE)，这些访问控制项可授予承载和管理域中用户的权限。必须在要部署运行 Lync Server 2013 的服务器的所有域中以及 Lync Server 用户所在的所有域中完成此任务。有关准备域的详细信息，请参阅部署文档中的[为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)。

有关准备 Active Directory 的完整过程和执行每个步骤所需的权限的概述，请参阅部署文档中的 [Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md)。

## 通用组

在准备林的过程中，Lync Server 2013 会在 Active Directory 域服务 内创建各种通用组，这些通用组有权访问和管理全局设置和服务。这些通用组包括：

  - **管理组**。这些组将定义 Lync Server 网络的基本管理员角色。在林的准备过程中，这些管理员组将添加到 Lync Server 基础结构组中。

  - **服务组**。这些组是访问 Lync Server 提供的各种服务所需的服务帐户。

  - **基础结构组**。这些组负责提供访问 Lync Server 基础结构的特定区域的权限。这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。在林的准备过程中，会将特定的服务组和管理组添加到适当的基础结构组。

有关为 Lync Server 准备 AD 时创建的特定通用组以及添加到基础结构组的服务组和管理组的详细信息，请参阅部署文档中的[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。

> [!NOTE]  
> Lync Server 2013 在 Windows Server 2012 中支持运行 Lync Server 2013 的服务器的通用组，而且在 Windows Server 2003 操作系统中支持域控制器的通用组。通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。通用组支持与管理员委派相结合，可简化对 Lync Server 部署的管理。例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。



## 基于角色的访问控制

除创建通用服务组和管理组以及将服务组和管理组添加到适当的通用组之外，林准备还创建基于角色的访问控制 (RBAC) 组。有关林准备所创建的特定 RBAC 组的详细信息，请参阅部署文档中的[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。有关 RBAC 组的详细信息，请参阅[Lync Server 2013 的基于角色的访问控制 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)。

## 访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。它对 Lync Server 所使用的全局设置容器创建特定的专用 ACE。此容器仅供 Lync Server 使用，且位于根域的“配置”容器或“系统”容器中（具体取决于存储全局设置的位置）。

域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。

有关林准备和域准备所创建和添加的公共 ACE 的详细信息，请参阅部署文档中的[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)和[Lync Server 2013 中的域准备所做的更改](lync-server-2013-changes-made-by-domain-preparation.md)。

组织通常锁定 Active Directory 域服务 (AD DS) 以帮助降低安全风险。但是，锁定的 Active Directory 环境会限制 Lync Server 2013 所需的权限。这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。在锁定的 Active Directory 环境中，必须在需要权限的容器和 OU 上手动设置权限。有关详细信息，请参阅部署文档中的[在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

## 服务器信息

在激活过程中，Lync Server 2013 会将服务器信息发布到 Active Directory 域服务 中的以下三个位置：

  - 与安装 Lync Server 2013 的物理计算机对应的每个 Active Directory 计算机对象上的服务连接点 (SCP)。

  - 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。

  - 拓扑生成器 中指定的受信任服务器。

## 服务连接点

Active Directory 域服务 中的每个 Lync Server 2013 对象都具有一个称作“RTC 服务”的 SCP，SCP 包含很多可用于标识每台计算机并指定其提供的服务的属性。在这些 SCP 属性中，比较重要的 SCP 属性为 *serviceDNSName*、*serviceDNSNameType*、*serviceClassname* 和 *serviceBindingInformation*。第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。

## Active Directory 服务器对象

每个 Lync Server 2013 服务器角色都包含一个对应的 Active Directory 对象，该对象的属性将定义此角色所提供的服务。同样，在激活 Standard Edition Server 或创建 企业版 池时，Lync Server 2013 会在 **msRTCSIP-Pools** 容器中创建新的 **msRTCSIP-Pool** 对象。**msRTCSIP-Pool** 类指定池的完全限定的域名 (FQDN)，以及池的前端组件和后端组件之间的关联。（Standard Edition Server 将被视为一个逻辑池，其前端组件和后端组件并置在同一台计算机上。）

## 受信任的服务器

在 Lync Server 2013 中，受信任服务器是指运行 拓扑生成器 并发布拓扑时指定的服务器。发布的拓扑（包括所有服务器信息）存储在中央管理存储中。只有中央管理存储中定义的服务器是受信任的。在 Lync Server 2013 中，受信任的服务器是指满足以下条件的服务器：

  - 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。

  - 服务器提供了来自受信任的 CA 的有效证书。有关详细信息，请参阅[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。

如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。此双重要求可防止未授权服务器可能通过尝试接管有效服务器的 FQDN 来发起攻击（虽然出现此情况的可能性不大）。

此外，为启用 Microsoft Office Communications Server 2007 R2 和 Microsoft Office Communications Server 2007 部署以与 Lync Server 2013 服务器进行通信，Lync Server 2013 会在林准备过程中创建多个容器以便保存早期版本的受信任服务器的列表。下表介绍为了与早期部署兼容而创建的容器。

### 与早期版本兼容的受信任的服务器列表及其 Active Directory 容器

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
<td><p>Lync Server 2013 不支持代理服务器的向后兼容</p></td>
</tr>
</tbody>
</table>


为支持早期版本的受信任服务器，必须运行最佳做法分析器工具。有关运行最佳做法分析器的详细信息，请参阅 [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)。

