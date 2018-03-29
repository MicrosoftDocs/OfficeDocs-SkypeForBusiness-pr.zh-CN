---
title: 添加 A / V MCU 池
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 所有企业版前端服务器的中心站点没有并入 A / V 会议服务可以使用相同的独立 A / V 会议池。 对于每个 A / V 会议池，必须指定完全限定的域名称 (FQDN) 的池和是否会有一个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-av-mcu-pool"></a>添加 A / V MCU 池
 
所有企业版前端服务器的中心站点没有并入 A / V 会议服务可以使用相同的独立 A / V 会议池。 对于每个 A / V 会议池，必须指定完全限定的域名称 (FQDN) 的池和是否会有一个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
  
> [!IMPORTANT]
> 不能将单服务器池转换到多服务器池。 如果您以后决定您的组织需要一个多服务器池，您必须删除该单服务器池，，然后添加多个服务器池。 
  
> [!TIP]
> 如果您计划如何实现 A / V 会议池以后，选择**多个计算机池**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当准备好以后向池中添加更多的计算机时，您必须拓扑生成器再次以定义新的池成员发布新的拓扑，然后设置了新的 / V 会议池成员通过 Skype 业务服务器部署向导。 A / V 会议服务器池都是唯一的因为它们不需要加载平衡器来创建池。 A / V 会议池内部负载平衡，并不需要额外的硬件。 
  

