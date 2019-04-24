---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212633"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的合规性状态信息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，不为 null  <br/> |最新处理的合规性事件的 ID。  <br/> |
|activeServerID  <br/> |int，不为 null  <br/> |如果无则保留排除锁数据库，则为-1 上的合规性服务器 ID。  <br/> |
|lockExpirationTime  <br/> |datetime2，不为 null  <br/> |锁定到期时间，（如果 activeServerID 不为-1）。  <br/> |
   

