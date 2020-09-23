---
title: 添加边缘服务器 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: 必须指定访问边缘服务的完全限定域名 (FQDN)。 如果未在 "选择功能" 页上选择 "使用单个 FQDN &amp; IP 地址" 选项，则还必须为 Web 会议边缘服务和 a/V 边缘服务指定一个 fqdn。
ms.openlocfilehash: d67caefe3e60d8c4e9cd398438fb7a4d93cd9d45
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219223"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="c4271-104">添加边缘服务器 FQDN</span><span class="sxs-lookup"><span data-stu-id="c4271-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="c4271-105">必须指定访问边缘服务的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c4271-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="c4271-106">如果未在 "**选择功能**" 页上选择 "**使用单个 FQDN &amp; IP 地址**" 选项，则还必须为 Web 会议边缘服务和 a/V 边缘服务指定一个 fqdn。</span><span class="sxs-lookup"><span data-stu-id="c4271-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="c4271-107">此外，如果选择了 " **使用单个 FQDN &amp; IP 地址** " 选项，则必须为每个边缘服务指定不同的端口号。 (建议的端口设置：444用于访问边缘服务，8057用于 Web 会议边缘服务，以及 a/V 边缘服务) 的443。</span><span class="sxs-lookup"><span data-stu-id="c4271-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="c4271-108">如果未选择此选项，则可以为所有三个服务使用相同的端口号（如 443）。</span><span class="sxs-lookup"><span data-stu-id="c4271-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

