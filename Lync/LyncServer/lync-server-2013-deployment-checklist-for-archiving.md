---
title: Lync Server 2013：存档的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中存档的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

存档将自动安装在 Lync Server 2013 部署中的每台前端服务器上, 但您仍需要对其进行设置, 然后才能使用它。 对其进行设置的步骤 (如本部分所述) 组成了存档的部署。

<div>

## <a name="deployment-sequence"></a>部署序列

设置存档的方式取决于您选择的存储选项:

  - 如果你对部署中的所有用户使用 Microsoft Exchange 集成, 则无需为你的用户配置 Lync Server 2013 存档策略。 相反, 配置 Exchange 就地保留策略以支持驻留在 Exchange 2013 上的用户的存档, 并将其邮箱置于就地保留。 有关配置这些策略的详细信息, 请参阅 Exchange 2013 产品文档。

  - 如果你不为部署中的所有用户使用 Microsoft Exchange 集成, 你需要将 Lync Server 存档数据库 (SQL Server 数据库) 添加到你的拓扑, 然后将其发布, 并为你的用户配置策略和设置, 然后才能为这些用户存档数据。 在部署初始拓扑时或在部署了至少一个前端池或标准版服务器之后, 你可以部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署来部署存档数据库。

如果在一个前端池或标准版服务器中启用存档, 则应为部署中的所有其他前端池和标准版服务器启用它。 这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。 如果承载对话或会议的池上没有启用存档，则无法存档完整会话。 在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。

<div>


> [!IMPORTANT]  
> 如果出于合规性原因, 存档在你的组织中非常重要, 请确保部署存档、在相应级别配置策略和其他选项, 并为所有适用的用户启用它, 然后再为 Lync Server 2013 启用这些用户。



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
<td><p><strong>安装必备硬件和软件</strong></p></td>
<td><ul>
<li><p>若要使用 Microsoft Exchange 集成 (使用 Exchange 2013 存档某些或所有用户的存储), 您需要一个现有的 Exchange 2013 部署。</p></li>
<li><p>若要使用单独的存档数据库 (使用 SQL Server 数据库) 来存档某些或所有用户的存储, 将存储存档数据的服务器上的 SQL Server。</p></li>
</ul>
<div>

> [!NOTE]  
> 存档在企业版池和标准版服务器的前端服务器上运行。 除了需要安装这些服务器外，没有额外的软硬件要求。


</div></td>
<td><p>属于本地 Administrators 组成员的域用户。</p></td>
<td><p>可支持文档中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a>。</p>
<p>支持文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a>。</p>
<p>规划文档中<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</p>
<p>在部署文档中,<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">在 Lync Server 2013 中设置用于存档的系统和基础结构</a>。</p>
<p>支持文档中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>创建适当的内部拓扑以支持存档 (仅在未对部署中的所有用户使用 Microsoft Exchange 集成时)</strong></p></td>
<td><p>运行拓扑生成器以将 Lync Server 2013 存档数据库 (SQL Server 数据库) 添加到拓扑, 然后发布拓扑。</p></td>
<td><p>定义用于合并存档数据库的拓扑, 该帐户是本地用户组的成员。</p>
<p>若要发布拓扑, 是域管理员组和 RTCUniversalServerAdmins 组的成员的帐户, 并且具有对 Lync Server 2013 文件存储使用的文件共享的完全控制权限 (读/写/修改), 以便拓扑生成器可以配置所需的 Dacl)。</p></td>
<td><p>在部署文档中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">将存档数据库添加到现有 Lync Server 2013 部署</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>配置服务器到服务器身份验证 (仅当使用 Microsoft Exchange 集成时)</strong></p></td>
<td><p>将服务器配置为在 Lync Server 2013 和 Exchange 2013 之间启用身份验证。 我们建议在启用存档之前, 运行<strong>CsExchangeStorageConnectivity testuser_sipUri-文件夹 Dumpster</strong>验证 Exchange 存档存储连接。</p></td>
<td><p>具有用于管理服务器上的证书的相应权限的帐户。</p></td>
<td><p>在部署文档或操作文档中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>配置存档策略和配置</strong></p></td>
<td><p>配置存档, 包括是否使用 Microsoft Exchange 集成、全局策略和任何网站和用户策略 (不使用 Microsoft Exchange 集成进行所有数据存储) 和特定的存档选项 (如关键模式和数据)导出和清除。</p>
<p>如果使用 Microsoft Exchange 集成, 请根据需要配置 Exchange 就地保留策略。</p></td>
<td><p>RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。</p></td>
<td><p>在部署文档中<a href="lync-server-2013-configuring-support-for-archiving.md">配置 Lync Server 2013 中的存档支持</a>。</p>
<p>Exchange 产品文档 (如果使用的是 Microsoft Exchange 集成)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>在不同的林中部署 Lync Server 和 Microsoft Exchange

如果 Microsoft Exchange Server 未在 Lync Server 所在的林中部署, 则必须确保以下 Exchange Active Directory 属性已同步到部署 Lync Server 的林:

1.  msExchUserHoldPolicies

2.  proxyAddresses

这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。

</div>

</div>

<span> </span>

</div>

</div>

</div>

