---
title: Lync Server 2013：配置 DFS 文件存储
description: Lync Server 2013：配置 DFS 文件存储。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564378"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="b95af-103">为 Lync Server 2013 配置 DFS 文件存储</span><span class="sxs-lookup"><span data-stu-id="b95af-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b95af-104">_**上次修改的主题：** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="b95af-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="b95af-105">Lync Server 2013 支持在分布式文件系统上使用文件共享 (DFS) 。</span><span class="sxs-lookup"><span data-stu-id="b95af-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="b95af-106">有关适用于 Windows Server 2008 的 DFS 的详细信息，请参阅 Windows Server 2008 at 的 DFS 分步指南 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) 。若要使用 DFS，Lync Server 2013 需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="b95af-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="b95af-107">命名空间基于域</span><span class="sxs-lookup"><span data-stu-id="b95af-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="b95af-108">所有命名空间服务器都至少运行 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="b95af-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="b95af-109">Lync Server 2013 安装程序要求对共享文件夹的权限允许对管理员具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="b95af-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="b95af-110">然后，Lync Server 2013 将使用 NTFS 文件权限对文件夹进行 ACL。</span><span class="sxs-lookup"><span data-stu-id="b95af-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="b95af-111">继承的 DFS 共享权限不会用于限制访问。</span><span class="sxs-lookup"><span data-stu-id="b95af-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="b95af-112">有关文件共享要求的更多详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="b95af-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b95af-113">您可能正在寻找有关配置非 DFS 共享的信息。</span><span class="sxs-lookup"><span data-stu-id="b95af-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="b95af-114">如果是，请查看 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬件设置</A>。</span><span class="sxs-lookup"><span data-stu-id="b95af-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b95af-115">以下过程介绍如何使用 DFS 命名空间向导（如 DFS 安装指南中所述）正确配置共享文件夹权限。</span><span class="sxs-lookup"><span data-stu-id="b95af-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="b95af-116">配置共享文件夹权限</span><span class="sxs-lookup"><span data-stu-id="b95af-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="b95af-117">单击“开始”\*\*\*\*，指向“所有程序”\*\*\*\*，指向“管理工具”\*\*\*\*，然后单击“DFS 管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b95af-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="b95af-118">在“DFS 管理”管理单元的控制台树中，右键单击命名空间服务器（如 filesrv1.contoso.com），然后单击“编辑设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b95af-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="b95af-119">选择“共享文件夹权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b95af-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="b95af-120">选择“使用自定义权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b95af-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="b95af-121">对于 Administrator 组，在“允许”\*\*\*\* 下选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="b95af-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="b95af-122">“完全控制”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b95af-122">**Full Control**</span></span>
    
      - <span data-ttu-id="b95af-123">**Change**</span><span class="sxs-lookup"><span data-stu-id="b95af-123">**Change**</span></span>
    
      - <span data-ttu-id="b95af-124">**Read**</span><span class="sxs-lookup"><span data-stu-id="b95af-124">**Read**</span></span>

6.  <span data-ttu-id="b95af-125">单击“应用”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b95af-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

