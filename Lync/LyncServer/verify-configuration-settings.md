---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bfc01e5b14738592647c379a1e2f9e62f808bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="edc83-102">验证配置设置</span><span class="sxs-lookup"><span data-stu-id="edc83-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc83-103">_**上次修改的主题：** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="edc83-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="edc83-104">您可以通过在中央管理存储所在的内部计算机上运行 Lync Server 2013 **get-csmanagementstorereplicationstatus** cmdlet，或在安装了 Lync Server 2013 核心组件（OcsCore）的任何加入域的计算机上运行 lync server cmdlet，来验证是否将配置信息复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="edc83-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="edc83-105">初始结果可能指示复制的状态为“False”而非“True”。</span><span class="sxs-lookup"><span data-stu-id="edc83-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="edc83-106">如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。</span><span class="sxs-lookup"><span data-stu-id="edc83-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

