---
title: 使用 Skype for Business 规划新式验证（ADAL）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍了什么新式身份验证（基于 Active Directory 身份验证库（ADAL）和 OAuth 2.0）。
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046285"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="fcc2d-103">如何将新式身份验证（ADAL）用于 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fcc2d-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="fcc2d-104">本文介绍了新式身份验证（基于 Active Directory 身份验证库（ADAL）和 OAuth 2.0），可在2006年3月2016累积更新中找到 skype for business Server 2015 或初始发布 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="fcc2d-105">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="fcc2d-105">What is ADAL?</span></span>

<span data-ttu-id="fcc2d-106">ADAL 是 "Active Directory 身份验证库" 的首字母缩写词，以及 OAuth 2.0，它是新式身份验证的基础。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="fcc2d-107">此代码库旨在通过安全令牌将目录中的受保护资源提供给客户端应用程序（如 Skype for Business）。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="fcc2d-108">ADAL 与 OAuth 2.0 结合使用，以启用更多身份验证和授权方案，如多重身份验证（MFA）和更多形式的 SAML Auth。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="fcc2d-109">充当客户端的各种应用可以利用新式验证来帮助获取受保护的资源。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="fcc2d-110">在 Skype for Business Server 中，在本地客户端和本地服务器之间使用此技术，以便为用户提供对资源的适当级别的授权。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="fcc2d-111">新式身份验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="fcc2d-112">有一个客户端发出对资源的请求，在这种情况下，客户端是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="fcc2d-113">有一个资源，客户端需要特定级别的访问权限，并且该资源由目录服务保护，在这种情况下，该资源是 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="fcc2d-114">有一个 OAuth 连接，也就是说，专用于*授权*用户访问资源的连接。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="fcc2d-115">（也可以使用更具描述性的名称 "服务器到服务器" 身份验证，并且通常缩写为 S2S。）</span><span class="sxs-lookup"><span data-stu-id="fcc2d-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="fcc2d-116">在 Skype for Business Server 新式验证（ADAL）对话中，Skype for Business Server 通过 ADFS （在 Windows Server 2012 R2 中为 ADFS 3.0）进行通信。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="fcc2d-117">使用其他一些标识提供程序（IdP）可能会发生身份验证，但需要将 Skype for Business 服务器配置为直接与 ADFS 通信。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="fcc2d-118">如果尚未将 ADFS 配置为与 Skype for Business Server 一起使用，请完成[ADFS 安装](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="fcc2d-119">ADAL 包含在 Skype for business Server 2015 的2016年3月累积更新中，**必须**安装 skype for Business 的3月2016累积更新，才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="fcc2d-120">对于 Skype for business Server 2019，可从产品的初始版本获取。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fcc2d-121">在初始发布过程中，仅当没有涉及的混合 Skype 拓扑时，才支持在本地环境中进行新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="fcc2d-122">例如，如果环境是纯 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="fcc2d-123">本声明可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="fcc2d-124">必须下载包含. ps1 文件的 PowerShell 包，其中包含由 ADAL 使用的命令，才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="fcc2d-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="fcc2d-125">若要了解如何在 Skype for Business 中实施新式验证，请参阅以下内容：[如何将新式身份验证（ADAL）用于 skype for](../../manage/authentication/use-adal.md) business</span><span class="sxs-lookup"><span data-stu-id="fcc2d-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
