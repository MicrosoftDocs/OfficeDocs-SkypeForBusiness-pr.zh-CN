---
title: 规划使用 Skype for Business (ADAL) 新式验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍基于 Active Directory 身份验证库 (ADAL (和 OAuth 2.0) 的新式身份验证) 是什么。
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816222"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="86c79-103">如何将新式验证 (ADAL) Skype for Business</span><span class="sxs-lookup"><span data-stu-id="86c79-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="86c79-104">本文介绍基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0) 的新式身份验证 (，可在 Skype for Business for Skype for Business Server 2015 的 2016 年 3 月累积更新或 Skype for Business Server 2019 的初始版本中找到。</span><span class="sxs-lookup"><span data-stu-id="86c79-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="86c79-105">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="86c79-105">What is ADAL?</span></span>

<span data-ttu-id="86c79-106">ADAL 是"Active Directory 身份验证库"的缩写，与 OAuth 2.0 一起是新式验证的基础。</span><span class="sxs-lookup"><span data-stu-id="86c79-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="86c79-107">此代码库旨在将目录中的安全资源提供给客户端应用程序， (Skype for Business) 通过安全令牌访问。</span><span class="sxs-lookup"><span data-stu-id="86c79-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="86c79-108">ADAL 与 OAuth 2.0 一起支持更多身份验证和授权方案，如多重身份验证 (MFA) 和更多形式的 SAML 身份验证。</span><span class="sxs-lookup"><span data-stu-id="86c79-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="86c79-109">各种充当客户端的应用可以利用新式验证来帮助获取安全资源。</span><span class="sxs-lookup"><span data-stu-id="86c79-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="86c79-110">在 Skype for Business Server 中，在本地客户端和内部部署服务器之间使用该技术，以便为用户提供对资源的适当级别的授权。</span><span class="sxs-lookup"><span data-stu-id="86c79-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="86c79-111">基于 ADAL (OAuth 2.0 的新式验证对话) 一些共同的元素。</span><span class="sxs-lookup"><span data-stu-id="86c79-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="86c79-112">有一个客户端请求资源，在这种情况下，客户端是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="86c79-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="86c79-113">客户端需要特定级别的访问权限，并且此资源受目录服务保护，在这种情况下，资源是 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="86c79-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="86c79-114">有一个 OAuth 连接，换句话说，是一个专用于授权用户访问资源的连接。</span><span class="sxs-lookup"><span data-stu-id="86c79-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="86c79-115"> (OAuth 也通过更具描述性的名称"服务器到服务器"身份验证来了解，并且通常缩写为 S2S.) </span><span class="sxs-lookup"><span data-stu-id="86c79-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="86c79-116">在 Skype for Business Server 新式身份验证 (ADAL) 对话中，Skype for Business Server 通过 Windows Server 2012 R2 (ADFS 3.0 中的 ADFS) 。</span><span class="sxs-lookup"><span data-stu-id="86c79-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="86c79-117">身份验证可能使用 IdP (的其他标识提供程序) ，但 Skype for Business 服务器需要配置为直接与 ADFS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="86c79-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="86c79-118">如果你尚未将 ADFS 配置为与 Skype for Business Server 一起工作，请完成 [ADFS 安装](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="86c79-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="86c79-119">ADAL 包含在 Skype for Business Server 2015 的 2016 年 3 月累积更新中，并且必须安装 Skype for **Business** 的 2016 年 3 月累积更新，并且需要此更新才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="86c79-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="86c79-120">对于 Skype for Business Server 2019，它可从产品的初始版本提供。</span><span class="sxs-lookup"><span data-stu-id="86c79-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86c79-121">在初始版本中，只有当没有涉及混合 Skype 拓扑时，才支持本地环境中的现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="86c79-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="86c79-122">例如，如果环境只是 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="86c79-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="86c79-123">此声明可能会更改。</span><span class="sxs-lookup"><span data-stu-id="86c79-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="86c79-124">必须下载包含 .ps1 文件以及 ADAL 使用的命令的 PowerShell 包，以成功配置。</span><span class="sxs-lookup"><span data-stu-id="86c79-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="86c79-125">若要了解如何在 Skype for Business 中实现新式验证，请参阅：如何在 ADAL (ADAL) [Skype for Business 中使用新式验证](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="86c79-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
