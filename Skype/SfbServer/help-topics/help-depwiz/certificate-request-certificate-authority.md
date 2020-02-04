---
title: 证书请求（证书颁发机构）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 在“选择证书颁发机构 (CA)”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：
ms.openlocfilehash: 6cd2eb648897adc4c6d627f8c97659ce3b13ea4e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687805"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="3b920-103">证书请求（证书颁发机构）</span><span class="sxs-lookup"><span data-stu-id="3b920-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="3b920-104">在“**选择证书颁发机构 (CA)**”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：</span><span class="sxs-lookup"><span data-stu-id="3b920-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="3b920-105">从在您的环境中检测到的列表中选择一个 CA。</span><span class="sxs-lookup"><span data-stu-id="3b920-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="3b920-106">指定其他证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3b920-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="3b920-107">如果您选择第一个选项，您将看到一个下拉列表，其中包含在您的环境中检测到的所有基于 Windows 服务器的证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3b920-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="3b920-108">选择证书相应的证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3b920-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="3b920-109">您可能需要咨询 CA 管理员以了解应选择哪个 CA。</span><span class="sxs-lookup"><span data-stu-id="3b920-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="3b920-p102">如果选择第二个选项，则需键入要用于证书的证书颁发机构的完全限定域名 (FQDN) 以及 CA 实例。如果要使用的 CA 不是基于 Windows Server 的 CA，但适用于基于 Windows Server 的 CA，则此选项适用。</span><span class="sxs-lookup"><span data-stu-id="3b920-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b920-112">应首先确认所需的组成员身份以确保证书请求能够成功。</span><span class="sxs-lookup"><span data-stu-id="3b920-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="3b920-113">通常，证书颁发机构对在服务器上安装 Skype for Business 服务器的要求具有不同的权限要求。</span><span class="sxs-lookup"><span data-stu-id="3b920-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="3b920-114">请与 CA 管理员确认请求证书的要求。</span><span class="sxs-lookup"><span data-stu-id="3b920-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

