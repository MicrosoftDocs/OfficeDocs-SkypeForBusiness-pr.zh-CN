---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315418"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的合规性状态信息。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，不为 null  <br/> |最新处理的合规性事件的 ID。  <br/> |
|activeServerID  <br/> |int，不为 null  <br/> |数据库上保留排除锁的合规性服务器 ID，或者，如果无则为 -1。  <br/> |
|lockExpirationTime  <br/> |datetime2，不为 null  <br/> |锁定到期时间（如果 activeServerID 不为 -1）。  <br/> |
   

