---
title: VideoMetricsThreshold 表
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
ms.localizationpriority: medium
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳值和可接受值。
ms.openlocfilehash: 9ad1be885a9d922b3884192f543e0e8e1c6415e0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586768"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 表
 
VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳值和可接受值。
  

| **列**                                               | **数据类型**       | **键/索引**  | **Details**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | 主  <br/> | 发出的呼叫的类型。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal (5，2)   <br/> |                | 默认值为 0.05。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal (5，2)   <br/> |                | 默认值为 0.10。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal (5，2)   <br/> |                | 默认值为 5.0。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal (5，2)   <br/> |                | 默认值为 10.0。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal (9，4)   <br/> |                | 默认值为 12.0000。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal (9，4)   <br/> |                | 默认值为 7.0000。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal (5，2)   <br/> |                | 默认值为 5.0。  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal (5，2)   <br/> |                | 默认值为 10.0。  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal (5，2)   <br/> |                | 默认值为 5.0。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal (5，2)   <br/> |                | 默认值为 10.0。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 默认值为 0.05。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 默认值为 0.10。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 默认值为 12。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 默认值为 7。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal (5，2)   <br/> |                | 默认值为 5.00。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal (5，2)   <br/> |                | 默认值为 10.00。  <br/>   |

