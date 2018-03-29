---
title: 证书申请 （返回）
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
description: 联机的证书申请状态页将显示重要信息成功创建和颁发联机证书请求而产生。 此页提供唯一标识证书的证书指纹。 默认情况下被选中复选框分配到 Skype 业务服务器证书用途的证书。 如果您单击完成，该证书将自动分配给 Lync Server 2013 期间创建的证书申请的步骤定义的目的。 默认情况下，将分配证书的目的是：
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-returned"></a>证书申请 （返回）
 
**联机的证书申请状态**页将显示重要信息成功创建和颁发联机证书请求而产生。 此页提供唯一标识证书的证书指纹。 默认情况下，**分配到企业服务器证书用途的 Skype 此证书**复选框被选中。 如果单击**完成**后，该证书将自动分配给 Lync Server 2013 期间创建的证书申请的步骤定义的目的。 默认情况下，将分配证书的目的是：
  
- 服务器默认值用于相互传输层安全性 (MTLS)-连接到客户端和其他服务器
    
- 内部的 web 服务在内部网站上的客户端和服务器连接的传输层安全性/安全套接字层 (TLS/SSL) 服务网站
    
- 外部的 web 服务在外部网站上的客户端和服务器连接的 TLS/SSL 服务网站
    
请单击要查看的证书，确认证书的属性是您想，且证书已准备好应用，并将投入使用的服务器上**查看证书详细信息**。
  
单击**完成**以完成联机证书请求过程。 如果您选择**分配到 Skype 业务服务器证书用法此证书**复选框，将自动分配证书。 如果您选择以清除此复选框，您必须分配一个单独的步骤中的证书。 
  
> [!IMPORTANT]
> 如果颁发证书颁发机构 (CA) 的根证书没有在计算机的受信任根证书颁发机构存储中，或者如果中间 CA 证书不正确的存储区中，您将看到摘要状态，如下图中所示。 您没有选择将证书分配。 要完成证书分配过程中，必须颁发 CA 根证书和任何中间 CA 证书，导入，然后将证书分配主证书向导页面上单击**分配**。
  

