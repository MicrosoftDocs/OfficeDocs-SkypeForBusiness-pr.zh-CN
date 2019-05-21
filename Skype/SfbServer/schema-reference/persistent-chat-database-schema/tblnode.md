---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含 "控制面板" 和 "管理" cmdlet 中托管的对象树 (包含类别或聊天室节点)。
ms.openlocfilehash: fedb7f88cd9b5a634fe9a6b34f746e61e6ee9be7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295347"
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含 "控制面板" 和 "管理" cmdlet 中托管的对象树 (包含类别或聊天室节点)。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|a  <br/> |int, not null  <br/> |节点 ID (唯一编号)。  <br/> |
|nodeGuid  <br/> |GUID, not null  <br/> |节点 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父项的节点 ID。 根节点 (ID 为 1) 也将其本身包括到父节点。  <br/> |
|nodeType  <br/> |位, not null  <br/> |如果节点是类别, 则为 True。  <br/> 如果节点是聊天室, 则为 False。  <br/> |
|nodeName  <br/> |nvarchar (256), not null  <br/> |节点名称。  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |节点说明。  <br/> |
|邀请  <br/> |bit  <br/> | 对于类别: <br/>  如果邀请已打开, 则为 True。 <br/>  如果邀请已关闭, 则为 False。 <br/>  对于会议室: <br/>  如果邀请已关闭, 则为 False (覆盖父类别)。 <br/>  如果 "邀请" 设置继承自父类别, 则为 Null。 <br/> |
|身份  <br/> |bit  <br/> | 对于类别: <br/>  如果打开聊天记录, 则为 True。 <br/>  如果聊天历史记录处于关闭状态, 则为 False。 <br/>  对于会议室: <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | 对于类别: <br/>  如果允许文件上载, 则为 True。 <br/>  如果不允许文件上载, 则为 False。 <br/>  对于会议室: <br/>  Null. <br/> |
|禁用  <br/> |位, not null  <br/> |如果禁用聊天室, 则为 True。 仅适用于聊天室。 (False 表示类别。)  <br/> |
|现象  <br/> |smallint, not null  <br/> | 行为 (在 EnumValue 表中查看): <br/>  4: 普通 (正常聊天室)。 <br/>  5: Auditorium (Auditorium 聊天室, 只有演示者可以参与)。 <br/>  仅适用于聊天室。 <br/> |
|了解  <br/> |smallint, not null  <br/> | 可见性 (在 EnumValue 表上查看): <br/>  2: 私密 <br/>  3: 范围 <br/>  6: 打开 <br/>  仅适用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |加载项 GUID (如果外接程序与此聊天室相关联)。 (类别没有外接程序。)  <br/> 外接程序信息在 SiopWhiteList 表中查找。  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |创建此节点的主体的 ID。  <br/> |
|nodeAddedOn  <br/> |bigint, not null  <br/> |节点创建的时间戳。  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |执行此节点的最新更新的主体的 ID。  <br/> |
|nodeUpdatedOn  <br/> |bigint, not null  <br/> |此节点的最新更新的时间戳。  <br/> |
|purgedOn  <br/> |datetime  <br/> |最新的清除操作 (从 tblScopedPrincipal 表的作用域和 tblPrincipalRole 表中的角色删除) 影响此节点的时间。 此功能由聊天服务的内部缓存更新机制使用。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|a  <br/> |主键。  <br/> |
|现象  <br/> |TblEnumValue 表中的 lookup 的外键。  <br/> |
|了解  <br/> |TblEnumValue 表中的 lookup 的外键。  <br/> |
|parentID  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
|siopID  <br/> |TblSiopWhiteList 表中的 lookup 的外键。  <br/> |
   

