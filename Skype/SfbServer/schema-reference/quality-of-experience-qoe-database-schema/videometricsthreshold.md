---
title: VideoMetricsThreshold 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳和可接受值。
ms.openlocfilehash: 382509826758af748d9e4eb111d4c3f6f86d52b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904221"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 表
 
VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳和可接受值。
  

| **列**                                               | **数据类型**       | **键/索引**  | **详细信息**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 发出的呼叫的类型。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | 默认值为 0.05。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | 默认值为 0.10。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | 默认值为 5.0。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | 默认值为 10.0。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | 默认值为 12.0000。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | 默认值为 7.0000。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | 默认值为 5.0。  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal(5,2)  <br/> |                | 默认值为 10.0 /  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 默认值为 5.0。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 默认值为 10.0。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 默认值为 0.05。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 默认值为 0.10。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 默认值为 12。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 默认值为 7。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 默认值为 5.00。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 默认值为 10.00。  <br/>   |

