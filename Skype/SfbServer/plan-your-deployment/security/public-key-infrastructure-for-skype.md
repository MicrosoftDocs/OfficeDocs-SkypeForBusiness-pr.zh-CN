---
title: Skype for Business Server 的公钥基础结构
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server 依赖证书进行服务器身份验证，并建立客户端和服务器之间以及不同服务器角色之间的信任链。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公钥基础结构 (PKI) 提供了用于建立和验证此信任链的基础结构。
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832142"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Skype for Business Server 的公钥基础结构
 
Skype for Business Server 依赖证书进行服务器身份验证，并建立客户端和服务器之间以及不同服务器角色之间的信任链。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公钥基础结构 (PKI) 提供了用于建立和验证此信任链的基础结构。
  
证书是数字 ID。 它们通过名称来标识某台服务器并指定其属性。 为了确保证书上的信息有效，证书必须由连接到该服务器的客户端或其他服务器信任的 CA 颁发。 如果服务器仅与专用网络中的其他客户端和服务器建立连接，则 CA 可以是企业 CA。 如果服务器与专用网络外部的实体进行交互，则可能需要公共 CA。
  
即使证书上的信息是有效的，也必须通过某些方法来确认提供证书的服务器实际上就是证书所代表的服务器。在这种情况下可以使用 Windows PKI。
  
每个证书都链接到一个公钥。证书上指明的服务器持有一个只有它自己知道的对应的私钥。连接的客户端或服务器使用公钥对随机的信息段进行加密并将其发送到该服务器。如果该服务器将此信息解密并以纯文本形式返回此信息，则连接的实体就可以确定该服务器持有证书的私钥，因此该服务器即是证书上指明的服务器。
  
> [!NOTE]
> 并非所有公共 CA 都符合 Skype for Business Server 证书的要求。 建议您参考经认证的公共 CA 供应商的列表以满足您使用公共证书的需要。 有关详细信息，请参阅统 [一通信证书合作伙伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。 
  
## <a name="crl-distribution-points"></a>CRL 分发点

Skype for Business Server 要求所有服务器证书包含一个或多个证书吊销列表 (CRL) 分发点。 可从 CRL 分发点 (CDP) 下载 CRL，以便确认证书自颁发以来未被吊销且仍处于有效期内。 CRL 分发点在证书的属性中标记为一个 URL，它通常是安全 HTTP。
  
## <a name="enhanced-key-usage"></a>增强型密钥使用

Skype for Business Server 需要所有服务器证书来支持增强型密钥 (EKU) EKU 证书，以便进行服务器身份验证。 配置用于服务器身份验证的 EKU 字段意味着证书可以对服务器进行身份验证。 此 EKU 对 MTLS 至关重要。 EKU 中可能存在多个条目以允许将证书用于多个目的。
  

