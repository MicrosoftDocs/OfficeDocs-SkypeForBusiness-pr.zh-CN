---
title: 添加控制器 Web 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 是https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。
ms.openlocfilehash: e62adfb080886397de51ff4c51c5fac19878eeff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685315"
---
# <a name="add-director-web-service"></a>添加控制器 Web 服务
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 是https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。
  
如果仅部署单个控制器，则不能替代内部 Web 服务池完全限定的域名（FQDN）。 如果你要为控制器池配置域名系统（DNS）负载平衡，你可以指定不同的内部基 URL （该 URL 必须不同于池 FQDN，例如，内部-\<你的基本 url\>）。
  
你可以指定与内部基础 URL 不同的外部基 URL，以区分域命名。 例如，你的内部域是 contoso.net，但你的外部域名是 contoso.com。 你可以使用 contoso.com 域名定义外部基 URL。 这对于边缘部署的反向代理服务器非常重要。 外部基 URL 域名应与反向代理的 FQDN 的域名相同。 
  

