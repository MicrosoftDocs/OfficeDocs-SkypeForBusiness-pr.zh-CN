---
title: 添加边缘服务器 FQDN
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
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: 必须指定访问边缘服务的完全限定域名 (FQDN)。 如果未在"选择功能"页上选择"使用单个 FQDN IP 地址"选项，则还必须为 Web 会议边缘服务和 A/V 边缘服务指定 &amp; FQDN。
ms.openlocfilehash: 7ddd36b16273ad57c7f4e4107bbf544a40f30964
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815252"
---
# <a name="add-edge-server-fqdn"></a>添加边缘服务器 FQDN
 
必须指定访问边缘服务的完全限定域名 (FQDN)。 如果未在"选择功能"页上选择"使用单个 **FQDN &amp; IP** 地址"选项，则还必须为 Web 会议边缘服务和 A/V 边缘服务指定 FQDN。 
  
此外，如果选择"使用单个 **FQDN &amp; IP** 地址"选项，则必须为每个边缘服务指定不同的端口号 (推荐的端口设置：访问边缘服务为 444，Web 会议边缘服务为 8057，A/V 边缘服务) 为 443。 如果未选择此选项，则可以为所有三个服务使用相同的端口号（如 443）。
  

