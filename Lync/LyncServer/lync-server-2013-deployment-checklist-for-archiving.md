---
title: Lync Server 2013：存档的部署清单
description: Lync Server 2013：存档的部署清单。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557708"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中存档的部署清单

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

存档将自动安装在 Lync Server 2013 部署中的每台前端服务器上，但您仍需要对其进行设置，然后才能使用它。 本节中总结了设置存档所需的步骤，这些步骤构成了存档的部署。

<div>

## <a name="deployment-sequence"></a>部署顺序

设置存档的方式取决于您所选的存储选项：

  - 如果对部署中的所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Lync Server 2013 存档策略。 相反，请将 Exchange In-Place 保留策略配置为支持驻留在 Exchange 2013 上的用户的存档，并将其邮箱置于 In-Place 保留状态。 有关配置这些策略的详细信息，请参阅 Exchange 2013 产品文档。

  - 如果您不在部署中对所有用户使用 Microsoft Exchange 集成，则需要将 Lync Server 存档数据库添加 (SQL Server 数据库) 到拓扑，然后发布该数据库，并为用户配置策略和设置，然后才能存档这些用户的数据。 可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。

如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。

<div>


> [!IMPORTANT]  
> 如果出于合规性原因，存档在您的组织中至关重要，请务必部署存档、在适当的级别配置策略和其他选项，并为所有适当的用户启用该策略，然后再为这些用户启用 Lync Server 2013。



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>存档部署过程

下表提供在现有拓扑中部署存档所需步骤的概述。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>角色和组成员身份</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安装必备软硬件</strong></p></td>
<td><ul>
<li><p>若要使用 Microsoft Exchange 集成 (使用 Exchange 2013 存档) 的部分或所有用户的存储，需要一个现有的 Exchange 2013 部署。</p></li>
<li><p>若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。</p></li>
</ul>
<div>

> [!NOTE]  
> 存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。


</div></td>
<td><p>属于本地 Administrators 组成员的域用户。</p></td>
<td><p>可支持性文档中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a>。</p>
<p>可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a>。</p>
<p>在规划文档中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</p>
<p>部署文档中的在<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 中设置用于存档的系统和基础结构</a>。</p>
<p>可支持性文档中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>创建适当的内部拓扑，以支持仅当不为部署中的所有用户使用 Microsoft Exchange 集成时 (存档) </strong></p></td>
<td><p>运行拓扑生成器以将 Lync Server 2013 存档数据库 (SQL Server 数据库) 到拓扑，然后发布拓扑。</p></td>
<td><p>要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。</p>
<p>若要发布拓扑，该帐户是 domain admins 组和 RTCUniversalServerAdmins 组的成员，并且具有对用于 Lync Server 2013 文件 (存储的文件共享上的完全控制权限 (读/写/修改) ，以便拓扑生成器可以配置所需的 Dacl) 。</p></td>
<td><p>在部署文档中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">将存档数据库添加到现有 Lync Server 2013 部署</a>中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>仅在使用 Microsoft Exchange 集成时配置服务器到服务器身份验证 () </strong></p></td>
<td><p>将服务器配置为在 Lync Server 2013 与 Exchange 2013 之间启用身份验证。 我们建议在启用存档之前，运行 <strong>CsExchangeStorageConnectivity testuser_sipUri – Folder 转储程序</strong> 以验证 Exchange 存档存储连接。</p></td>
<td><p>具有用于管理服务器上的证书的相应权限的帐户。</p></td>
<td><p>在部署文档或操作文档中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>配置存档策略和配置</strong></p></td>
<td><p>配置存档，包括是否使用 Microsoft Exchange 集成、全局策略和任何站点和用户策略 (不将 Microsoft Exchange 集成用于所有数据存储) ，以及特定的存档选项（如关键模式和数据导出和清除）。</p>
<p>如果使用 Microsoft Exchange 集成，请根据需要配置 Exchange In-Place 保留策略。</p></td>
<td><p>RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。</p></td>
<td><p>在部署文档中<a href="lync-server-2013-configuring-support-for-archiving.md">配置对 Lync Server 2013 存档的支持</a>。</p>
<p>如果使用 Microsoft Exchange 集成) ，则为 Exchange 产品文档 (。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>在不同林中部署 Lync Server 和 Microsoft Exchange

如果 Microsoft Exchange Server 未部署在与 Lync Server 相同的林中，则必须确保将以下 Exchange Active Directory 属性同步到部署 Lync Server 的林：

1.  msExchUserHoldPolicies

2.  proxyAddresses

这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。

</div>

</div>

<span> </span>

</div>

</div>

</div>

