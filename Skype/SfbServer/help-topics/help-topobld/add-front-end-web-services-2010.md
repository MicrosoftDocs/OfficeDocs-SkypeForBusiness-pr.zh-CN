---
title: 添加前端 Web 服务 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: ad21132f26abd03355cb214811a67dfe0f42add2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services-2010"></a>添加前端 Web 服务 2010
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
  
不能重写内部 Web 服务池完全合格的域名称 (FQDN) 标准版服务器。 如果您在配置域名系统 (DNS) 负载平衡的前端企业版池，您可以指定不同的内部基本 URL (它必须不同于池的 FQDN，并可能是，例如，内部的\<基 URL\>)。
  
您可以指定不同的外部的基 URL 从您内部的基 URL 来区分域命名它。 例如，您的内部域是 contoso.net，但外部域名 contoso.com。将通过使用 contoso.com 域的名称来定义外部的基 URL。 这是非常重要的反向代理服务器的边缘部署。 外部的基 URL 域名称应与反向代理服务器的 FQDN 的域的名称相同。 即时消息和状态要求对前端池的 HTTP 访问。
  

