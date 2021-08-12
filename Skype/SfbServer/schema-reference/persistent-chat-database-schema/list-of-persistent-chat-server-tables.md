---
title: 持久聊天服务器表列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 持久聊天数据库架构由下表组成。
ms.openlocfilehash: bc7189eac8e8fbd42cdaa5786b82d5652c616a69ae3fc4fc180c189416a94468
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280935"
---
# <a name="list-of-persistent-chat-server-tables"></a>持久聊天服务器表列表
 
持久聊天数据库架构由下表组成。
  
## <a name="active-directory-sync"></a>Active Directory 同步

|**Table**|**说明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含当前的轻型目录访问协议 (LDAP) 同步 Cookie。 每行对应于持久聊天服务器正在主动监视更改的 Active Directory 域服务域。  (此表中只表示与持久聊天服务器相关的 Active Directory 域)   <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含组成员身份更改 (包括尚未由稍后的 Active Directory 同步步骤处理的已添加和删除的成员) ，以及 active Directory Sync 第一步中使用的临时表 (以及 tblADUpdates 表) 之一。  <br/> 仅对 tblPrincipal 表中列出的组或该表中已列出其成员的组，存储和/或处理成员身份更改信息。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含对 Active Directory 域服务所做的更改，这些更改尚未由稍后的 Active Directory 同步步骤处理，并且与 Active Directory 同步的第一步中使用的 tblPrincipalMemberDifference 表) 一起是临时表 (之一。  <br/> 对 Active Directory 的更改仅存储、处理或仅针对 tblPrincipal 表中已列出的主体。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主体成员身份。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含必须从 Active Directory 中刷新的主体。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含由于某种原因（通常是由于 Active Directory 访问错误）无法刷新的附属关系。  <br/> 该表仅供参考。其内容不可用。  <br/> 带有无法正常刷新的附属关系的主体保存在 tblPrincipalMeta 表中，它们还有一次刷新机会。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主体、隶属项、节点、作用域和角色

|**Table**|**说明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |包含 tblPrincipal 表中的要分类的主体类型。该表是静态表。在数据库创建时建立，不能更改。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |包含所有主体（用户、文件夹、组等）。 持久聊天服务器将此操作作为平面异类列表处理。 各列均基于每个主体的类型。  <br/> 这些主体中的大多数都是存储在 Active Directory 中的对象的缓存副本。 在这些 Active Directory 对象的 Principal 表中创建缓存副本称为设置。  <br/> 某些主体的创建方式比创建其他主体更积极，而某些 Active Directory 对象则完全被忽略。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含描述 Active Directory 安全组、Active Directory 容器等中的成员身份的主体附属关系。  <br/> |
|[tblNode](tblnode.md) <br/> |包含在控制面板中管理的类别节点。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |包含角色类型及其相关的权限集。该查找表是静态表。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含分配至节点的作用域。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含分配至节点的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含可与节点关联的注册外接程序。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |仅包含用于 tblNode 表的硬编码“Visibility”和“Behavior”属性。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含在 tblNode 表中使用的硬编码的"Visibility"和"Behavior"属性的值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀请、聊天和其他客户端支持

|**Table**|**说明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |包含系统中启用自动邀请功能的所有节点的所有设置用户的邀请。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有聊天消息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含用户客户端首选项（仅由旧式客户端使用）。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含用于文件传输的临时标记。 每次上载或下载文件时，持久聊天服务都会生成客户端用于访问 Web 服务文件存储的令牌。  <br/> |
   
## <a name="server-support"></a>服务器支持

|**Table**|**说明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含持久聊天服务器池中的活动服务器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含用于运行某些管理员命令的管理员锁定。在每次解除锁定后，tblSystemRevision 表中的系统修订条目都会增加。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |包含为实现多个服务器之间的一致性使用的修订号条目（与 tblAdminLock 表一起）。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含持久聊天服务之间的当前对等连接。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含不支持持久聊天服务器的配置。  <br/> |
   

