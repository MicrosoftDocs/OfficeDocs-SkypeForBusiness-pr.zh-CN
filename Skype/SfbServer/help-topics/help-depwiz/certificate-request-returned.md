---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: “联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。 该页提供了可以唯一标识证书的证书指纹。 默认情况下，选中"将此证书分配给 Skype for Business Server 证书用法"复选框。 如果单击"完成"，证书将自动分配给 Lync Server 2013，用于证书请求的创建步骤中定义的目的。 默认情况下，分配证书的目的如下：
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805142"
---
# <a name="certificate-request-returned"></a>证书请求（已返回）
 
“联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。 该页提供了可以唯一标识证书的证书指纹。 默认情况下，选中"将 **此证书分配给 Skype for Business Server 证书用法** "复选框。 如果单击 **"完成**"，证书将自动分配给 Lync Server 2013，用于证书请求的创建步骤中定义的目的。 默认情况下，分配证书的目的如下：
  
- 相互传输层安全性的服务器默认值 (MTLS) - 与客户端和其他服务器的连接
    
- Web 服务内部 - 内部 Web 服务网站上传输层安全性/安全套接字层 (TLS/SSL) 
    
- Web 服务外部 - 外部 Web 服务网站上 TLS/SSL 的客户端和服务器连接
    
单击“查看证书详细信息”可查看证书，以确认证书属性是否符合您的预期，并确认证书是否已准备好在服务器上应用并投入使用。
  
单击“完成”以完成联机证书请求过程。 如果选中了"将 **此证书** 分配给 Skype for Business Server 证书用法"复选框，将自动分配该证书。 如果选择清除此复选框，则必须通过单独的步骤分配证书。 
  
> [!IMPORTANT]
> 如果颁发证书颁发机构 (CA) 根证书不在计算机的受信任根证书颁发机构存储中，或者中间 CA 证书不在正确的存储中，则会看到摘要状态，如下图所示。 没有分配证书的选项。 要完成证书分配过程，必须导入证书颁发机构根证书和所有中间 CA 证书，然后通过在证书向导主页上单击“分配”来分配证书。
  

