---
title: 公钥基础结构 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype 业务 server 依靠证书进行服务器身份验证以及建立之间的不同服务器角色和客户端和服务器之间的信任链。 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2 和 Windows Server 2008 公钥基础结构 (PKI) 提供用于建立和验证这种信任链的基础结构。
ms.openlocfilehash: 7ff0c2b7d40b2e650dd7c66ecfe23d4981e6f7af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897462"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a><span data-ttu-id="1052a-104">公钥基础结构 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="1052a-104">Public Key Infrastructure for Skype for Business Server</span></span>
 
<span data-ttu-id="1052a-105">Skype 业务 server 依靠证书进行服务器身份验证以及建立之间的不同服务器角色和客户端和服务器之间的信任链。</span><span class="sxs-lookup"><span data-stu-id="1052a-105">Skype for Business Server relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="1052a-106">Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2 和 Windows Server 2008 公钥基础结构 (PKI) 提供用于建立和验证这种信任链的基础结构。</span><span class="sxs-lookup"><span data-stu-id="1052a-106">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, and Windows Server 2008 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>
  
<span data-ttu-id="1052a-p103">证书是数字 ID。它们通过名称来标识某台服务器并指定其属性。要确保证书上的信息有效，该证书必须由连接到该服务器的客户端或其他服务器信任的 CA 颁发。如果服务器仅与专用网络中的其他客户端和服务器建立连接，则 CA 可以是企业 CA。如果服务器与专用网络外部的实体进行交互，则可能需要公共 CA。</span><span class="sxs-lookup"><span data-stu-id="1052a-p103">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>
  
<span data-ttu-id="1052a-p104">即使证书上的信息是有效的，也必须通过某些方法来确认提供证书的服务器实际上就是证书所代表的服务器。在这种情况下可以使用 Windows PKI。</span><span class="sxs-lookup"><span data-stu-id="1052a-p104">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>
  
<span data-ttu-id="1052a-p105">每个证书都链接到一个公钥。证书上指明的服务器持有一个只有它自己知道的对应的私钥。连接的客户端或服务器使用公钥对随机的信息段进行加密并将其发送到该服务器。如果该服务器将此信息解密并以纯文本形式返回此信息，则连接的实体就可以确定该服务器持有证书的私钥，因此该服务器即是证书上指明的服务器。</span><span class="sxs-lookup"><span data-stu-id="1052a-p105">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1052a-118">不是所有公共 Ca 符合业务服务器证书的 Skype 的要求。</span><span class="sxs-lookup"><span data-stu-id="1052a-118">Not all public CAs comply with the requirements of Skype for Business Server certificates.</span></span> <span data-ttu-id="1052a-119">建议您参考经认证的公共 CA 供应商的列表以满足您使用公共证书的需要。</span><span class="sxs-lookup"><span data-stu-id="1052a-119">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="1052a-120">有关详细信息，请参阅[统一通信证书伙伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。</span><span class="sxs-lookup"><span data-stu-id="1052a-120">For details, see [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898).</span></span> 
  
## <a name="crl-distribution-points"></a><span data-ttu-id="1052a-121">CRL 分发点</span><span class="sxs-lookup"><span data-stu-id="1052a-121">CRL Distribution Points</span></span>

<span data-ttu-id="1052a-122">Skype 业务服务器要求所有服务器证书包含一个或多个证书吊销列表 (CRL) 分发点。</span><span class="sxs-lookup"><span data-stu-id="1052a-122">Skype for Business Server requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="1052a-123">可从 CRL 分发点 (CDP) 下载 CRL，以便确认证书自颁发以来未被吊销且仍处于有效期内。</span><span class="sxs-lookup"><span data-stu-id="1052a-123">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="1052a-124">CRL 分发点在证书的属性中标记为一个 URL，它通常是安全 HTTP。</span><span class="sxs-lookup"><span data-stu-id="1052a-124">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>
  
## <a name="enhanced-key-usage"></a><span data-ttu-id="1052a-125">增强型密钥使用</span><span class="sxs-lookup"><span data-stu-id="1052a-125">Enhanced Key Usage</span></span>

<span data-ttu-id="1052a-126">Skype 业务服务器要求所有服务器证书支持增强型密钥用法 (EKU) 用于服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="1052a-126">Skype for Business Server requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="1052a-127">配置用于服务器身份验证的 EKU 字段意味着证书可以对服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1052a-127">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="1052a-128">此 EKU 对 MTLS 至关重要。</span><span class="sxs-lookup"><span data-stu-id="1052a-128">This EKU is essential for MTLS.</span></span> <span data-ttu-id="1052a-129">EKU 中可能存在多个条目以允许将证书用于多个目的。</span><span class="sxs-lookup"><span data-stu-id="1052a-129">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>
  

