---
title: 持久聊天服务器表的列表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 持续聊天数据库架构包含，以下各表。
ms.openlocfilehash: d9a00095cb18e63cc29e16ae66e608127afad606
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-tables"></a>持久聊天服务器表的列表
 
持续聊天数据库架构包含，以下各表。
  
## <a name="active-directory-sync"></a>活动目录同步

|**表**|**说明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含当前的轻型目录访问协议 (LDAP) 同步 cookie。 每一行对应于持久聊天服务器主动监视的更改 Active Directory 域服务域中。 （相关的持久聊天服务器的 Active Directory 域被表示此表中。  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含组成员身份的更改 （添加和删除成员） 尚未处理的后续活动目录同步步骤，而是一个活动目录同步的第一步中使用的临时表 （与 tblADUpdates 表）。  <br/> 成员资格更改将存储，处理，或者，只能针对已经 tblPrincipal 表中所列出的组均那里列出成员。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含对尚未处理的后续活动目录同步步骤的 Active Directory 域服务的更改，而是一个 Active Directory 的第一步中使用的临时表 （与 tblPrincipalMemberDifference 表）同步。  <br/> 活动目录更改的存储，处理，或两只的 tblPrincipal 表中已列出的承担者。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主要成员身份。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含需要刷新来自 Active Directory 的主体。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含无法刷新由于某种原因，通常是因为 Active Directory 访问错误的隶属关系。  <br/> 此表是仅用于提供信息。 不使用其内容。  <br/> 隶属关系，不能正确刷新与主体 tblPrincipalMeta 表中保留，并给出了另一个有机会被刷新。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主体、 隶属关系、 节点、 范围和角色

|**表**|**说明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |包含主体的类型进行分类的 tblPrincipal 表中。 此表是静态的。 它在数据库创建过程中设置并不会改变。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |包含所有承担者 （用户、 文件夹、 组等）。 持久的聊天服务器处理此为单层异类列表。 各列基于每个主体的类型。  <br/> 大多数这些主体都存储在 Active Directory 中的对象的缓存的副本。 创建的缓存的副本在主体中的这些 Active Directory 对象的表称为资源调配。  <br/> 比其他人更严格地创建一些主体，某些 Active Directory 对象被完全忽略。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含描述在 Active Directory 安全组、 Active Directory 容器等的成员身份的主要附属机构。  <br/> |
|[tblNode](tblnode.md) <br/> |包含类别节点中，在控制面板中进行管理。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |包含角色类型和其关联的权限集。 此查阅表格是静态的。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含分配给节点的作用。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含分配给节点的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含已注册的外接程序可与节点相关联。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |包含的硬编码"可见性"和"行为"属性使用 tblNode 表中。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含在 tblNode 表中使用的硬编码"可见性"和"行为"属性的值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀请、 聊天室和其他客户端支持

|**表**|**说明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |自动邀请启用所有节点的系统中包含已设置的所有用户的邀请。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有的聊天消息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |包含已生成 （和 tblPrincipalInvites 表中） 的最后一次邀请 ID 为每个用户。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |包含已生成 （和 tblChat 表中） 的最后一个聊天 ID 为每个用户。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含用户客户端首选项 （使用旧式客户端）。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含文件传输目的的临时标记。 文件上载或下载，每次持续聊天服务生成客户端用于访问 Web 服务文件存储的标记。  <br/> |
   
## <a name="server-support"></a>服务器支持

|**表**|**说明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含持久聊天服务器池中的活动服务器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含管理员锁定运行某些管理员命令。 在每个释放锁后，tblSystemRevision 表中的系统修订条目就会增加。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |跨多个服务器实现一致性包含修订编号条目 （与 tblAdminLock 表中）。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含当前持续聊天服务之间的对等连接。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含的持久聊天服务器不受支持的配置。  <br/> |
   

