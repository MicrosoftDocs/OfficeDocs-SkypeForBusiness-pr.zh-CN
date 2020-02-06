---
title: 添加受信任应用程序池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787732"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="0aaf0-103">添加受信任应用程序池 FQDN</span><span class="sxs-lookup"><span data-stu-id="0aaf0-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="0aaf0-104">若要定义受信任的应用程序池完全限定的域名（FQDN），请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="0aaf0-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="0aaf0-105">将托管受信任的应用程序的服务器或服务器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0aaf0-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="0aaf0-106">如果要为受信任的应用程序部署负载平衡和高可用性的服务器池，或者选择 "**单个计算机池**" （如果不需要负载平衡或高可用性），请选择 "**多台计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="0aaf0-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0aaf0-107">一个受信任的应用程序服务器稍后无法转换为服务器池。</span><span class="sxs-lookup"><span data-stu-id="0aaf0-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="0aaf0-108">如果你认为将来可能需要一个池，你可以部署包含一台计算机的多个服务器池，并根据需要添加服务器。</span><span class="sxs-lookup"><span data-stu-id="0aaf0-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="0aaf0-109">有关受信任的应用程序池的详细信息，请参阅[CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0aaf0-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

