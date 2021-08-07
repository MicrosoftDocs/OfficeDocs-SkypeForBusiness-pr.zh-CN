---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。
ms.openlocfilehash: fcb0323b1e6775b20a8ca4d269bcc8eecdc055b73d5a93a490e97f8a1af44b11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305344"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |主  <br/> |标识来源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)   <br/> |独特  <br/> |这是所设定的带宽限制的来源。 它描述带宽限制来自何处 (例如，"策略服务器"、"TURN 服务器"或"形式") 。  <br/> |
   

