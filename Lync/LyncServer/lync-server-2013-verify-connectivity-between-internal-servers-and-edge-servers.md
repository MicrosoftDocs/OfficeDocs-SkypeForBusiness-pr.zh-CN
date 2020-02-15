---
title: 验证内部服务器与边缘服务器之间的连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf2a8c64e549a90661d10614254c5937ebde603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="d6d06-102">验证 Lync Server 2013 中的内部服务器与边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="d6d06-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d06-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d6d06-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d6d06-104">在 Lync Server 2013 中，可使用单独的验证向导来帮助验证边缘服务器和内部服务器之间的连接。</span><span class="sxs-lookup"><span data-stu-id="d6d06-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="d6d06-105">在 Lync Server 2013 中，连接的验证是在您安装边缘服务器时自动完成的。</span><span class="sxs-lookup"><span data-stu-id="d6d06-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="d6d06-106">您可以通过在中央管理存储所在的内部计算机上运行 Windows PowerShell **get-csmanagementstorereplicationstatus** cmdlet （或安装了 Lync Server 2013 核心组件（OcsCore）的任何加入域的计算机）来验证配置信息到边缘的复制。</span><span class="sxs-lookup"><span data-stu-id="d6d06-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="d6d06-107">初始结果可能指示复制的状态为“False”而非“True”。</span><span class="sxs-lookup"><span data-stu-id="d6d06-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="d6d06-108">如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。</span><span class="sxs-lookup"><span data-stu-id="d6d06-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="d6d06-109">可以单独验证外部用户连接，包括使用 Office Communications Server 远程连接分析器验证远程用户连接。</span><span class="sxs-lookup"><span data-stu-id="d6d06-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="d6d06-110">有关详细信息，请参阅[在 Lync Server 2013 中验证外部用户的连接性](lync-server-2013-verify-connectivity-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d06-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

