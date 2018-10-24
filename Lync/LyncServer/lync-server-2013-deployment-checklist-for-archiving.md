---
title: Lync Server 2013：存档的部署清单
TOCTitle: 存档的部署清单
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205009(v=OCS.15)
ms:contentKeyID: 49313258
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中存档的部署清单

 

_**上一次修改主题：** 2015-03-09_

虽然在 Lync Server 2013 部署中会将存档自动安装到前端服务器上，但您仍需先设置存档，然后才能使用它。本节中总结了设置存档所需的步骤，这些步骤构成了存档的部署。

## 部署顺序

设置存档的方式取决于您所选的存储选项：

  - 如果在部署中对所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Lync Server 2013 存档策略。相反，配置 Exchange 就地保留策略以支持对驻留在 Exchange 2013 中且其邮箱已被置于就地保留状态的用户进行存档。有关配置这些策略的详细信息，请参阅 Exchange 2013 产品文档。

  - 如果在部署中未对所有用户使用 Microsoft Exchange 集成，则需要将 Lync Server 存档数据库（ SQL Server 数据库）添加到您的拓扑，然后发布拓扑，并为用户配置策略和设置，然后才能为这些用户存档数据。可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。

如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。

> [!IMPORTANT]
> 如果由于合规性原因，存档在您的组织中非常关键，请务必在适当级别部署存档、配置策略和其他选项，并为相应的所有用户启用存档（在为 Lync Server 2013 启用这些用户之前）。


## 存档部署过程

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
<li><p>若要使用 Microsoft Exchange 集成（使用 Exchange 2013 为部分或所有用户进行存档存储），您需要一个现有 Exchange 2013 部署。</p></li>
<li><p>若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。</p></li>
</ul>
<div>

> [!NOTE]  
> 存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。


</div></td>
<td><p>属于本地 Administrators 组成员的域用户。</p></td>
<td><p>可支持性文档中的 <a href="lync-server-2013-supported-hardware.md">支持的适用于 Lync Server 2013 的硬件</a>。</p>
<p>可支持性文档中的 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的服务器软件和基础结构支持</a>。</p>
<p>规划文档中的 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存档技术要求</a>。</p>
<p>部署文档中的 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">设置存档的系统和基础结构</a>。</p>
<p>可支持性文档中的 <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>创建适当的内部拓扑以支持存档（仅当未在部署中对所有用户使用 Microsoft Exchange 集成时）</strong></p></td>
<td><p>运行 拓扑生成器以向拓扑中添加 Lync Server 2013 存档数据库（ SQL Server 数据库），然后发布该拓扑。</p></td>
<td><p>要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。</p>
<p>要发布拓扑，需要具有满足以下条件的帐户：它是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并对要用于 Lync Server 2013 文件存储的文件共享拥有完全控制权限（读取/写入/修改）（因此，拓扑生成器可以配置所需的 DACL）。</p></td>
<td><p>部署文档中的 <a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">向现有 Lync Server 2013 部署添加存档数据库</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>配置服务器到服务器身份验证（仅在使用 Microsoft Exchange 集成时）</strong></p></td>
<td><p>配置服务器以启用 Lync Server 2013 和 Exchange 2013 之间的身份验证。在启用存档之前，建议先运行 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> 来验证 Exchange 存档存储连接。</p></td>
<td><p>具有用于管理服务器上的证书的相应权限的帐户。</p></td>
<td><p>部署文档或操作文档中的 <a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>配置存档策略和配置</strong></p></td>
<td><p>配置存档，包括是否使用 Microsoft Exchange 集成、全局策略及任何站点策略和用户策略（在未对所有数据存储使用 Microsoft Exchange 集成时）以及特定的存档选项（例如，临界模式以及数据导出和清除）。</p>
<p>如果使用 Microsoft Exchange 集成，请根据需要配置 Exchange 就地保留策略。</p></td>
<td><p>RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。</p></td>
<td><p>部署文档中的 <a href="lync-server-2013-configuring-support-for-archiving.md">配置存档支持</a>。</p>
<p>Exchange 产品文档（如果使用 Microsoft Exchange 集成）。</p></td>
</tr>
</tbody>
</table>


## 在不同林中部署 Lync Server 和 Microsoft Exchange

如果未在 Lync Server 所在的林中部署 Microsoft Exchange Server，则必须确保将以下 Exchange Active Directory 属性同步到部署了 Lync Server 的林：

1.  msExchUserHoldPolicies

2.  proxyAddresses

这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。

