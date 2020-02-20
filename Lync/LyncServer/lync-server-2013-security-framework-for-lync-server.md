---
title: Lync Server 2013： Lync Server 的安全框架
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 472e15d2206e787abb571885f0155bb0169f7234
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="afe80-102">Lync Server 2013 的安全框架</span><span class="sxs-lookup"><span data-stu-id="afe80-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afe80-103">_**上次修改的主题：** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="afe80-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="afe80-104">本节概述了构成 Microsoft Lync Server 2013 安全框架的基本元素。</span><span class="sxs-lookup"><span data-stu-id="afe80-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="afe80-105">了解这些元素协同工作的方式对于做出有关保护您的特定 Lync Server 2013 部署的明智决定至关重要。</span><span class="sxs-lookup"><span data-stu-id="afe80-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="afe80-106">这些要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="afe80-106">These elements are as follows:</span></span>

  - <span data-ttu-id="afe80-107">Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供一个受信任的后端存储库。</span><span class="sxs-lookup"><span data-stu-id="afe80-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="afe80-108">基于角色的访问控制（RBAC）使您能够在保持高标准安全性的同时委派管理任务。</span><span class="sxs-lookup"><span data-stu-id="afe80-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="afe80-109">公钥基础结构（PKI）使用受信任的证书颁发机构（Ca）颁发的证书对服务器进行身份验证，并确保数据完整性。</span><span class="sxs-lookup"><span data-stu-id="afe80-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="afe80-p102">传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。</span><span class="sxs-lookup"><span data-stu-id="afe80-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="afe80-112">用于用户身份验证的行业标准协议，如果可能。</span><span class="sxs-lookup"><span data-stu-id="afe80-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="afe80-113">Windows PowerShell 提供默认启用的安全功能，这样用户便无法轻松或在不知情的情况下运行脚本。</span><span class="sxs-lookup"><span data-stu-id="afe80-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="afe80-114">这些基本安全元素协同工作以定义受信任的用户、服务器、连接和操作，以帮助确保 Lync Server 2013 的安全基础。</span><span class="sxs-lookup"><span data-stu-id="afe80-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afe80-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="afe80-115">In This Section</span></span>

<span data-ttu-id="afe80-116">本节中的主题介绍每个基本元素如何工作以增强 Lync Server 基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="afe80-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="afe80-117">Lync Server 2013 的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="afe80-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="afe80-118">Lync Server 2013 的基于角色的访问控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="afe80-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="afe80-119">Lync Server 2013 的公钥基础结构</span><span class="sxs-lookup"><span data-stu-id="afe80-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="afe80-120">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="afe80-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="afe80-121">Lync Server 2013 加密</span><span class="sxs-lookup"><span data-stu-id="afe80-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="afe80-122">Lync Server 2013 的用户和客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="afe80-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="afe80-123">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="afe80-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

