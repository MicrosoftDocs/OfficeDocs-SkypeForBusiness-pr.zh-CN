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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811440"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |标识源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar （256）  <br/> |唯一  <br/> |这是所强加的带宽上限的来源。 它介绍带宽限制的来源（例如，"策略服务器"、"转换服务器" 或 "模态"）。  <br/> |
   

