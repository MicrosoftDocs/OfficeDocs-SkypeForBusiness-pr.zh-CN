---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295109"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |标识源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |唯一  <br/> |这是所强加的带宽上限的来源。 它介绍带宽限制的来源 (例如, "策略服务器"、"转换服务器" 或 "模态")。  <br/> |
   

