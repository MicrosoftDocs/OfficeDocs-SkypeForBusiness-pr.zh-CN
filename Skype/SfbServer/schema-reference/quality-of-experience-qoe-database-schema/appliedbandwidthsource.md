---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。 每条记录代表一个源。
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212353"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是一个支持表。 每条记录代表一个源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |标识来源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |唯一  <br/> |这是带宽帽正在施加的源。 它介绍了其中的带宽限制来自 （例如，"策略服务器"、"打开服务器"或"形式"）。  <br/> |
   

