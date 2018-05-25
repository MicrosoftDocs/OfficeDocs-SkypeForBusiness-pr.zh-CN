---
title: 添加控制器 Web 服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="add-director-web-service"></a>添加控制器 Web 服务
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
  
如果要部署一个控制器，无法覆盖内部 Web 服务池完全限定的域名 (FQDN)。 如果要配置域名系统 (DNS) 负载平衡的控制器池，则可以指定不同的内部基本 URL (哪些必须与池 FQDN 不同，可能是，例如，内部-\<基 URL\>)。
  
您可以指定不同的外部基 URL 从您的内部基本 URL 区分域命名。 例如，内部域 contoso.net，但在您的外部域的名称是 contoso.com。将使用的 contoso.com 域的名称来定义外部基 URL。 这是重要边缘部署的反向代理服务器。 外部基 URL 域名称应为反向代理服务器的 FQDN 的域名相同。 
  

