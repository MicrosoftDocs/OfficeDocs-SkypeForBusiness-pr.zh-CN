---
title: 确认配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以通过在中央管理存储是位于，或对任何内部计算机上运行业务服务器 2019 Get-csmanagementstorereplicationstatus cmdlet Skype 验证到边缘服务器的配置信息的复制加入域的计算机的业务 Server 2019 核心组件 (OcsCore.msi) 的 Skype 已安装。
ms.openlocfilehash: 23a5b4c3af8ac02ebfd620d3bbc46ddcba5bea11
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027807"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="f6a42-103">确认配置设置</span><span class="sxs-lookup"><span data-stu-id="f6a42-103">Verify configuration settings</span></span>

<span data-ttu-id="f6a42-104">您可以通过中央管理存储所在，在内部计算机上运行业务服务器 2019 **Get-csmanagementstorereplicationstatus** cmdlet Skype 验证到边缘服务器的配置信息的复制或在其上任何加入域的计算机上安装 Skype 的业务 Server 2019 核心组件 (OcsCore.msi)。</span><span class="sxs-lookup"><span data-stu-id="f6a42-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="f6a42-105">初始结果可能指示的状态为"False"而不是"True"进行复制。</span><span class="sxs-lookup"><span data-stu-id="f6a42-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="f6a42-106">如果是这样，运行**Invoke CsManagementStoreReplication** cmdlet，并允许再次运行**Get-csmanagementstorereplicationstatus**之前完成复制的时间。</span><span class="sxs-lookup"><span data-stu-id="f6a42-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

