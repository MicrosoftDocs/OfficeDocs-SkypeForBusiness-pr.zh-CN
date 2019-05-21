---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: "\"联机证书请求状态\" 页面向你显示成功创建和发出在线证书请求所产生的重要信息。 此页面提供唯一标识证书的证书指纹。 默认情况下, 将选中 \"将此证书分配给 Skype for business 服务器证书使用情况\" 复选框。 如果单击 \"完成\", 则证书将自动分配给 Skype for business 服务器, 目的是在证书请求的创建步骤中定义。 默认情况下, 将分配证书的目的是:"
ms.openlocfilehash: 02d114ff55360f3e88a866485759510ce5f107c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278019"
---
# <a name="certificate-request-returned"></a>证书请求（已返回）
 
"**联机证书请求状态**" 页面向你显示成功创建和发出在线证书请求所产生的重要信息。 此页面提供唯一标识证书的证书指纹。 默认情况下, 将选中 "**将此证书分配给 Skype for Business 服务器证书使用**情况" 复选框。 如果单击 "**完成**", 则证书将自动分配给 Skype For business 服务器, 目的是在证书请求的创建步骤中定义。 默认情况下, 将分配证书的目的是:
  
- 相互传输层安全性 (MTLS) 的服务器默认值-与客户端和其他服务器的连接
    
- Web 服务内部-用于传输层安全/安全套接字层 (TLS/SSL) 的内部 Web 服务网站上的客户端和服务器连接
    
- 适用于 TLS/SSL 的外部 Web 服务网站上的 Web 服务外部客户端和服务器连接
    
单击 "**查看证书详细信息**" 以查看证书, 以确认证书的属性是否符合你的要求, 以及证书是否已准备好进行应用, 并将其放入服务器上使用。
  
单击 "**完成**" 以完成联机证书请求过程。 如果选中 "**将此证书分配给 Skype for Business 服务器证书使用**情况" 复选框, 则会自动分配证书。 如果您选择清除此复选框, 则必须在单独的步骤中分配证书。 
  
> [!IMPORTANT]
> 如果颁发证书颁发机构 (CA) 根证书不在计算机的受信任的根证书颁发机构存储中, 或者中间 CA 证书不在正确的应用商店中, 你将看到摘要状态, 如下图所示。 您没有分配证书的选项。 若要完成证书分配过程, 必须导入颁发 CA 根证书和任何中间 CA 证书, 然后通过单击 "主证书向导" 页面上的 "**分配**" 来分配证书。
  

