---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含对象树 (类别或聊天室节点) 在控制面板和管理 cmdlet 中进行管理。
ms.openlocfilehash: 0935e5cdec8db7f7ce33b07dcf287c1a8bd5d749
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776142"
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含对象树 (类别或聊天室节点) 在控制面板和管理 cmdlet 中进行管理。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为 null  <br/> |节点 ID（唯一编号）。  <br/> |
|nodeGuid  <br/> |GUID，不为 null  <br/> |节点 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父节点 ID。根节点（ID 为 1）将其自身用作父项。  <br/> |
|nodeType  <br/> |bit，不为 null  <br/> |如果节点是类别，则为 True。  <br/> 如果节点是聊天室，则为 False。  <br/> |
|nodeName  <br/> |nvarchar (256)，不为 null  <br/> |节点名称。  <br/> |
|nodeDesc  <br/> |nvarchar (256)，不为 null  <br/> |节点描述。  <br/> |
|invite  <br/> |bit  <br/> | 针对类别： <br/>  如果邀请打开，则为 True。 <br/>  如果邀请关闭，则为 False。 <br/>  针对聊天室： <br/>  如果邀请关闭，则为 False（覆盖父类别）。 <br/>  如果邀请设置是继承自父类别，则为 Null。 <br/> |
|已记录  <br/> |bit  <br/> | 针对类别： <br/>  如果聊天历史记录打开，则为 True。 <br/>  如果聊天历史记录关闭，则为 False。 <br/>  针对聊天室： <br/>  Null。 <br/> |
|filePost  <br/> |bit  <br/> | 针对类别： <br/>  如果允许文件上载，则为 True。 <br/>  如果不允许文件上载，则为 False。 <br/>  针对聊天室： <br/>  Null。 <br/> |
|disabled  <br/> |bit，不为 null  <br/> |如果聊天室已禁用，则为 True。仅适用于聊天室。（对于类别则为 False。）  <br/> |
|behavior  <br/> |smallint，不为 null  <br/> | 行为（在 EnumValue 表中查找）： <br/>  4：普通（普通聊天室）。 <br/>  5：大会堂（大会堂聊天室，仅演示者可以参与）。 <br/>  仅适用于聊天室。 <br/> |
|visibility  <br/> |smallint，不为 null  <br/> | 可见性（在 EnumValue 表中查找）： <br/>  2：专用 <br/>  3：范围 <br/>  6：打开 <br/>  仅适用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |如果外接程序与此聊天室关联，则为外接程序 GUID。（类别没有外接程序。）  <br/> 外接程序信息在 SiopWhiteList 表中进行查找。  <br/> |
|nodeAddedBy  <br/> |int，不为 null  <br/> |创建此节点的主体的 ID。  <br/> |
|nodeAddedOn  <br/> |bigint，不为 null  <br/> |节点创建的时间戳。  <br/> |
|nodeUpdatedBy  <br/> |int，不为 null  <br/> |对此节点执行最新更新的主体的 ID。  <br/> |
|nodeUpdatedOn  <br/> |bigint，不为 null  <br/> |此节点最新更新的时间戳。  <br/> |
|purgedOn  <br/> |datetime  <br/> |影响此节点的最近一次清除操作（从 tblScopedPrincipal 表中删除范围，从 tblPrincipalRole 表中删除角色）的时间。 这由聊天服务的内部缓存更新机制使用。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|nodeID  <br/> |主键。  <br/> |
|behavior  <br/> |在 tblEnumValue.valueID 表中查找的外键。  <br/> |
|visibility  <br/> |在 tblEnumValue.valueID 表中查找的外键。  <br/> |
|parentID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
|siopID  <br/> |在 tblSiopWhiteList.siopId 表中查找的外键。  <br/> |
   

