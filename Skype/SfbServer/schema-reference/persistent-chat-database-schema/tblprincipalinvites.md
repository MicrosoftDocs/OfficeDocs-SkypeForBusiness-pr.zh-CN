---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
ms.openlocfilehash: fa90d112ce7b3397f055023034888b45bc5b8bcabc7948f7c4af0bb59788c2d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318685"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|invID  <br/> |int，不为 null  <br/> |从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。  <br/> |
|nodeID  <br/> |int，不为 null  <br/> |节点 ID（仅聊天室）。  <br/> |
|createdOn  <br/> |datetime，不为 null  <br/> |创建的时间。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |主键。  <br/> |
|prinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
|nodeID  <br/> |其查找包含在 tblNode.nodeID 表中的外键。  <br/> |
   

