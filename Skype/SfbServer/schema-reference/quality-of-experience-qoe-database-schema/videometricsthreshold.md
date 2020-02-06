---
title: VideoMetricsThreshold 表
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 表包含用于视频通话的体验指标质量的最佳值和可接受值。
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804732"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 表
 
VideoMetricsThreshold 表包含用于视频通话的体验指标质量的最佳值和可接受值。
  

| **列**                                               | **数据类型**       | **键/索引**  | **详细信息**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 所发出通话的类型。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | 十进制（5，2）  <br/> |                | 默认值为0.05。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | 十进制（5，2）  <br/> |                | 默认值为0.10。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | 十进制（5，2）  <br/> |                | 默认值为5.0。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | 十进制（5，2）  <br/> |                | 默认值为10.0。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | 十进制（9，4）  <br/> |                | 默认值为12.0000。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | 十进制（9，4）  <br/> |                | 默认值为7.0000。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | 十进制（5，2）  <br/> |                | 默认值为5.0。  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | 十进制（5，2）  <br/> |                | 默认值为 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | 十进制（5，2）  <br/> |                | 默认值为5.0。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | 十进制（5，2）  <br/> |                | 默认值为10.0。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 默认值为0.05。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 默认值为0.10。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 默认值为12。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 默认值为7。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | 十进制（5，2）  <br/> |                | 默认值为5.00。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | 十进制（5，2）  <br/> |                | 默认值为10.00。  <br/>   |

