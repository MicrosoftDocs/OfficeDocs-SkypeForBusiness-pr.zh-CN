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
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳值和可接受值。
ms.openlocfilehash: 15bf482412973fe4b3a0178be6ecdcc593c762e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821372"
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

