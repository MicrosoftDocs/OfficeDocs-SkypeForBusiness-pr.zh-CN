---
title: 添加控制器文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: 必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 128069ee17410e8b7c0a0e9cd54f917a119b5b40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886591"
---
# <a name="add-director-file-store"></a>添加控制器文件存储

必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。

> [!IMPORTANT]
> 向拓扑中添加控制器时，拓扑发布需要相应的访问权限以在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器并发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。

有关文件共享的存储支持的详细信息，请参阅可支持性文档中的[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)和部署文档中的[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。有关文件共享并置的详细信息，请参阅可支持性文档中的[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)。有关设计控制器拓扑的详细信息，请参阅部署文档中的[Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)。


