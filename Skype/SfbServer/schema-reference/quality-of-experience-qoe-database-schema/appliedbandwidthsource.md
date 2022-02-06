---
title: AppliedBandwidthSource 表
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。
---

# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |主  <br/> |标识来源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)   <br/> |独特  <br/> |这是所设定的带宽限制的来源。 它描述带宽限制来自何处 (例如，"策略服务器"、"TURN 服务器"或"形式") 。  <br/> |
   

