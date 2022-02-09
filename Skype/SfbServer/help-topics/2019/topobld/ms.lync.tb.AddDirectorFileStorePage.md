---
title: 添加控制器文件存储
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 47ff804eec897d1bf54dd2d012b777b022cd515e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400926"
---
# <a name="add-director-file-store"></a>添加控制器文件存储

必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。

> [!IMPORTANT]
> 向拓扑中添加控制器时，拓扑发布需要相应的访问权限以在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器并发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。

有关文件共享的存储支持的详细信息，请参阅可存储性文档中的 File [存储 Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 和部署文档中的 SQL Server [Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。 有关文件共享并置的详细信息，请参阅可支持性文档中的[支持的服务器并置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)。 有关设计控制器拓扑的详细信息，请参阅部署文档中的[Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology)。