---
title: 持久聊天服务器表的列表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 持久聊天数据库架构由以下表组成。
ms.openlocfilehash: e2ce24bb37c3ea4eaee0986f0243033ab4a8a18a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898541"
---
# <a name="list-of-persistent-chat-server-tables"></a>持久聊天服务器表的列表
 
持久聊天数据库架构由以下表组成。
  
## <a name="active-directory-sync"></a>Active Directory 同步

|**表格**|**说明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含当前轻型目录访问协议 (LDAP) 同步 cookie。 每一行对应于持久聊天服务器当前正在监控的更改的 Active Directory 域服务域。 （for Persistent Chat Server 相关的 Active Directory 域中都表示该表。）  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 同步步骤处理和是一种 Active Directory 同步的第一步中使用的临时表 （以及 tblADUpdates 表）。  <br/> 存储成员身份更改处理，或同时，仅对 tblPrincipal 表或中已列出的组已列出其成员存在。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改和是一种 Active Directory 的第一步中使用的临时表 （以及 tblPrincipalMemberDifference 表中）同步。  <br/> 存储对 Active Directory 更改处理，仅对 tblPrincipal 表中已列出的主体和 / 或。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主体成员身份。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含必须从 Active Directory 刷新的主体。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含一些原因，通常因为 Active Directory 访问错误无法刷新的附属关系。  <br/> 此表是仅用于提供信息。 不使用其内容。  <br/> 带有无法正常刷新的隶属项的主体保存在 tblPrincipalMeta 表，并给出了一次刷新机会。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主体、 隶属项、 节点、 作用域和角色

|**表格**|**说明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |包含要分类 tblPrincipal 表中的主体类型。 此表是静态的。 它在数据库创建期间设置并不会更改。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |包含所有主体 （用户、 文件夹、 组和等等）。 持久聊天服务器处理这为平面异构列表。 各列基于每个主体的类型。  <br/> 这些主体大部分是在 Active Directory 中存储的对象缓存的副本。 创建缓存的副本主体中的这些 Active Directory 对象的表称作设置。  <br/> 某些主体在创建时比其他，更多的目的和某些 Active Directory 对象会被完全忽略。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含主体附属关系介绍 Active Directory 安全组、 Active Directory 容器等中的成员身份。  <br/> |
|[tblNode](tblnode.md) <br/> |包含类别节点中，在控制面板中管理。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |包含角色类型和其关联的权限集。 此查阅表格是静态的。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含分配至节点的作用域。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含分配至节点的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含注册的加载项可与节点关联。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |包含仅的硬编码"Visibility"和"Behavior"属性用于 tblNode 表。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含用于 tblNode 表的硬编码"Visibility"和"Behavior"属性的值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀请、 聊天和其他客户端支持

|**表格**|**说明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |自动邀请启用系统中的所有节点包含所有已设置用户的邀请。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有聊天消息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含用户客户端首选项 （由旧客户端）。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含用于文件传输的临时令牌。 每次上载或下载，文件的持久聊天服务会生成客户端用于访问 Web 服务文件存储的令牌。  <br/> |
   
## <a name="server-support"></a>服务器支持

|**表格**|**说明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含持久聊天服务器池中的活动服务器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含运行一些管理员命令的管理员锁。 TblSystemRevision 表中的系统修订条目将递增后锁定的每个版本。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |包含为实现多个服务器之间的一致性的修订号条目 （与 tblAdminLock 表） 一起使用。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含持久聊天服务之间当前对等连接。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含持久聊天服务器不支持的配置。  <br/> |
   

