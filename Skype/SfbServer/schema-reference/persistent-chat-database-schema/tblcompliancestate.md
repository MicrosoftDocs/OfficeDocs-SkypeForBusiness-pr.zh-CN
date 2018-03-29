---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的法规遵从性状态的信息。
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的法规遵从性状态的信息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，不为空  <br/> |最新的处理法规遵从性事件 ID。  <br/> |
|activeServerID  <br/> |int，不为空  <br/> |如果没有保存在数据库中，则为-1 的排它锁的法规遵从性服务器的 ID。  <br/> |
|lockExpirationTime  <br/> |datetime2，不为空  <br/> |锁定到期时间 （如果 activeServerID 不是-1）。  <br/> |
   

