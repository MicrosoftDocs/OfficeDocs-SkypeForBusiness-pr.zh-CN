---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 627632625e5898557d650009974fe709ff00e35d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398636"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的合规性状态信息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，不为 null  <br/> |最新处理的合规性事件的 ID。  <br/> |
|activeServerID  <br/> |int，不为 null  <br/> |数据库上保留排除锁的合规性服务器 ID，或者，如果无则为 -1。  <br/> |
|lockExpirationTime  <br/> |datetime2，不为 null  <br/> |锁定到期时间（如果 activeServerID 不为 -1）。  <br/> |
   

