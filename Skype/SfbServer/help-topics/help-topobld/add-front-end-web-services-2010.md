---
title: 添加前端 Web 服务 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: ab64d473c3b0493e7d578c5cfa9f55475d1d06ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897658"
---
# <a name="add-front-end-web-services-2010"></a>添加前端 Web 服务 2010
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
  
无法覆盖内部 Web 服务池完全限定的域名 (FQDN) 的 Standard Edition Server。 如果要配置域名系统 (DNS) 负载平衡对于 Enterprise Edition 前端池，则可以指定不同的内部基本 URL (哪些必须与池 FQDN 不同，可能是，例如，内部-\<基 URL\>)。
  
您可以指定不同的外部基 URL 从您的内部基本 URL 区分域命名。 例如，内部域 contoso.net，但在您的外部域的名称是 contoso.com。 将使用的 contoso.com 域的名称来定义外部基 URL。 这是重要边缘部署的反向代理服务器。 外部基 URL 域名称应为反向代理服务器的 FQDN 的域名相同。 即时消息和状态需要对前端池的 HTTP 访问。
  

