---
title: 添加存档服务器文件存储
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: 要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 160289766fcdbf38f706962329e61d1d72e96af5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388820"
---
# <a name="add-archiving-server-file-store"></a>添加存档服务器文件存储

要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。

> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 >向拓扑中添加存档服务器时，拓扑生成器必须能够在要用于文件存储的文件共享上设置存档文件存储并配置任意访问控制列表 () 。 这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。

有关文件共享的存储支持的详细信息，请参阅可支持性文档中的 File [存储 Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 和部署文档中的 SQL Server [Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。 有关文件共享并置的详细信息，请参阅可支持性文档中的[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)。