---
title: 添加前端 Web 服务 2010
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 `https://pool01.contoso.net`，则基 URL 为 `pool01.contoso.net`。
ms.openlocfilehash: 5a4de05a5cf8c46c8c61a8b5bb54c4ebe9335f35
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399126"
---
# <a name="add-front-end-web-services-2010"></a>添加前端 Web 服务 2010
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 `https://pool01.contoso.net`，则基 URL 为 `pool01.contoso.net`。
  
不能覆盖内部 Web 服务池的完全限定域名 (FQDN) 服务器Standard Edition FQDN。 如果要为 Enterprise Edition 前端池配置域名系统 (DNS) 负载平衡，可以指定一个不同的内部基 URL (该 URL 必须不同于池 FQDN，例如 internal-\<your base URL\>) 。
  
可以指定与内部基 URL 不同的外部基 URL 以区分域命名。 例如，内部域是 ， `contoso.net`但外部域名是 `contoso.com`。 您可以使用 contoso.com 域名来定义外部基 URL。 这对于边缘部署中的反向代理服务器非常重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 即时消息和状态要求对前端池具有 HTTP 访问权限。
  

