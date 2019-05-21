---
title: 添加前端 Web 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如, 如果池的 Web 服务的完整 URL 是https://pool01.contoso.net, 则基 URL 为 pool01.contoso.net。
ms.openlocfilehash: 3317df51fcacd17de8c1ce3f40163f2ce63dc13f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275281"
---
# <a name="add-front-end-web-services"></a>添加前端 Web 服务
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如, 如果池的 Web 服务的完整 URL 是https://pool01.contoso.net, 则基 URL 为 pool01.contoso.net。
  
不能替代标准版服务器的内部 Web 服务池完全限定的域名 (FQDN)。 如果要为企业版前端池配置域名系统 (DNS) 负载平衡, 可以指定不同的内部基 URL, 该 URL 必须不同于池 FQDN (例如, 内部-\<你的基本 url\>)。
  
你可以指定与内部基础 URL 不同的外部基 URL, 以区分域命名。 例如, 你的内部域是 contoso.net, 但你的外部域名是 contoso.com。 你将使用 contoso.com 域名定义外部基 URL。 这对于边缘部署的反向代理服务器非常重要。 外部基 URL 域名应与反向代理的 FQDN 的域名相同。 即时消息和状态要求具有对前端池的 HTTP 访问权限。
  

