---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814630"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的合规性状态信息。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，not null  <br/> |最新的已处理合规性事件的 ID。  <br/> |
|activeServerID  <br/> |int，not null  <br/> |在数据库上持有独占锁的合规性服务器 ID，或者，如果没有，则为-1。  <br/> |
|lockExpirationTime  <br/> |datetime2，not null  <br/> |锁过期时间（如果 activeServerID 不是-1）。  <br/> |
   

