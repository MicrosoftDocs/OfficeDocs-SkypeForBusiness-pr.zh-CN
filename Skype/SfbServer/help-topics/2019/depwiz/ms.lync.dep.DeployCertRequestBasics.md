---
title: 证书请求（基本）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "\"名称和安全设置\"页提供了用于定义友好名称的文本框、私钥和公钥对的位长度的下拉列表，以及允许您将证书的私钥标记为可导出的复选框。"
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830412"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="7eebf-103">证书请求（基本）</span><span class="sxs-lookup"><span data-stu-id="7eebf-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="7eebf-104">"名称和安全设置"页提供了一个文本框来定义友好名称、私钥和公钥对的 **位** 长度的下拉列表，以及一个允许您将证书的私钥标记为可导出的 **复选框**。</span><span class="sxs-lookup"><span data-stu-id="7eebf-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="7eebf-105">证书上的友好或简单名称是容易识别的名称，使查看证书的人员更容易识别它。</span><span class="sxs-lookup"><span data-stu-id="7eebf-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="7eebf-106">可供选择的私钥和公钥对的位长度为 1024、2048 或 4096。</span><span class="sxs-lookup"><span data-stu-id="7eebf-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="7eebf-107">选中"将证书的私钥标记为可导出"复选框将允许导出证书和私钥，并移动到其他计算机或服务器。</span><span class="sxs-lookup"><span data-stu-id="7eebf-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="7eebf-108">唯一需要这样做的时间是在为 MRAS 服务中的媒体中继身份验证服务创建边缘 (池) 。</span><span class="sxs-lookup"><span data-stu-id="7eebf-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7eebf-109">为了帮助维护证书和密钥对的安全性，应仅在绝对有必要时选择将证书的私钥标记为可导出选项。</span><span class="sxs-lookup"><span data-stu-id="7eebf-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

