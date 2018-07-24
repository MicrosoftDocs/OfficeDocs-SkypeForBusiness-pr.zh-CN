---
title: 添加前端 Web 服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: dbad738a6bce55d308adc1ee48b04b56c2cabb2f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016831"
---
# <a name="add-front-end-web-services"></a>添加前端 Web 服务
 
基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
  
无法覆盖内部 Web 服务池完全限定的域名 (FQDN) 的 Standard Edition server。 如果要配置域名系统 (DNS) 负载平衡对于 Enterprise Edition 前端池，则可以指定其他内部基本 URL，该节点必须是池 FQDN 不同 (例如，内部-\<基 URL\>)。
  
您可以指定不同的外部基 URL 从您的内部基本 URL 区分域命名。 例如，内部域 contoso.net，但在您的外部域的名称是 contoso.com。 您将定义外部基 URL 使用的 contoso.com 域的名称。 这是重要边缘部署的反向代理服务器。 外部基 URL 域名称应为反向代理服务器的 FQDN 的域名相同。 即时消息和状态需要对前端池的 HTTP 访问。
  

