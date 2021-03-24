---
title: 添加控制器文件存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: 必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 8e110324dd1e19ae3dc6eca40aa272d7cdf72414
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114308"
---
# <a name="add-director-file-store"></a><span data-ttu-id="cf123-104">添加控制器文件存储</span><span class="sxs-lookup"><span data-stu-id="cf123-104">Add Director File Store</span></span>

<span data-ttu-id="cf123-p102">必须指定文件共享以用作控制器的文件存储。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。</span><span class="sxs-lookup"><span data-stu-id="cf123-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf123-p103">向拓扑中添加控制器时，拓扑发布需要相应的访问权限以在要用作文件存储的文件共享上设置文件存储并配置随机访问控制列表 (DACL)。这就要求在运行拓扑生成器并发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="cf123-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="cf123-109">有关文件共享的存储支持的详细信息，请参阅可支持性文档中的 File [Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)和部署文档中的 SQL Server Data and Log [File Placement。](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)</span><span class="sxs-lookup"><span data-stu-id="cf123-109">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="cf123-110">有关文件共享并置的详细信息，请参阅可支持性文档中的[支持的服务器并置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)。</span><span class="sxs-lookup"><span data-stu-id="cf123-110">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="cf123-111">有关设计控制器拓扑的详细信息，请参阅部署文档中的[Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology)。</span><span class="sxs-lookup"><span data-stu-id="cf123-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) in the Deployment documentation.</span></span>