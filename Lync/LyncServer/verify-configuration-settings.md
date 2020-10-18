---
title: 验证配置设置
description: 验证配置设置。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7bb1135e95dafe51e906768fe0f4f0d57bf2d6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573108"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="0237a-103">验证配置设置</span><span class="sxs-lookup"><span data-stu-id="0237a-103">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0237a-104">_**上次修改的主题：** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="0237a-104">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="0237a-105">您可以通过在中央管理存储所在的内部计算机上运行 Lync Server 2013 **get-csmanagementstorereplicationstatus** cmdlet，或在任何已安装 ( # A0) 的 lync Server 2013 核心组件的已加入域的计算机上，验证配置信息到边缘服务器的复制。</span><span class="sxs-lookup"><span data-stu-id="0237a-105">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="0237a-106">初始结果可能指示复制的状态为“False”而非“True”。</span><span class="sxs-lookup"><span data-stu-id="0237a-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="0237a-107">如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。</span><span class="sxs-lookup"><span data-stu-id="0237a-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

