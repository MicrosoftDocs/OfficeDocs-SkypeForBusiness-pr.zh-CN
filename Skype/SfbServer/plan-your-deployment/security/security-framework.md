---
title: Skype for Business Server 2015 安全框架
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本节概述了业务服务器 2015年的 Skype 形成安全框架的基本元素。 了解这些元素在一起工作的方式对有关保护您特定的业务服务器 2015年部署 Skype 明智决策至关重要。
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a><span data-ttu-id="f698f-104">Skype for Business Server 2015 安全框架</span><span class="sxs-lookup"><span data-stu-id="f698f-104">Security framework for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f698f-105">本节概述了业务服务器 2015年的 Skype 形成安全框架的基本元素。</span><span class="sxs-lookup"><span data-stu-id="f698f-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server 2015.</span></span> <span data-ttu-id="f698f-106">了解这些元素在一起工作的方式对有关保护您特定的业务服务器 2015年部署 Skype 明智决策至关重要。</span><span class="sxs-lookup"><span data-stu-id="f698f-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="f698f-107">这些要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="f698f-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="f698f-108">Active Directory 域服务 (AD DS) 提供一个可靠的后端存储库的用户帐户和网络资源。</span><span class="sxs-lookup"><span data-stu-id="f698f-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="f698f-109">通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。</span><span class="sxs-lookup"><span data-stu-id="f698f-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="f698f-110">公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。</span><span class="sxs-lookup"><span data-stu-id="f698f-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="f698f-p103">传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。</span><span class="sxs-lookup"><span data-stu-id="f698f-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="f698f-113">用于用户身份验证的行业标准协议，如果可能。</span><span class="sxs-lookup"><span data-stu-id="f698f-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="f698f-114">Windows PowerShell 提供安全功能，默认情况下启用，以便用户不能轻松地不知不觉地或运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f698f-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="f698f-115">这些基本的安全元素一起工作来定义受信任的用户、 服务器、 连接和操作，来帮助确保安全的基础的 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="f698f-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server 2015.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f698f-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="f698f-116">In this section</span></span>

<span data-ttu-id="f698f-117">本节中的主题描述每个基本元素的工作方式来提高您 Skype 业务服务器基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="f698f-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="f698f-118">Skype 业务服务器 2015年的 active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="f698f-118">Active Directory Domain Services for Skype for Business Server 2015</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="f698f-119">为业务服务器 2015年的 Skype 的基于角色的访问控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="f698f-119">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="f698f-120">Skype 业务服务器 2015年的公钥基础结构</span><span class="sxs-lookup"><span data-stu-id="f698f-120">Public Key Infrastructure for Skype for Business Server 2015</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="f698f-121">TLS 和 Skype 业务服务器 2015年的 MTLS</span><span class="sxs-lookup"><span data-stu-id="f698f-121">TLS and MTLS for Skype for Business Server 2015</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="f698f-122">对 Skype 业务服务器 2015年的加密</span><span class="sxs-lookup"><span data-stu-id="f698f-122">Encryption for Skype for Business Server 2015</span></span>](encryption.md)
    
- [<span data-ttu-id="f698f-123">用户和客户端的身份验证为 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="f698f-123">User and client authentication for Skype for Business Server 2015</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="f698f-124">Windows PowerShell 和 Skype 业务服务器 2015年管理工具</span><span class="sxs-lookup"><span data-stu-id="f698f-124">Windows PowerShell and Skype for Business Server 2015 management tools</span></span>](management-tools.md)
    

