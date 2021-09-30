---
title: 添加控制器 Web 服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 `https://pool01.contoso.net` ，则基 URL 为 `pool01.contoso.net` 。
ms.openlocfilehash: aaa3451e842700cbc1d98cc72b08fc53ccff1555
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015326"
---
# <a name="add-director-web-service"></a>添加控制器 Web 服务
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 `https://pool01.contoso.net` ，则基 URL 为 `pool01.contoso.net` 。
  
如果仅部署单个控制器，则不能覆盖内部 Web 服务池完全限定的域名 (FQDN)。 如果要为控制器池配置域名系统 (DNS) 负载平衡，可以指定不同的内部基 URL (该 URL 必须与池 FQDN 不同，例如，可以是 internal- \<your base URL\>) 。
  
可以指定与内部基 URL 不同的外部基 URL 以区分域命名。 例如，内部域是 `contoso.net` ，但外部域名是 `contoso.com` 。 您将使用域名定义外部基 `contoso.com` URL。 这对于边缘部署中的反向代理服务器非常重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 
  

