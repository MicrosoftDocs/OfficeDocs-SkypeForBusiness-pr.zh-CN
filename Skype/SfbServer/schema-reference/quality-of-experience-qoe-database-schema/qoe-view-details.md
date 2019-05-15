---
title: QoE 视图列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图介绍用于从 QoE SQL 数据库返回数据的最常见方案。 建议用于构建而不是直接访问数据库表; 的自定义报告视图这是因为视图是更容易保持向后兼容性将来版本。
ms.openlocfilehash: 2726900a1fc31c6e69571123c87137b3291a507e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924862"
---
# <a name="qoe-view-details"></a>QoE 视图列表
 
视图介绍用于从 QoE SQL 数据库返回数据的最常见方案。 建议用于构建而不是直接访问数据库表; 的自定义报告视图这是因为视图是更容易保持向后兼容性将来版本。
  
|**视图名称**|**说明**|
|:-----|:-----|
|[AudioStreamDetail 视图](audiostreamdetail.md) <br/> |在数据库中存储有关每个音频流的信息。  <br/> |
|[MediaLine 视图](medialine.md) <br/> |在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行;但是，会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。  <br/> |
|[NetworkConfigurationSettings 视图](networkconfigurationsettings.md) <br/> |存储有关网络配置信息。  <br/> |
|[会话视图](session-0.md) <br/> |存储有关数据库中包含记录的会话的信息。  <br/> |
|[UserAgent 视图](useragent-0.md) <br/> |存储有关数据库中包含记录的会话中涉及的用户代理的信息。  <br/> |
|[VideoStreamDetail 视图](videostreamdetail.md) <br/> |在数据库中存储有关每个视频流的信息。  <br/> |
   

