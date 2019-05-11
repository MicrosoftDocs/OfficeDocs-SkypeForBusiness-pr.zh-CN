---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含的对象树 （包含类别或聊天室节点） 在控制面板和管理 cmdlet 管理。
ms.openlocfilehash: 333ea267c4e65f20d5c4dd15f115b40ec162e209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929831"
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含的对象树 （包含类别或聊天室节点） 在控制面板和管理 cmdlet 管理。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为 null  <br/> |节点 ID （唯一编号）。  <br/> |
|nodeGuid  <br/> |GUID，不为 null  <br/> |节点 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父节点 ID。 （与 ID 为 1) 的根节点包括本身作为父以及。  <br/> |
|nodeType  <br/> |bit，不为 null  <br/> |如果节点是类别，则为 true。  <br/> 如果节点是聊天室，则为 false。  <br/> |
|节点名称  <br/> |nvarchar (256)，不为 null  <br/> |节点名称。  <br/> |
|nodeDesc  <br/> |nvarchar (256)，不为 null  <br/> |节点描述。  <br/> |
|邀请  <br/> |bit  <br/> | 针对类别： <br/>  如果邀请打开，则为 true。 <br/>  如果邀请关闭，则为 false。 <br/>  针对聊天室： <br/>  如果邀请关闭 false （覆盖父类别）。 <br/>  如果邀请设置继承自父类别，则为 null。 <br/> |
|记录  <br/> |bit  <br/> | 针对类别： <br/>  如果聊天历史记录上，则为 true。 <br/>  如果聊天历史记录处于关闭状态，则为 false。 <br/>  针对聊天室： <br/>  Null。 <br/> |
|filePost  <br/> |bit  <br/> | 针对类别： <br/>  如果允许文件上载，则为 true。 <br/>  如果不允许文件上载，则为 false。 <br/>  针对聊天室： <br/>  Null。 <br/> |
|禁用  <br/> |bit，不为 null  <br/> |如果禁用该聊天室，则为 true。 仅适用于聊天室。 (类别 false)。  <br/> |
|行为  <br/> |smallint，不为 null  <br/> | 行为 （在 EnumValue 表中查找）： <br/>  4： 普通 （普通聊天室）。 <br/>  5： 大会堂 （大会堂聊天室，仅演示者可以参与）。 <br/>  仅适用于聊天室。 <br/> |
|可见性  <br/> |smallint，不为 null  <br/> | 可见性 （在 EnumValue 表上查找）： <br/>  2： 专用 <br/>  3： 范围 <br/>  6： 打开 <br/>  仅适用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |外接程序 GUID 如果外接程序与此聊天室。 （类别无需外接程序）。  <br/> 外接程序信息在 SiopWhiteList 表中查找。  <br/> |
|nodeAddedBy  <br/> |int，不为 null  <br/> |创建此节点的主体的 ID。  <br/> |
|nodeAddedOn  <br/> |bigint，不为 null  <br/> |节点创建的时间戳。  <br/> |
|nodeUpdatedBy  <br/> |int，不为 null  <br/> |执行此节点最新更新的主体的 ID。  <br/> |
|nodeUpdatedOn  <br/> |bigint，不为 null  <br/> |此节点最新更新的时间戳。  <br/> |
|purgedOn  <br/> |datetime  <br/> |最新的清除操作 （删除 tblScopedPrincipal 表中的范围和 tblPrincipalRole 表中的角色） 影响此节点的时间。 使用聊天服务的内部缓存更新机制。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|nodeID  <br/> |主键。  <br/> |
|行为  <br/> |在 tblEnumValue.valueID 表中查找的外键。  <br/> |
|可见性  <br/> |在 tblEnumValue.valueID 表中查找的外键。  <br/> |
|parentID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
|siopID  <br/> |在 tblSiopWhiteList.siopId 表中查找的外键。  <br/> |
   

