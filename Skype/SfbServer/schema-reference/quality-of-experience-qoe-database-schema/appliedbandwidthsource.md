---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。 每条记录代表一个源。
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924848"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表
 
AppliedBandwidthSource 表是一个支持表。 每条记录代表一个源。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |标识来源的唯一编号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |唯一  <br/> |这是带宽帽正在施加的源。 它介绍了其中的带宽限制来自 （例如，"策略服务器"、"打开服务器"或"形式"）。  <br/> |
   

