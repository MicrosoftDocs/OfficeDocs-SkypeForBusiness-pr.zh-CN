---
title: 添加控制器文件存储
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: ab724e0d7d7d6cdbf4bc3c67074d908debb7605c
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059495"
---
# <a name="add-director-file-store"></a>添加控制器文件存储
 
必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
  
> [!IMPORTANT]
> 向拓扑中添加控制器时，拓扑发布需要相应的访问权限以在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器并发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。 
  
有关文件共享的存储支持的详细信息，请参阅[文件存储支持](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)的可支持性文档和[SQL Server 数据和日志文件放置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)在部署文档中。 有关详细信息并置的文件共享，请参阅可支持性文档中的[Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 。 有关为控制器设计拓扑的详细信息，请参阅部署文档中的[定义单个控制器拓扑生成器中](http://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)。
  

