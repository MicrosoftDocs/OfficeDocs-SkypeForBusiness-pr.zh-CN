---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 联机证书请求状态页将显示的重要信息从成功创建和发布的联机证书请求的结果。 此页提供唯一标识证书的证书指纹。 默认情况下，选中分配此证书 Skype 的业务服务器证书用法复选框。 如果单击完成时，证书将自动分配给 Lync Server 2013 的过程创建证书申请的步骤中定义，以便。 默认情况下，将分配证书的目的是：
ms.openlocfilehash: 61e62216cd582a07b95a51d05033482699ca2f3d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897606"
---
# <a name="certificate-request-returned"></a>证书请求（已返回）
 
**联机证书请求状态**页将显示的重要信息从成功创建和发布的联机证书请求的结果。 此页提供唯一标识证书的证书指纹。 默认情况下，选中**分配此证书 Skype 的业务服务器证书用法**复选框。 如果单击**完成**时，证书将自动分配给 Lync Server 2013 的过程创建证书申请的步骤中定义，以便。 默认情况下，将分配证书的目的是：
  
- 服务器默认值为相互传输层安全性 (MTLS) 的客户端之间的连接及其他服务器
    
- 内部-web 服务客户端和服务器的内部 Web 服务站点上连接的传输层安全性/安全套接字层 (TLS/SSL)
    
- 外部-web 服务客户端和服务器的外部 Web 服务站点上连接的 TLS/SSL
    
单击**查看证书详细信息**，若要查看确认证书的属性包括您的目的，并已准备好应用并置于服务器上使用证书的证书。
  
单击**完成**以完成联机证书请求进程。 如果您选择了**分配此证书 Skype 的业务服务器证书用法**复选框，将自动分配证书。 如果您选择清除此复选框，就必须分配一个单独的步骤中的证书。 
  
> [!IMPORTANT]
> 如果颁发的证书颁发机构 (CA) 根证书不在计算机的受信任的根证书颁发机构存储，或者中间 CA 证书不在适当的存储区中，您将看到摘要的状态，如下图所示。 您没有分配证书选项。 若要完成证书分配过程，您必须导入发证 CA 根证书和所有中间 CA 证书，然后通过单击证书向导的主页上的**分配**分配证书。
  

