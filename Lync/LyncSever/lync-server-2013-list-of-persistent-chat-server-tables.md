---
title: Lync Server 2013：持久聊天服务器表的列表
TOCTitle: 持久聊天服务器表的列表
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558628(v=OCS.15)
ms:contentKeyID: 49312293
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中持久聊天服务器表的列表

 

_**上一次修改主题：** 2015-03-09_

持久聊天数据库架构由以下表组成。

## Active Directory 同步


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></p></td>
<td><p>包含当前轻型目录访问协议 (LDAP) 同步 Cookie。每行均与 持久聊天服务器主动监控变更情况的 Active Directory 域服务 域对应。（该表中仅显示与 持久聊天服务器相关的 Active Directory 域。）</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></p></td>
<td><p>包含尚未通过随后的 Active Directory 同步步骤处理的组成员身份更改（添加的和删除的成员）信息，该表是 Active Directory 同步的第一步使用的临时表（与 tblADUpdates 表一起）之一。</p>
<p>仅对 tblPrincipal 表中列出的组或该表中已列出其成员的组，存储和/或处理成员身份更改信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></p></td>
<td><p>包含尚未通过随后的 Active Directory 同步步骤处理的 Active Directory 域服务 更改信息，该表是 Active Directory 同步的第一步使用的临时表（与 tblPrincipalMemberDifference 表一起）之一。</p>
<p>仅对 tblPrincipal 表中已列出的主体，存储和/或处理 Active Directory 更改信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></p></td>
<td><p>包含主体成员身份。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></p></td>
<td><p>包含必须通过 Active Directory 刷新的主体。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></p></td>
<td><p>包含因某些原因（通常因为 Active Directory 访问错误）无法刷新的附属关系。</p>
<p>该表仅供参考。其内容不可用。</p>
<p>带有无法正常刷新的附属关系的主体保存在 tblPrincipalMeta 表中，它们还有一次刷新机会。</p></td>
</tr>
</tbody>
</table>


## 主体、隶属项、节点、作用域和角色


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
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
<td><p>包含所有主体（用户、文件夹、组等）。 持久聊天服务器可将该表处理为平面异类列表。各列均基于每个主体的类型。</p>
<p>其中大多数主体都是 Active Directory 中存储的对象的缓存副本。在 Principal 表中对这些 Active Directory 对象创建缓存副本的过程称为 <em>设置</em> 。</p>
<p>某些主体在创建时比其他主体有更多的目的，而某些 Active Directory 对象会被完全忽略。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></p></td>
<td><p>包含主体附属关系，说明在 Active Directory 安全组、 Active Directory 容器等位置的成员身份。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></p></td>
<td><p>包含在 Lync Server 控制面板中管理的类别节点。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></p></td>
<td><p>包含角色类型及其相关的权限集。该查找表是静态表。</p></td>
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
<td><p>仅包含用于 tblNode 表的硬编码“Visibility”和“Behavior”属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></p></td>
<td><p>包含用于 tblNode 表的硬编码“Visibility”和“Behavior”属性的值。</p></td>
</tr>
</tbody>
</table>


## 邀请、聊天和其他客户端支持


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
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
<td><p>包含用于文件传输的临时标记。每次上载或下载文件时， 持久聊天服务都会生成一个客户端用于访问 Web 服务文件存储的标记。</p></td>
</tr>
</tbody>
</table>


## 服务器支持


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></p></td>
<td><p>包含 持久聊天服务器池中的活动服务器。</p></td>
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
<td><p>包含 持久聊天服务之间的当前点到点连接。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></p></td>
<td><p>包含 持久聊天服务器不支持的配置。</p></td>
</tr>
</tbody>
</table>

