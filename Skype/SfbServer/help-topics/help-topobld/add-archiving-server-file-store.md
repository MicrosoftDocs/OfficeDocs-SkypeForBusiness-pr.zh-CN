---
title: 添加存档服务器文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: 要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 22f7de704b3d7a611d4601df4c14ed75f7466c1c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217423"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="48ddc-104">添加存档服务器文件存储</span><span class="sxs-lookup"><span data-stu-id="48ddc-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="48ddc-p102">要启用即时消息 (IM) 和 Web 会议内容的存档，必须指定文件共享以用作所有 Web 会议内容副本的文件存储。可以将现有的文件共享用作存档文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。</span><span class="sxs-lookup"><span data-stu-id="48ddc-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48ddc-107">可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="48ddc-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="48ddc-108">> 将存档服务器添加到拓扑中时，拓扑生成器必须能够设置存档文件存储，并在文件共享上配置用于文件存储的随机访问控制列表 (Dacl) 。</span><span class="sxs-lookup"><span data-stu-id="48ddc-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="48ddc-109">这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="48ddc-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="48ddc-110">有关文件共享的存储支持的详细信息，请参阅可支持性文档中的 [文件存储支持](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 以及部署文档中的 [SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="48ddc-110">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="48ddc-111">有关文件共享并置的详细信息，请参阅可支持性文档中的[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48ddc-111">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


