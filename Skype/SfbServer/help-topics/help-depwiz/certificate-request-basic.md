---
title: 证书请求（基本）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: 名称和安全性设置页面提供定义的友好名称，私有和公共密钥对和一个复选框，使您可以将标记为可导出的证书的专用密钥的位长的下拉列表的文本框。
ms.openlocfilehash: e9c70074a168b00288b931cb168b5fea210367c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-basic"></a><span data-ttu-id="3af9c-103">证书请求（基本）</span><span class="sxs-lookup"><span data-stu-id="3af9c-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="3af9c-104">**名称和安全性设置**页面提供定义的**友好名称**，私有和公共密钥对和一个复选框，使您能够为**Mark 证书的专用密钥的**位长**的下拉列表的文本框可导出**。</span><span class="sxs-lookup"><span data-stu-id="3af9c-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="3af9c-105">证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。</span><span class="sxs-lookup"><span data-stu-id="3af9c-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="3af9c-106">可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。</span><span class="sxs-lookup"><span data-stu-id="3af9c-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="3af9c-107">选择复选框**标记为可导出的证书的专用密钥**允许的证书和私钥导出，并将它们移动到另一台计算机或服务器。</span><span class="sxs-lookup"><span data-stu-id="3af9c-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="3af9c-108">只有在为媒体中继身份验证服务 (MRAS) 创建边缘服务器池时，才需要选中此项。</span><span class="sxs-lookup"><span data-stu-id="3af9c-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3af9c-109">为了维持证书和密钥对的安全性，您应选择标记证书的专用密钥为可导出选项仅当绝对必要。</span><span class="sxs-lookup"><span data-stu-id="3af9c-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

