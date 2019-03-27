---
title: 添加受信任应用程序池 FQDN
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 要定义受信任应用程序池完全限定的域名 (FQDN)，请指定以下内容：
ms.openlocfilehash: b10053abdb8abcb11aa1a69e1acfcb97a92c4a76
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879967"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="bd78b-103">添加受信任应用程序池 FQDN</span><span class="sxs-lookup"><span data-stu-id="bd78b-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="bd78b-104">要定义受信任应用程序池完全限定的域名 (FQDN)，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="bd78b-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="bd78b-105">服务器或服务器将承载受信任应用程序池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bd78b-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="bd78b-106">如果您要部署的服务器从负载平衡和高可用性的受信任应用程序池，或选择**单计算机池**，如果您不需要负载平衡或高可用性，请选择**多计算机池**。</span><span class="sxs-lookup"><span data-stu-id="bd78b-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bd78b-107">单一的受信任应用程序服务器无法转换为的更高版本服务器池。</span><span class="sxs-lookup"><span data-stu-id="bd78b-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="bd78b-108">如果您认为您将来可能需要一个池，您可以部署多个服务器池现在，包含一台计算机，并添加时所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="bd78b-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="bd78b-109">关于受信任应用程序池的详细信息，请参阅[New-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="bd78b-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

