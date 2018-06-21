---
title: 添加前端文件存储
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: 必须为 Standard Edition 服务器或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: b8e29253a3ed918755d29ff6d1432f879a6164ea
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979937"
---
# <a name="add-front-end-file-store"></a>添加前端文件存储
 
必须为 Standard Edition 服务器或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
  
> [!IMPORTANT]
> 文件共享不能位于 Enterprise Edition 前端服务器，但可以位于 Standard Edition Server。 
  
> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 
  
> [!IMPORTANT]
> 向拓扑中添加 Enterprise 前端池或 Standard Edition 服务器时，拓扑生成器必须能够在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。 
  
有关文件共享的存储支持的详细信息，请参阅[文件存储支持](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)的可支持性文档和[SQL Server 数据和日志文件放置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)在部署文档中。 有关详细信息并置的文件共享，请参阅可支持性文档中的[Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 。 有关设计的 Enterprise Edition 前端池的拓扑的详细信息，请参阅部署文档中的[Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。
  

