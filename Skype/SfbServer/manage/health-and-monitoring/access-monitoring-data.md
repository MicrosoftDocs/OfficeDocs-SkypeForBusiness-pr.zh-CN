---
title: 在 Skype for Business 服务器中访问监视数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '摘要: 了解 Skype for Business 服务器中使用的监视数据。'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303882"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>在 Skype for Business 服务器中访问监视数据
 
**摘要:** 了解 Skype for Business 服务器中使用的监视数据。
  
监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别之处；也就是说您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。
  
在访问和分析监视数据时, 应考虑的一个工具是 Skype for business 服务器监视报告。 监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。 这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。 在安装并配置了 Skype for business 服务器并已配置监视后, 可通过 skype for business 服务器发布的 "监视报告" 与 skype for business 服务器一起安装并安装 "Skype for Business 服务器部署" 向导。
  
如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。
  
有关详细信息, 请参阅[在 Skype For Business 服务器中安装监视报告](../../deploy/deploy-monitoring/install-monitoring-reports.md)主题。
  

