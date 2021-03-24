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
description: 本文介绍基于 Active Directory 身份验证库 (ADAL (和 OAuth 2.0) 新式验证) 是什么。
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096608"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="e3b9a-103">如何使用 Skype for Business (ADAL) 新式验证</span><span class="sxs-lookup"><span data-stu-id="e3b9a-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="e3b9a-104">本文介绍了基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0) 的新式验证 (，可在 Skype for Business for Skype for Business Server 2015 的 2016 年 3 月累积更新或 Skype for Business Server 2019 的初始版本中找到。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="e3b9a-105">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="e3b9a-105">What is ADAL?</span></span>

<span data-ttu-id="e3b9a-106">ADAL 是"Active Directory 身份验证库"的缩写，与 OAuth 2.0 一起是新式验证的基础。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="e3b9a-107">此代码库旨在向客户端应用程序（如 Skype for Business (通过安全令牌) 目录中的安全资源。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="e3b9a-108">ADAL 与 OAuth 2.0 一起支持更多身份验证和授权方案，如多重身份验证 (MFA) 以及更多形式的 SAML 身份验证。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="e3b9a-109">各种充当客户端的应用可以利用新式验证来帮助获取安全资源。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="e3b9a-110">在 Skype for Business Server 中，此技术在本地客户端和本地服务器之间使用，以便为用户提供适当级别的资源授权。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="e3b9a-111">基于 ADAL (OAuth 2.0 的新式身份验证对话) 一些共同的元素。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="e3b9a-112">有一个客户端请求资源，在这种情况下，客户端是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="e3b9a-113">有一个资源，客户端需要特定级别的访问权限，此资源受目录服务保护，在这种情况下，资源是 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="e3b9a-114">有一个 OAuth 连接，即专用于授权用户访问资源的连接。 </span><span class="sxs-lookup"><span data-stu-id="e3b9a-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="e3b9a-115"> (OAuth 也称作更具描述性的名称"服务器到服务器"身份验证，通常缩写为 S2S.) </span><span class="sxs-lookup"><span data-stu-id="e3b9a-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="e3b9a-116">在 Skype for Business Server 新式验证 (ADAL) 对话中，Skype for Business Server 通过 Windows Server 2012 R2 (ADFS 3.0 中的 ADFS) 通信。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="e3b9a-117">身份验证可能会使用 IdP (的其他一) ，但 Skype for Business 服务器需要配置为直接与 ADFS 通信。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="e3b9a-118">如果你尚未将 ADFS 配置为与 Skype for Business Server 一起运行，请完成 [ADFS 安装](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>
  
<span data-ttu-id="e3b9a-119">ADAL 包含在 Skype for Business Server 2015 的 2016 年 3 月累积更新中，并且必须安装 Skype for **Business** 的 2016 年 3 月累积更新，并且该更新是成功配置所需的。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="e3b9a-120">对于 Skype for Business Server 2019，它可从产品的初始版本提供。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3b9a-121">在初始版本中，只有在未涉及混合 Skype 拓扑时，才支持内部部署环境中的现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="e3b9a-122">例如，如果环境完全为 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="e3b9a-123">此声明可能会更改。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="e3b9a-124">必须下载 PowerShell 程序包（包括 .ps1 文件以及 ADAL 使用的命令）以成功配置。</span><span class="sxs-lookup"><span data-stu-id="e3b9a-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="e3b9a-125">若要了解如何在 Skype for Business 中实现新式验证，请参阅：如何将新式验证 ([ADAL](/microsoft-365/enterprise/hybrid-modern-auth-overview)) Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e3b9a-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span>