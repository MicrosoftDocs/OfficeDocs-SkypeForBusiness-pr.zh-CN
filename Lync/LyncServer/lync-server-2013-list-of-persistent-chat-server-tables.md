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
ms.openlocfilehash: e65560cd792fe4132cf20f3b32824b2c828ae757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="6a30d-102">Lync Server 2013 中持久聊天服务器表的列表</span><span class="sxs-lookup"><span data-stu-id="6a30d-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a30d-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6a30d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6a30d-104">持久聊天数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="6a30d-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="6a30d-105">Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="6a30d-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a30d-106">Table</span><span class="sxs-lookup"><span data-stu-id="6a30d-106">Table</span></span></th>
<th><span data-ttu-id="6a30d-107">说明</span><span class="sxs-lookup"><span data-stu-id="6a30d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-109">包含当前的轻型目录访问协议（LDAP）同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="6a30d-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="6a30d-110">每行对应于持久聊天服务器主动监视更改的 Active Directory 域服务域。</span><span class="sxs-lookup"><span data-stu-id="6a30d-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="6a30d-111">（只有与持久聊天服务器相关的 Active Directory 域才会在此表中表示。）</span><span class="sxs-lookup"><span data-stu-id="6a30d-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-113">包含后续 Active Directory 同步步骤尚未处理的组成员身份更改（添加和删除的成员），并且是 Active Directory 同步第一步中使用的临时表（连同 tblADUpdates 表）之一。</span><span class="sxs-lookup"><span data-stu-id="6a30d-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="6a30d-114">仅对 tblPrincipal 表中列出的组或该表中已列出其成员的组，存储和/或处理成员身份更改信息。</span><span class="sxs-lookup"><span data-stu-id="6a30d-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-116">包含对 Active Directory 域服务所做的更改，这些更改尚未经过后续 Active Directory 同步步骤的处理，是 Active directory 第一步中使用的临时表（连同 tblPrincipalMemberDifference 表）之一同步.</span><span class="sxs-lookup"><span data-stu-id="6a30d-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="6a30d-117">仅对已在 tblPrincipal 表中列出的主体存储、处理或处理对 Active Directory 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6a30d-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-119">包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="6a30d-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-121">包含必须从 Active Directory 刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="6a30d-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-123">包含由于某种原因无法刷新的隶属关系，通常是由于 Active Directory 访问错误而导致的。</span><span class="sxs-lookup"><span data-stu-id="6a30d-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="6a30d-p102">该表仅供参考。其内容不可用。</span><span class="sxs-lookup"><span data-stu-id="6a30d-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="6a30d-126">带有无法正常刷新的附属关系的主体保存在 tblPrincipalMeta 表中，它们还有一次刷新机会。</span><span class="sxs-lookup"><span data-stu-id="6a30d-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="6a30d-127">主体、隶属项、节点、作用域和角色</span><span class="sxs-lookup"><span data-stu-id="6a30d-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a30d-128">Table</span><span class="sxs-lookup"><span data-stu-id="6a30d-128">Table</span></span></th>
<th><span data-ttu-id="6a30d-129">说明</span><span class="sxs-lookup"><span data-stu-id="6a30d-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-p103">包含 tblPrincipal 表中的要分类的主体类型。该表是静态表。在数据库创建时建立，不能更改。</span><span class="sxs-lookup"><span data-stu-id="6a30d-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-135">包含所有主体（用户、文件夹、组等）。</span><span class="sxs-lookup"><span data-stu-id="6a30d-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="6a30d-136">持久聊天服务器将其作为单层异类列表处理。</span><span class="sxs-lookup"><span data-stu-id="6a30d-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="6a30d-137">各列均基于每个主体的类型。</span><span class="sxs-lookup"><span data-stu-id="6a30d-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="6a30d-138">大多数主体都是存储在 Active Directory 中的对象的缓存副本。</span><span class="sxs-lookup"><span data-stu-id="6a30d-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="6a30d-139">在这些 Active Directory 对象的主体表中创建缓存副本称为 "<em>设置</em>"。</span><span class="sxs-lookup"><span data-stu-id="6a30d-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="6a30d-140">有些主体的创建比其他主体更主动，并且某些 Active Directory 对象完全忽略。</span><span class="sxs-lookup"><span data-stu-id="6a30d-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-142">包含描述 Active Directory 安全组、Active Directory 容器等成员身份的主体隶属关系。</span><span class="sxs-lookup"><span data-stu-id="6a30d-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-144">包含在 Lync Server 控制面板中托管的类别节点。</span><span class="sxs-lookup"><span data-stu-id="6a30d-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-146">包含角色类型及其相关的权限集。</span><span class="sxs-lookup"><span data-stu-id="6a30d-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="6a30d-147">该查找表是静态表。</span><span class="sxs-lookup"><span data-stu-id="6a30d-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-149">包含分配至节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="6a30d-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-151">包含分配至节点的角色。</span><span class="sxs-lookup"><span data-stu-id="6a30d-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-153">包含可与节点关联的注册外接程序。</span><span class="sxs-lookup"><span data-stu-id="6a30d-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-155">仅包含 tblNode 表&quot;中&quot;使用&quot;的&quot;硬编码的可见性和行为属性。</span><span class="sxs-lookup"><span data-stu-id="6a30d-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-157">包含在 tblNode 表中使用&quot;的硬编码的可见&quot;性 "和" 行为属性的值。</span><span class="sxs-lookup"><span data-stu-id="6a30d-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="6a30d-158">邀请、聊天和其他客户端支持</span><span class="sxs-lookup"><span data-stu-id="6a30d-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a30d-159">Table</span><span class="sxs-lookup"><span data-stu-id="6a30d-159">Table</span></span></th>
<th><span data-ttu-id="6a30d-160">说明</span><span class="sxs-lookup"><span data-stu-id="6a30d-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-162">包含系统中启用自动邀请功能的所有节点的所有设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="6a30d-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-164">包含所有聊天消息。</span><span class="sxs-lookup"><span data-stu-id="6a30d-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-166">包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="6a30d-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-168">包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="6a30d-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-170">包含用户客户端首选项（仅由旧式客户端使用）。</span><span class="sxs-lookup"><span data-stu-id="6a30d-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-172">包含用于文件传输的临时标记。</span><span class="sxs-lookup"><span data-stu-id="6a30d-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="6a30d-173">每次上传或下载文件时，持久聊天服务都会生成一个令牌，客户端使用该令牌来访问 Web 服务文件存储。</span><span class="sxs-lookup"><span data-stu-id="6a30d-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="6a30d-174">服务器支持</span><span class="sxs-lookup"><span data-stu-id="6a30d-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a30d-175">Table</span><span class="sxs-lookup"><span data-stu-id="6a30d-175">Table</span></span></th>
<th><span data-ttu-id="6a30d-176">说明</span><span class="sxs-lookup"><span data-stu-id="6a30d-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-177"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-178">包含持久聊天服务器池中的活动服务器。</span><span class="sxs-lookup"><span data-stu-id="6a30d-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-p108">包含用于运行某些管理员命令的管理员锁定。在每次解除锁定后，tblSystemRevision 表中的系统修订条目都会增加。</span><span class="sxs-lookup"><span data-stu-id="6a30d-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-183">包含为实现多个服务器之间的一致性使用的修订号条目（与 tblAdminLock 表一起）。</span><span class="sxs-lookup"><span data-stu-id="6a30d-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a30d-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-185">包含持续聊天服务之间的当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="6a30d-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a30d-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="6a30d-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6a30d-187">包含持久聊天服务器不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="6a30d-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

