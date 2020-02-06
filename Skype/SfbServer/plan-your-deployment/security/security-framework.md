---
title: Skype for business Server 的安全框架
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本部分概述了构成 Skype for business 服务器安全框架的基本元素。 了解这些元素如何协同工作对于做出有关保护特定 Skype for Business 服务器部署的明智决策至关重要。
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815610"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="8d931-104">Skype for business Server 的安全框架</span><span class="sxs-lookup"><span data-stu-id="8d931-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="8d931-105">本部分概述了构成 Skype for business 服务器安全框架的基本元素。</span><span class="sxs-lookup"><span data-stu-id="8d931-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="8d931-106">了解这些元素如何协同工作对于做出有关保护特定 Skype for Business 服务器部署的明智决策至关重要。</span><span class="sxs-lookup"><span data-stu-id="8d931-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="8d931-107">这些要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d931-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="8d931-108">Active Directory 域服务（AD DS）为用户帐户和网络资源提供单个受信任的后端存储库。</span><span class="sxs-lookup"><span data-stu-id="8d931-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="8d931-109">通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。</span><span class="sxs-lookup"><span data-stu-id="8d931-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="8d931-110">公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。</span><span class="sxs-lookup"><span data-stu-id="8d931-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="8d931-p103">传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。</span><span class="sxs-lookup"><span data-stu-id="8d931-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="8d931-113">用于用户身份验证的行业标准协议，如果可能。</span><span class="sxs-lookup"><span data-stu-id="8d931-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="8d931-114">Windows PowerShell 提供默认启用的安全功能，以便用户无法轻松或不知不觉地运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8d931-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="8d931-115">这些基本的安全元素协同工作以定义受信任的用户、服务器、连接和操作，以帮助确保 Skype for business 服务器的安全基础。</span><span class="sxs-lookup"><span data-stu-id="8d931-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8d931-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d931-116">In this section</span></span>

<span data-ttu-id="8d931-117">本部分中的主题介绍了每个基本元素如何工作以增强 Skype for business 服务器基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="8d931-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="8d931-118">适用于 Skype for business 服务器的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="8d931-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="8d931-119">Skype for business Server 的基于角色的访问控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="8d931-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="8d931-120">Skype for business 服务器的公共密钥基础结构</span><span class="sxs-lookup"><span data-stu-id="8d931-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="8d931-121">Skype for business 服务器的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="8d931-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="8d931-122">Skype for business 服务器加密</span><span class="sxs-lookup"><span data-stu-id="8d931-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="8d931-123">Skype for business Server 的用户和客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="8d931-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="8d931-124">Windows PowerShell 和 Skype for business 服务器管理工具</span><span class="sxs-lookup"><span data-stu-id="8d931-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

