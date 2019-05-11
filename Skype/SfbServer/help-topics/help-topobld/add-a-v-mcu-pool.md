---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 所有 Enterprise Edition 前端服务器的中央站点没有并置的 A / V 会议服务可以使用相同的独立 A / V 会议池。 每个 a / V 会议池，必须指定完全限定的域名 (FQDN) 的池以及是否将具有单个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
ms.openlocfilehash: a5f61e3bbf8def833163ea15b97e781c348191bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886787"
---
# <a name="add-av-mcu-pool"></a>添加 A/V MCU 池
 
所有 Enterprise Edition 前端服务器的中央站点没有并置的 A / V 会议服务可以使用相同的独立 A / V 会议池。 每个 a / V 会议池，必须指定完全限定的域名 (FQDN) 的池以及是否将具有单个 A / V 会议服务器或多个负载平衡 A / V 会议服务器。
  
> [!IMPORTANT]
> 您不能将单服务器池转换为多服务器池。 如果您以后决定您的组织需要多服务器池，必须删除单服务器池，并将多服务器池。 
  
> [!TIP]
> 如果您打算实现 A / V 会议池将来，选择**多个计算机池**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当您准备好以后向池中添加更多计算机时，您必须拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置新的 A / V 会议池成员通过 Skype 的业务 Server 部署向导。 A / V 会议服务器池都是唯一的它们不需要加载平衡器来创建池。 A / V 会议池内部负载平衡和不需要额外的硬件。 
  

