---
title: 通过 Skype for Business 规划新式验证 (ADAL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍了什么新式身份验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0)。
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297293"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="efdaa-103">如何将新式验证 (ADAL) 与 Skype for Business 配合使用</span><span class="sxs-lookup"><span data-stu-id="efdaa-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="efdaa-104">本文介绍了新式验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0), 可在2016年3月累积更新中找到 skype for business Server 2015 的 skype for business 累积更新或初始验证发布 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="efdaa-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="efdaa-105">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="efdaa-105">What is ADAL?</span></span>

<span data-ttu-id="efdaa-106">ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。</span><span class="sxs-lookup"><span data-stu-id="efdaa-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="efdaa-107">此代码库旨在通过安全令牌使你的目录中的安全资源可供客户端应用程序 (如 Skype for Business) 使用。</span><span class="sxs-lookup"><span data-stu-id="efdaa-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="efdaa-108">ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。</span><span class="sxs-lookup"><span data-stu-id="efdaa-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="efdaa-109">充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。</span><span class="sxs-lookup"><span data-stu-id="efdaa-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="efdaa-110">在 Skype for Business 服务器中, 将在本地客户端和本地服务器之间使用此技术, 以便为用户提供适当级别的资源授权。</span><span class="sxs-lookup"><span data-stu-id="efdaa-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="efdaa-111">新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。</span><span class="sxs-lookup"><span data-stu-id="efdaa-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="efdaa-112">客户端正在请求资源, 在这种情况下, 客户端是 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="efdaa-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="efdaa-113">客户端需要具有特定级别的访问权限的资源, 并且此资源由目录服务保护, 在这种情况下, 资源是 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="efdaa-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="efdaa-114">有一个 OAuth 连接, 换言之, 即专用于*授权*用户访问资源的连接。</span><span class="sxs-lookup"><span data-stu-id="efdaa-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="efdaa-115">(OAuth 也可以通过更具描述性的名称 "服务器到服务器" 身份验证来识别, 并且通常缩写为 S2S。)</span><span class="sxs-lookup"><span data-stu-id="efdaa-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="efdaa-116">在 Skype for business Server 新式验证 (ADAL) 对话中, Skype for business 服务器通过 ADFS (在 Windows Server 2012 R2 中是 ADFS 3.0) 进行通信。</span><span class="sxs-lookup"><span data-stu-id="efdaa-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="efdaa-117">可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="efdaa-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="efdaa-118">如果尚未配置 ADFS 使用 Skype for Business 服务器, 请完成[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="efdaa-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="efdaa-119">ADAL 已包含在 skype for business Server 2015 的2016年3月累积更新中, 并且必须安装 2006 2016 年3月的 skype for business 累积更新, 并且需要成功配置。</span><span class="sxs-lookup"><span data-stu-id="efdaa-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="efdaa-120">对于 Skype for business Server 2019, 可从产品的初始版本获取。</span><span class="sxs-lookup"><span data-stu-id="efdaa-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efdaa-121">在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。</span><span class="sxs-lookup"><span data-stu-id="efdaa-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="efdaa-122">例如, 如果环境是纯 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="efdaa-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="efdaa-123">此陈述可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="efdaa-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="efdaa-124">必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="efdaa-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="efdaa-125">有关如何在 Skype for Business 中实施新式身份验证的信息, 请参阅:[如何将新式身份验证 (ADAL) 用于 skype for](../../manage/authentication/use-adal.md) business</span><span class="sxs-lookup"><span data-stu-id="efdaa-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
