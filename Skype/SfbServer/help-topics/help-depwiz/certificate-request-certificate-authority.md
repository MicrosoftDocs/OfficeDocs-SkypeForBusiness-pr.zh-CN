---
title: 证书请求（证书颁发机构）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 向联机证书颁发机构 (CA) 发出证书请求时 （通常情况下，这些都是在内部网络上的服务器） 上选择证书颁发机构 (CA) 页上，将会出现两个选项：
ms.openlocfilehash: 6fea8ba9500e1612ff13796f4c58550687baa99a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="605ed-103">证书请求（证书颁发机构）</span><span class="sxs-lookup"><span data-stu-id="605ed-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="605ed-104">在“**选择证书颁发机构 (CA)**”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：</span><span class="sxs-lookup"><span data-stu-id="605ed-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="605ed-105">从在您的环境中检测到的列表中选择一个 CA。</span><span class="sxs-lookup"><span data-stu-id="605ed-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="605ed-106">指定其他证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="605ed-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="605ed-107">如果您选择第一个选项，您将看到包含在您的环境中检测到的所有基于 Windows 服务器的证书颁发机构列表。</span><span class="sxs-lookup"><span data-stu-id="605ed-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="605ed-108">选择证书相应的证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="605ed-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="605ed-109">您可能需要咨询 CA 管理员以了解应选择哪个 CA。</span><span class="sxs-lookup"><span data-stu-id="605ed-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="605ed-p102">如果选择第二个选项，则需键入要用于证书的证书颁发机构的完全限定域名 (FQDN) 以及 CA 实例。如果要使用的 CA 不是基于 Windows Server 的 CA，但适用于基于 Windows Server 的 CA，则此选项适用。</span><span class="sxs-lookup"><span data-stu-id="605ed-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="605ed-112">应首先确认所需的组成员身份以确保证书请求能够成功。</span><span class="sxs-lookup"><span data-stu-id="605ed-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="605ed-113">通常，证书颁发机构有不同的权限要求从 Skype 业务服务器安装在服务器上的要求。</span><span class="sxs-lookup"><span data-stu-id="605ed-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="605ed-114">请与 CA 管理员确认请求证书的要求。</span><span class="sxs-lookup"><span data-stu-id="605ed-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

