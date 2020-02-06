---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: "\"名称和安全设置\" 页面提供一个文本框，用于定义友好名称、用于私钥和公钥对的位长的下拉列表，以及使你能够将证书的专用密钥标记为可导出的复选框。"
ms.openlocfilehash: 26315f24dd14989bd2832d6f28e591a7ae38cc64
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796763"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="b6567-103">证书请求（基本）</span><span class="sxs-lookup"><span data-stu-id="b6567-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="b6567-104">"**名称和安全设置**" 页面提供一个文本框，用于定义**友好名称**、用于私钥和公钥对的**位长**的下拉列表，以及使你能够将**证书的专用密钥标记为可导出**的复选框。</span><span class="sxs-lookup"><span data-stu-id="b6567-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="b6567-105">证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。</span><span class="sxs-lookup"><span data-stu-id="b6567-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="b6567-106">可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。</span><span class="sxs-lookup"><span data-stu-id="b6567-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="b6567-107">选中 "将**证书的私钥标记**为可导出" 复选框后，即可导出证书和私钥并将其移动到另一台计算机或服务器。</span><span class="sxs-lookup"><span data-stu-id="b6567-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="b6567-108">只有在为媒体中继身份验证服务 (MRAS) 创建边缘服务器池时，才需要选中此项。</span><span class="sxs-lookup"><span data-stu-id="b6567-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b6567-109">若要帮助维护证书和密钥对的安全性，应选中 "将证书的私钥标记为可导出" 选项（仅当绝对必要时）。</span><span class="sxs-lookup"><span data-stu-id="b6567-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

