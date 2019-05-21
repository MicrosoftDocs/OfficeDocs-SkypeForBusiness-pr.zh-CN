---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 没有 collocated A/V 会议服务的中心网站的所有企业版前端服务器都可以使用相同的独立 A/V 会议池。 对于每个 A/V 会议池, 你必须为该池指定完全限定的域名 (FQDN), 以及它将仅具有单个 A/V 会议服务器还是具有多个负载平衡的 A/V 会议服务器。
ms.openlocfilehash: b854e7ecaeed13bd7df15c3ac0439323f3deb311
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304994"
---
# <a name="add-av-mcu-pool"></a>添加 A/V MCU 池
 
没有 collocated A/V 会议服务的中心网站的所有企业版前端服务器都可以使用相同的独立 A/V 会议池。 对于每个 A/V 会议池, 你必须为该池指定完全限定的域名 (FQDN), 以及它将仅具有单个 A/V 会议服务器还是具有多个负载平衡的 A/V 会议服务器。
  
> [!IMPORTANT]
> 不能将单个服务器池转换为多服务器池。 如果稍后确定你的组织需要多服务器池, 则必须删除单服务器池, 然后添加多服务器池。 
  
> [!TIP]
> 如果你计划在将来实现 A/V 会议池, 请选择 "**多台计算机池**"。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当你准备好将更多计算机添加到池中时, 你必须再次使用拓扑生成器来定义新的池成员、发布新拓扑, 然后通过 Skype for Business 服务器部署向导设置新的 A/V 会议池成员。 A/V 会议服务器池是唯一的, 因为它们不需要负载平衡器即可创建池。 A/V 会议池内部负载平衡, 并且不需要其他硬件。 
  

