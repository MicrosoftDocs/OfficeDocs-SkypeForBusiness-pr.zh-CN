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
ms.openlocfilehash: ada345c95f2754cab927a3469660404256d7c53dac7bca3b2f62bf26ce3fca8c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290880"
---
# <a name="add-edge-server-fqdn"></a>添加边缘服务器 FQDN
 
必须指定访问边缘服务的完全限定域名 (FQDN)。 如果未在"选择功能"页上选择"使用单个 **FQDN &amp; IP** 地址"选项，则还必须为 Web 会议边缘服务和 A/V 边缘服务指定 FQDN。 
  
此外，如果选择了"使用单个 **FQDN &amp; IP** 地址"选项，则必须为每个边缘服务 (建议端口设置指定不同的端口号：444 用于访问边缘服务，8057 用于 Web 会议边缘服务，443 用于 A/V 边缘服务) 。 如果未选择此选项，则可以为所有三个服务使用相同的端口号（如 443）。
  

