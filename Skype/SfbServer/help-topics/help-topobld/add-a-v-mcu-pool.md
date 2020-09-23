---
title: 添加 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 中央站点中没有并置的 A/V 会议服务的所有 Enterprise Edition 前端服务器可使用相同的独立 A/V 会议池。对于每个 A/V 会议池，必须为其指定完全限定域名 (FQDN)，并指定该池将具有单台 A/V 会议服务器还是多台负载平衡的 A/V 会议服务器。
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217473"
---
# <a name="add-av-mcu-pool"></a>添加 A/V MCU 池
 
中央站点中没有并置的 A/V 会议服务的所有 Enterprise Edition 前端服务器可使用相同的独立 A/V 会议池。对于每个 A/V 会议池，必须为其指定完全限定域名 (FQDN)，并指定该池将具有单台 A/V 会议服务器还是多台负载平衡的 A/V 会议服务器。
  
> [!IMPORTANT]
> 无法将单个服务器的池转换为多个服务器的池。如果以后确定组织需要多个服务器的池，则必须先删除单个服务器的池，然后添加多个服务器的池。 
  
> [!TIP]
> 如果计划将来实施 A/V 会议池，请选择“多个计算机池”****。 即使将池定义为具有两个或更多负载平衡的计算机，仍可以创建单一计算机池并为该单一计算机创建池 FQDN。 当您准备好将更多计算机添加到池时，您必须再次使用拓扑生成器来定义新的池成员，发布新的拓扑，然后通过 Skype for Business Server 部署向导设置新的 A/V 会议池成员。 A/V 会议服务器池是唯一的，因此无需负载平衡器就可以创建池。 A/V 会议池内部可进行负载平衡，无需其他硬件。 
  

