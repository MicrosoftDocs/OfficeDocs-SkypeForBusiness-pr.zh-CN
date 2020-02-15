---
title: 验证配置设置的复制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65620e07227581f35e5760e8665e615c6976bde2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="f9d7a-102">验证配置设置的复制</span><span class="sxs-lookup"><span data-stu-id="f9d7a-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9d7a-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f9d7a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f9d7a-104">您可以通过在中央管理存储所在的内部计算机上运行 Lync Server 2013 **get-csmanagementstorereplicationstatus** cmdlet，或在其中安装了 Lync Server 2013 核心组件的任何加入域的计算机上，验证配置信息到边缘服务器的复制。</span><span class="sxs-lookup"><span data-stu-id="f9d7a-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="f9d7a-105">初始结果可能指示复制的状态为“False”而非“True”。</span><span class="sxs-lookup"><span data-stu-id="f9d7a-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="f9d7a-106">如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** cmdlet 前为完成复制留出时间。</span><span class="sxs-lookup"><span data-stu-id="f9d7a-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

