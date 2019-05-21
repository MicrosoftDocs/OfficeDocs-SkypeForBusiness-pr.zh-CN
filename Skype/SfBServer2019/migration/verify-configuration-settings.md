---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For CsManagementStoreReplicationStatus cmdlet 验证配置信息到边缘服务器的复制, 或者在任何安装了 Skype for business Server 2019 核心组件 (OcsCore) 的加入域的计算机。
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307033"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="c10b2-103">验证配置设置</span><span class="sxs-lookup"><span data-stu-id="c10b2-103">Verify configuration settings</span></span>

<span data-ttu-id="c10b2-104">你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For **CsManagementStoreReplicationStatus** cmdlet 来验证对边缘服务器的配置信息的复制, 或者在安装了 Skype for Business Server 2019 核心组件 (OcsCore) 的任何加入域的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c10b2-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="c10b2-105">初始结果可能表明状态为 "False", 而不是 "True" 用于复制。</span><span class="sxs-lookup"><span data-stu-id="c10b2-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="c10b2-106">如果是这样, 请运行**CsManagementStoreReplication** cmdlet 并等待复制完成, 然后再再次运行**Get CsManagementStoreReplicationStatus** 。</span><span class="sxs-lookup"><span data-stu-id="c10b2-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

