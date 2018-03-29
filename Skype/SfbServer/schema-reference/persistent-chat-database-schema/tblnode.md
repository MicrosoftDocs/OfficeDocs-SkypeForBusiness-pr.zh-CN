---
title: tblNode
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含对象 （类别或聊天室节点树） 托管在控制面板和管理 cmdlet。
ms.openlocfilehash: b743453225fda70db18a7bc616a5f7b647d5ebff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含对象 （类别或聊天室节点树） 托管在控制面板和管理 cmdlet。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为空  <br/> |节点的 ID （唯一编号）。  <br/> |
|nodeGuid  <br/> |GUID，不为空  <br/> |节点的 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父节点 ID。 （具有 ID 为 1) 的根节点包含自身作为父项也。  <br/> |
|节点类型  <br/> |位，不为空  <br/> |如果该节点是一个类别，则返回 true。  <br/> 如果该节点是聊天室，则为 false。  <br/> |
|节点名称  <br/> |nvarchar (256) 不为空  <br/> |节点名称。  <br/> |
|nodeDesc  <br/> |nvarchar (256) 不为空  <br/> |节点的说明。  <br/> |
|邀请  <br/> |bit  <br/> | 类别： <br/>  如果邀请在上，则为 true。 <br/>  如果邀请处于关闭状态，则为 false。 <br/>  为文件室： <br/>  如果邀请处于关闭状态 （将重写父类别）。 <br/>  如果从父类别继承设置的邀请，则为 null。 <br/> |
|记录  <br/> |bit  <br/> | 类别： <br/>  如果聊天历史上，则为 true。 <br/>  如果聊天历史处于关闭状态，则为 false。 <br/>  为文件室： <br/>  为空。 <br/> |
|filePost  <br/> |bit  <br/> | 类别： <br/>  如果允许文件上载，则为 true。 <br/>  如果不允许使用文件上载，则为 false。 <br/>  为文件室： <br/>  为空。 <br/> |
|禁用  <br/> |位，不为空  <br/> |如果聊天室被禁用，则为 true。 仅适用于聊天室。 （类别为假）。  <br/> |
|||
|行为  <br/> |smallint，不为空  <br/> | （在 EnumValue 表中查找） 的行为： <br/>  4： 普通 （正常聊天室）。 <br/>  5： 大会堂 （大会堂聊天室，仅演示者可以参与）。 <br/>  仅适用于聊天室。 <br/> |
|可见性  <br/> |smallint，不为空  <br/> | （在 EnumValue 表上查找） 的可见性： <br/>  2： 专用 <br/>  3： 范围 <br/>  6： 打开 <br/>  仅适用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |外接程序 GUID 如果外接程序与此聊天室。 （类别有外接程序）。  <br/> SiopWhiteList 表中查找外接程序的信息。  <br/> |
|nodeAddedBy  <br/> |int，不为空  <br/> |创建此节点的主要用户的 ID。  <br/> |
|nodeAddedOn  <br/> |bigint，不为空  <br/> |节点创建时间戳。  <br/> |
|nodeUpdatedBy  <br/> |int，不为空  <br/> |做最新的更新，此节点的主要用户的 ID。  <br/> |
|nodeUpdatedOn  <br/> |bigint，不为空  <br/> |此节点的最后更新的时间戳。  <br/> |
|purgedOn  <br/> |datetime  <br/> |最新的清除操作 （删除作用域从 tblScopedPrincipal 表和角色从 tblPrincipalRole 表） 影响此节点的时间。 这使用聊天服务的内部缓存更新机制。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|nodeID  <br/> |为主键。  <br/> |
|行为  <br/> |TblEnumValue.valueID 表中查找与外键。  <br/> |
|可见性  <br/> |TblEnumValue.valueID 表中查找与外键。  <br/> |
|parentID  <br/> |TblNode.nodeID 表中查找与外键。  <br/> |
|siopID  <br/> |TblSiopWhiteList.siopId 表中查找与外键。  <br/> |
   

