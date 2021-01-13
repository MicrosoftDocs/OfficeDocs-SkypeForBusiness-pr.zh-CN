---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: “联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。 该页提供了可以唯一标识证书的证书指纹。 默认情况下，选中"将此证书分配给 Skype for Business Server 证书用法"复选框。 如果单击"完成"，证书将自动分配给 Lync Server 2013，用于证书请求的创建步骤中定义的目的。 默认情况下，分配证书的目的如下：
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805142"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="c8e5b-107">证书请求（已返回）</span><span class="sxs-lookup"><span data-stu-id="c8e5b-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="c8e5b-108">“联机证书请求状态”页将显示与成功创建并发出联机证书请求有关的重要信息。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="c8e5b-109">该页提供了可以唯一标识证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="c8e5b-110">默认情况下，选中"将 **此证书分配给 Skype for Business Server 证书用法** "复选框。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="c8e5b-111">如果单击 **"完成**"，证书将自动分配给 Lync Server 2013，用于证书请求的创建步骤中定义的目的。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="c8e5b-112">默认情况下，分配证书的目的如下：</span><span class="sxs-lookup"><span data-stu-id="c8e5b-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="c8e5b-113">相互传输层安全性的服务器默认值 (MTLS) - 与客户端和其他服务器的连接</span><span class="sxs-lookup"><span data-stu-id="c8e5b-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="c8e5b-114">Web 服务内部 - 内部 Web 服务网站上传输层安全性/安全套接字层 (TLS/SSL) </span><span class="sxs-lookup"><span data-stu-id="c8e5b-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="c8e5b-115">Web 服务外部 - 外部 Web 服务网站上 TLS/SSL 的客户端和服务器连接</span><span class="sxs-lookup"><span data-stu-id="c8e5b-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="c8e5b-116">单击“查看证书详细信息”可查看证书，以确认证书属性是否符合您的预期，并确认证书是否已准备好在服务器上应用并投入使用。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="c8e5b-117">单击“完成”以完成联机证书请求过程。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="c8e5b-118">如果选中了"将 **此证书** 分配给 Skype for Business Server 证书用法"复选框，将自动分配该证书。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="c8e5b-119">如果选择清除此复选框，则必须通过单独的步骤分配证书。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c8e5b-120">如果颁发证书颁发机构 (CA) 根证书不在计算机的受信任根证书颁发机构存储中，或者中间 CA 证书不在正确的存储中，则会看到摘要状态，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="c8e5b-121">没有分配证书的选项。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="c8e5b-122">要完成证书分配过程，必须导入证书颁发机构根证书和所有中间 CA 证书，然后通过在证书向导主页上单击“分配”来分配证书。</span><span class="sxs-lookup"><span data-stu-id="c8e5b-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

