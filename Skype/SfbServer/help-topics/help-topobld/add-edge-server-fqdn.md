---
title: 添加 Edge Server FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: 你必须为访问边缘服务指定完全限定的域名（FQDN）。 如果未在 "选择功能" 页面上选择&amp; "使用单个 FQDN IP 地址" 选项，则还必须为 Web 会议 Edge 服务和 a/V 边缘服务指定一个 fqdn。
ms.openlocfilehash: c3ccc2f42f090fd3d6f28d22064de98879561a01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821054"
---
# <a name="add-edge-server-fqdn"></a>添加 Edge Server FQDN
 
你必须为访问边缘服务指定完全限定的域名（FQDN）。 如果未在 "**选择功能**" 页面上选择 "**使用单个&amp; FQDN IP 地址**" 选项，则还必须为 Web 会议 Edge 服务和 A/V 边缘服务指定一个 fqdn。
  
同样，如果你选择 "**使用单个 FQDN &amp; IP 地址**" 选项，则必须为每个 Edge 服务指定不同的端口号（推荐的端口设置：444用于访问边缘服务，8057用于 Web 会议 Edge 服务，443用于 a/V 边缘服务）。 如果未选择此选项，则可以对所有三种服务使用相同的端口号（如443）。
  

