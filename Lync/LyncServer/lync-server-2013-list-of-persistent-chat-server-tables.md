---
title: Lync Server 2013：持久聊天服务器表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d9fe9db5ad22a0d6ad2d68d0afdbd5b0969608
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器表的列表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

持久聊天数据库架构由下表组成。

<div>

## <a name="active-directory-sync"></a>Active Directory 同步


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></p></td>
<td><p>包含当前的轻型目录访问协议（LDAP）同步 cookie。 每行对应于持久聊天服务器主动监视更改的 Active Directory 域服务域。 （只有与持久聊天服务器相关的 Active Directory 域才会在此表中表示。）</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></p></td>
<td><p>包含后续 Active Directory 同步步骤尚未处理的组成员身份更改（添加和删除的成员），并且是 Active Directory 同步第一步中使用的临时表（连同 tblADUpdates 表）之一。</p>
<p>仅对 tblPrincipal 表中列出的组或该表中已列出其成员的组，存储和/或处理成员身份更改信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></p></td>
<td><p>包含对 Active Directory 域服务所做的更改，这些更改尚未经过后续 Active Directory 同步步骤的处理，是 Active directory 第一步中使用的临时表（连同 tblPrincipalMemberDifference 表）之一同步.</p>
<p>仅对已在 tblPrincipal 表中列出的主体存储、处理或处理对 Active Directory 所做的更改。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></p></td>
<td><p>包含主体成员身份。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></p></td>
<td><p>包含必须从 Active Directory 刷新的主体。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></p></td>
<td><p>包含由于某种原因无法刷新的隶属关系，通常是由于 Active Directory 访问错误而导致的。</p>
<p>该表仅供参考。其内容不可用。</p>
<p>带有无法正常刷新的附属关系的主体保存在 tblPrincipalMeta 表中，它们还有一次刷新机会。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主体、隶属项、节点、作用域和角色


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></p></td>
<td><p>包含 tblPrincipal 表中的要分类的主体类型。该表是静态表。在数据库创建时建立，不能更改。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></p></td>
<td><p>包含所有主体（用户、文件夹、组等）。 持久聊天服务器将其作为单层异类列表处理。 各列均基于每个主体的类型。</p>
<p>大多数主体都是存储在 Active Directory 中的对象的缓存副本。 在这些 Active Directory 对象的主体表中创建缓存副本称为 "<em>设置</em>"。</p>
<p>有些主体的创建比其他主体更主动，并且某些 Active Directory 对象完全忽略。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></p></td>
<td><p>包含描述 Active Directory 安全组、Active Directory 容器等成员身份的主体隶属关系。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></p></td>
<td><p>包含在 Lync Server 控制面板中托管的类别节点。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></p></td>
<td><p>包含角色类型及其相关的权限集。 该查找表是静态表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></p></td>
<td><p>包含分配至节点的作用域。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></p></td>
<td><p>包含分配至节点的角色。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></p></td>
<td><p>包含可与节点关联的注册外接程序。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></p></td>
<td><p>仅包含 tblNode 表&quot;中&quot;使用&quot;的&quot;硬编码的可见性和行为属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></p></td>
<td><p>包含在 tblNode 表中使用&quot;的硬编码的可见&quot;性 "和" 行为属性的值。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>邀请、聊天和其他客户端支持


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></p></td>
<td><p>包含系统中启用自动邀请功能的所有节点的所有设置用户的邀请。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></p></td>
<td><p>包含所有聊天消息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></p></td>
<td><p>包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></p></td>
<td><p>包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></p></td>
<td><p>包含用户客户端首选项（仅由旧式客户端使用）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></p></td>
<td><p>包含用于文件传输的临时标记。 每次上传或下载文件时，持久聊天服务都会生成一个令牌，客户端使用该令牌来访问 Web 服务文件存储。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>服务器支持


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></p></td>
<td><p>包含持久聊天服务器池中的活动服务器。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></p></td>
<td><p>包含用于运行某些管理员命令的管理员锁定。在每次解除锁定后，tblSystemRevision 表中的系统修订条目都会增加。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></p></td>
<td><p>包含为实现多个服务器之间的一致性使用的修订号条目（与 tblAdminLock 表一起）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></p></td>
<td><p>包含持续聊天服务之间的当前对等连接。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></p></td>
<td><p>包含持久聊天服务器不支持的配置。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

