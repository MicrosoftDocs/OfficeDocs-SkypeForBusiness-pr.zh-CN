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
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="241ca-102">Lync Server 2013 中持久聊天服务器表的列表</span><span class="sxs-lookup"><span data-stu-id="241ca-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="241ca-103">_**主题上次修改时间：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="241ca-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="241ca-104">持久聊天数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="241ca-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="241ca-105">Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="241ca-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="241ca-106">表格</span><span class="sxs-lookup"><span data-stu-id="241ca-106">Table</span></span></th>
<th><span data-ttu-id="241ca-107">说明</span><span class="sxs-lookup"><span data-stu-id="241ca-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="241ca-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="241ca-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-109">包含当前的轻型目录访问协议（LDAP）同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="241ca-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="241ca-110">每行对应于持久聊天服务器主动监视更改的 Active Directory 域服务域。</span><span class="sxs-lookup"><span data-stu-id="241ca-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="241ca-111">（此表中仅表示与持久聊天服务器相关的 Active Directory 域。）</span><span class="sxs-lookup"><span data-stu-id="241ca-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="241ca-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-113">包含后续 Active Directory 同步步骤尚未处理的组成员身份更改（已添加和已删除成员），并且是 Active Directory 同步的第一步中使用的临时表（连同 tblADUpdates 表）之一。</span><span class="sxs-lookup"><span data-stu-id="241ca-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="241ca-114">仅对 tblPrincipal 表中列出的组或已列出成员的组，存储、处理或处理成员身份更改。</span><span class="sxs-lookup"><span data-stu-id="241ca-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="241ca-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-116">包含对 Active Directory 域服务所做的更改，这些更改尚未由后续 Active Directory 同步步骤处理，并且是 Active directory 的第一步中使用的临时表（以及 tblPrincipalMemberDifference 表）之一同步.</span><span class="sxs-lookup"><span data-stu-id="241ca-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="241ca-117">仅对已在 tblPrincipal 表中列出的主体存储、处理或处理对 Active Directory 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="241ca-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="241ca-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-119">包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="241ca-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="241ca-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-121">包含必须从 Active Directory 刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="241ca-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="241ca-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-123">包含由于某些原因而无法刷新的隶属关系，通常是由于 Active Directory 访问错误所致。</span><span class="sxs-lookup"><span data-stu-id="241ca-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="241ca-124">此表仅供提供信息之用。</span><span class="sxs-lookup"><span data-stu-id="241ca-124">This table is for informational purposes only.</span></span> <span data-ttu-id="241ca-125">不使用其内容。</span><span class="sxs-lookup"><span data-stu-id="241ca-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="241ca-126">具有无法正确刷新的隶属关系的主体将保留在 tblPrincipalMeta 表中，并且会被授予另一次机会进行刷新。</span><span class="sxs-lookup"><span data-stu-id="241ca-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="241ca-127">主体、隶属关系、节点、范围和角色</span><span class="sxs-lookup"><span data-stu-id="241ca-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="241ca-128">表格</span><span class="sxs-lookup"><span data-stu-id="241ca-128">Table</span></span></th>
<th><span data-ttu-id="241ca-129">说明</span><span class="sxs-lookup"><span data-stu-id="241ca-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="241ca-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="241ca-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-131">包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="241ca-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="241ca-132">此表是静态表。</span><span class="sxs-lookup"><span data-stu-id="241ca-132">This table is static.</span></span> <span data-ttu-id="241ca-133">它是在创建数据库期间设置的，不会更改。</span><span class="sxs-lookup"><span data-stu-id="241ca-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="241ca-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-135">包含所有主体（用户、文件夹、组等）。</span><span class="sxs-lookup"><span data-stu-id="241ca-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="241ca-136">持久聊天服务器将其作为单层异类列表处理。</span><span class="sxs-lookup"><span data-stu-id="241ca-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="241ca-137">各种列基于每个主体的类型。</span><span class="sxs-lookup"><span data-stu-id="241ca-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="241ca-138">大多数主体都是存储在 Active Directory 中的对象的缓存副本。</span><span class="sxs-lookup"><span data-stu-id="241ca-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="241ca-139">在这些 Active Directory 对象的主体表中创建缓存的副本称为<em>预配</em>。</span><span class="sxs-lookup"><span data-stu-id="241ca-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="241ca-140">某些主体的创建比其他主体更主动，并且某些 Active Directory 对象完全被忽略。</span><span class="sxs-lookup"><span data-stu-id="241ca-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="241ca-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-142">包含描述 Active Directory 安全组、Active Directory 容器等中的成员身份的承担者隶属关系。</span><span class="sxs-lookup"><span data-stu-id="241ca-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="241ca-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-144">包含 "Lync Server 控制面板" 中托管的 "类别" 节点。</span><span class="sxs-lookup"><span data-stu-id="241ca-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="241ca-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-146">包含角色类型及其关联的权限集。</span><span class="sxs-lookup"><span data-stu-id="241ca-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="241ca-147">此查阅表格是静态的。</span><span class="sxs-lookup"><span data-stu-id="241ca-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="241ca-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-149">包含分配给节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="241ca-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="241ca-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-151">包含分配给节点的角色。</span><span class="sxs-lookup"><span data-stu-id="241ca-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="241ca-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-153">包含可与节点相关联的注册外接程序。</span><span class="sxs-lookup"><span data-stu-id="241ca-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="241ca-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-155">仅包含 tblNode 表&quot;中&quot;使用&quot;的&quot;硬编码的可见性和行为属性。</span><span class="sxs-lookup"><span data-stu-id="241ca-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="241ca-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-157">包含在 tblNode 表中使用&quot;的硬编码的可见&quot;性 "和" 行为属性的值。</span><span class="sxs-lookup"><span data-stu-id="241ca-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="241ca-158">邀请、聊天和其他客户端支持</span><span class="sxs-lookup"><span data-stu-id="241ca-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="241ca-159">表格</span><span class="sxs-lookup"><span data-stu-id="241ca-159">Table</span></span></th>
<th><span data-ttu-id="241ca-160">说明</span><span class="sxs-lookup"><span data-stu-id="241ca-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="241ca-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="241ca-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-162">包含系统中已启用自动邀请的所有节点的所有预配用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="241ca-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="241ca-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-164">包含所有聊天消息。</span><span class="sxs-lookup"><span data-stu-id="241ca-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="241ca-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-166">包含为每位用户生成的最后一个邀请 ID （并在 tblPrincipalInvites 表中使用）。</span><span class="sxs-lookup"><span data-stu-id="241ca-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="241ca-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-168">包含为每位用户生成的最后一个聊天 ID （和在 tblChat 表中使用）。</span><span class="sxs-lookup"><span data-stu-id="241ca-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="241ca-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-170">包含用户客户端首选项（仅供旧版客户端使用）。</span><span class="sxs-lookup"><span data-stu-id="241ca-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="241ca-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-172">包含用于文件传输目的的临时令牌。</span><span class="sxs-lookup"><span data-stu-id="241ca-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="241ca-173">每次上载或下载文件时，持久聊天服务都会生成客户端用于访问 Web 服务文件存储的令牌。</span><span class="sxs-lookup"><span data-stu-id="241ca-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="241ca-174">服务器支持</span><span class="sxs-lookup"><span data-stu-id="241ca-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="241ca-175">表格</span><span class="sxs-lookup"><span data-stu-id="241ca-175">Table</span></span></th>
<th><span data-ttu-id="241ca-176">说明</span><span class="sxs-lookup"><span data-stu-id="241ca-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="241ca-177"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="241ca-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-178">包含持久聊天服务器池中的活动服务器。</span><span class="sxs-lookup"><span data-stu-id="241ca-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="241ca-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-180">包含用于运行某些管理员命令的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="241ca-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="241ca-181">TblSystemRevision 表中的系统修订条目在每个锁版本后递增。</span><span class="sxs-lookup"><span data-stu-id="241ca-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="241ca-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-183">包含所使用的修订号条目（与 tblAdminLock 表一起），以便跨多台服务器实现一致性。</span><span class="sxs-lookup"><span data-stu-id="241ca-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="241ca-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="241ca-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-185">包含持久聊天服务之间的当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="241ca-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="241ca-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="241ca-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="241ca-187">包含持久聊天服务器不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="241ca-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

