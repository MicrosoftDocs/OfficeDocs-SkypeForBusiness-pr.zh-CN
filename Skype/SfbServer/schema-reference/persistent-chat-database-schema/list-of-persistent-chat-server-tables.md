---
title: 持久聊天服务器表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 持久聊天数据库架构由下表组成。
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295648"
---
# <a name="list-of-persistent-chat-server-tables"></a>持久聊天服务器表的列表
 
持久聊天数据库架构由下表组成。
  
## <a name="active-directory-sync"></a>Active Directory 同步

|**表格**|**说明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含当前的轻型目录访问协议 (LDAP) 同步 cookie。 每行对应于持久聊天服务器主动监视更改的 Active Directory 域服务域。 (此表中仅表示与持久聊天服务器相关的 Active Directory 域。)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含后续 Active Directory 同步步骤尚未处理的组成员身份更改 (已添加和已删除成员), 并且是 Active Directory 同步的第一步中使用的临时表 (连同 tblADUpdates 表) 之一。  <br/> 仅对 tblPrincipal 表中列出的组或已列出成员的组, 存储、处理或处理成员身份更改。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含对 Active Directory 域服务所做的更改, 这些更改尚未由后续 Active Directory 同步步骤处理, 并且是 Active directory 的第一步中使用的临时表 (以及 tblPrincipalMemberDifference 表) 之一同步.  <br/> 仅对已在 tblPrincipal 表中列出的主体存储、处理或处理对 Active Directory 所做的更改。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主体成员身份。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含必须从 Active Directory 刷新的主体。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含由于某些原因而无法刷新的隶属关系, 通常是由于 Active Directory 访问错误所致。  <br/> 此表仅供提供信息之用。 不使用其内容。  <br/> 具有无法正确刷新的隶属关系的主体将保留在 tblPrincipalMeta 表中, 并且会被授予另一次机会进行刷新。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主体、隶属关系、节点、范围和角色

|**表格**|**说明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |包含用于对 tblPrincipal 表中的内容进行分类的主体类型。 此表是静态表。 它是在创建数据库期间设置的, 不会更改。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |包含所有主体 (用户、文件夹、组等)。 持久聊天服务器将其作为单层异类列表处理。 各种列基于每个主体的类型。  <br/> 大多数主体都是存储在 Active Directory 中的对象的缓存副本。 在这些 Active Directory 对象的主体表中创建缓存的副本称为预配。  <br/> 某些主体的创建比其他主体更主动, 并且某些 Active Directory 对象完全被忽略。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含描述 Active Directory 安全组、Active Directory 容器等中的成员身份的承担者隶属关系。  <br/> |
|[tblNode](tblnode.md) <br/> |包含 "控制面板" 中托管的 "类别" 节点。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |包含角色类型及其关联的权限集。 此查阅表格是静态的。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含分配给节点的作用域。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含分配给节点的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含可与节点相关联的注册外接程序。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |仅包含 tblNode 表中使用的硬编码的 "Visibility" 和 "行为" 属性。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含 tblNode 表中使用的硬编码的 "Visibility" 和 "行为" 属性的值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀请、聊天和其他客户端支持

|**表格**|**说明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |包含系统中已启用自动邀请的所有节点的所有预配用户的邀请。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有聊天消息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |包含为每位用户生成的最后一个邀请 ID (并在 tblPrincipalInvites 表中使用)。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |包含为每位用户生成的最后一个聊天 ID (和在 tblChat 表中使用)。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含用户客户端首选项 (仅供旧版客户端使用)。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含用于文件传输目的的临时令牌。 每次上载或下载文件时, 持久聊天服务都会生成客户端用于访问 Web 服务文件存储的令牌。  <br/> |
   
## <a name="server-support"></a>服务器支持

|**表格**|**说明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含持久聊天服务器池中的活动服务器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含用于运行某些管理员命令的管理员锁。 TblSystemRevision 表中的系统修订条目在每个锁版本后递增。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |包含所使用的修订号条目 (与 tblAdminLock 表一起), 以便跨多台服务器实现一致性。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含持久聊天服务之间的当前对等连接。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含持久聊天服务器不支持的配置。  <br/> |
   

