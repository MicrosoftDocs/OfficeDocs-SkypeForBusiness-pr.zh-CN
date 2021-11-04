---
title: 添加前端文件存储
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: 必须为 Standard Edition 服务器或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 5cda72723d4c183271324f45f4279f741972becc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752531"
---
# <a name="add-front-end-file-store"></a>添加前端文件存储

必须为 Standard Edition 服务器或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。

> [!IMPORTANT]
> 文件共享不能位于前端Enterprise Edition，但可以位于 Standard Edition 服务器上。

> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。

> [!IMPORTANT]
> 向拓扑中添加 Enterprise 前端池或 Standard Edition 服务器时，拓扑生成器必须能够在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。

有关文件共享的存储支持的详细信息，请参阅可支持性文档中的 File[存储 Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)和部署文档中的 SQL Server Data and Log [File Placement。](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 有关文件共享并置的详细信息，请参阅可支持性文档中的[支持的服务器并置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)。 有关设计 Enterprise Edition 前端池拓扑的详细信息，请参阅部署文档中的[Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)。