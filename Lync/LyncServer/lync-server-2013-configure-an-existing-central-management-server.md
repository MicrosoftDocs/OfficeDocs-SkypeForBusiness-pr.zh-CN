---
title: Lync Server 2013：配置现有中央管理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="fccc1-102">在 Lync Server 2013 中配置现有中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="fccc1-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fccc1-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fccc1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fccc1-104">如果从现有 Lync Server 2013 部署重用中央管理服务器, 则必须运行以下所述的过程, 以确保 Lync Server 控制面板和 Windows PowerShell 正常工作。</span><span class="sxs-lookup"><span data-stu-id="fccc1-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="fccc1-105">配置现有中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="fccc1-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="fccc1-106">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="fccc1-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fccc1-107">使用**CsAdminRole** cmdlet 更新存储在中央管理服务器中的基于角色的访问控制 (RBAC) 角色。</span><span class="sxs-lookup"><span data-stu-id="fccc1-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fccc1-108">不应输出, 除非出现错误。</span><span class="sxs-lookup"><span data-stu-id="fccc1-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

