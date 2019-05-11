---
title: 添加存档服务器文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: 要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: b59850988e2c863d599fb608c06446e102490f44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889225"
---
# <a name="add-archiving-server-file-store"></a>添加存档服务器文件存储

要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。

> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 > 到拓扑中，拓扑生成器中添加存档服务器时必须能够设置存档文件存储和配置用于文件存储的文件共享上的随机访问控制列表 (Dacl)。 这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。

有关文件共享的存储支持的详细信息，请参阅可支持性文档中的[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 和部署文档中的[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。有关文件共享并置的详细信息，请参阅可支持性文档中的[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)。


