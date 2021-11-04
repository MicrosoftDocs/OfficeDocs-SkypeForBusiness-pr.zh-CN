---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: “联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。 该页提供了可以唯一标识证书的证书指纹。 默认情况下，选中"为此证书分配Skype for Business Server证书用法"复选框。 如果单击"完成"，证书将自动分配给Skype for Business Server证书请求创建步骤期间定义的目的。 默认情况下，分配证书的目的如下：
ms.openlocfilehash: 7f92c95fa5d1588d7563791dca38da46c550048b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740048"
---
# <a name="certificate-request-returned"></a>证书请求（已返回）
 
“联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。 该页提供了可以唯一标识证书的证书指纹。 默认情况下，选中"为此 **证书分配Skype for Business Server证书用法**"复选框。 如果单击 **"完成**"，证书将自动分配给Skype for Business Server证书请求创建步骤期间定义的目的。 默认情况下，分配证书的目的如下：
  
- 相互传输层安全性服务器的默认 (MTLS) - 与客户端和其他服务器的连接
    
- Web 服务内部 - 内部 Web 服务网站上传输层安全性/安全套接字层与 TLS/SSL (客户端和服务器) 
    
- 外部 Web 服务 - TLS/SSL 的外部 Web 服务站点上的客户端和服务器连接
    
单击“查看证书详细信息”可查看证书，以确认证书属性是否符合您的预期，并确认证书是否已准备好在服务器上应用并投入使用。
  
单击“完成”以完成联机证书请求过程。 如果选中"分配此证书以 **Skype for Business Server证书用法"** 复选框，将自动分配证书。 如果选择清除此复选框，则必须通过单独的步骤分配证书。 
  
> [!IMPORTANT]
> 如果证书颁发机构 (CA) 根证书不在计算机的受信任的根证书颁发机构存储中，或者中间 CA 证书不在正确的存储中，则会看到摘要状态，如下图所示。 没有分配证书的选项。 要完成证书分配过程，必须导入证书颁发机构根证书和所有中间 CA 证书，然后通过在证书向导主页上单击“分配”来分配证书。
  

