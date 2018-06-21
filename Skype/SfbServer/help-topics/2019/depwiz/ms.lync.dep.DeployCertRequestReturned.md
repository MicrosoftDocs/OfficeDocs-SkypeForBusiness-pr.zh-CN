---
title: 证书请求 （已返回）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 联机证书请求状态页将显示的重要信息从成功创建和发布的联机证书请求的结果。 此页提供唯一标识证书的证书指纹。 默认情况下，选中分配此证书 Skype 的业务服务器证书用法复选框。 如果单击完成时，证书将自动分配给 Lync Server 2013 的过程创建证书申请的步骤中定义，以便。 默认情况下，将分配证书的目的是：
ms.openlocfilehash: 74ee0fba06add0d069473bc5b6b580c1b1d5810a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976595"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="8a1f4-107">证书请求 （已返回）</span><span class="sxs-lookup"><span data-stu-id="8a1f4-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="8a1f4-108">**联机证书请求状态**页将显示的重要信息从成功创建和发布的联机证书请求的结果。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="8a1f4-109">此页提供唯一标识证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="8a1f4-110">默认情况下，选中**分配此证书 Skype 的业务服务器证书用法**复选框。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="8a1f4-111">如果单击**完成**时，证书将自动分配给 Lync Server 2013 的过程创建证书申请的步骤中定义，以便。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="8a1f4-112">默认情况下，将分配证书的目的是：</span><span class="sxs-lookup"><span data-stu-id="8a1f4-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="8a1f4-113">服务器默认值为相互传输层安全性 (MTLS) 的客户端之间的连接及其他服务器</span><span class="sxs-lookup"><span data-stu-id="8a1f4-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="8a1f4-114">内部-web 服务客户端和服务器的内部 Web 服务站点上连接的传输层安全性/安全套接字层 (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="8a1f4-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="8a1f4-115">外部-web 服务客户端和服务器的外部 Web 服务站点上连接的 TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="8a1f4-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="8a1f4-116">单击**查看证书详细信息**，若要查看确认证书的属性包括您的目的，并已准备好应用并置于服务器上使用证书的证书。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="8a1f4-117">单击**完成**以完成联机证书请求进程。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="8a1f4-118">如果您选择了**分配此证书 Skype 的业务服务器证书用法**复选框，将自动分配证书。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="8a1f4-119">如果您选择清除此复选框，就必须分配一个单独的步骤中的证书。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8a1f4-120">如果颁发的证书颁发机构 (CA) 根证书不在计算机的受信任的根证书颁发机构存储，或者中间 CA 证书不在适当的存储区中，您将看到摘要的状态，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="8a1f4-121">您没有分配证书选项。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="8a1f4-122">若要完成证书分配过程，您必须导入发证 CA 根证书和所有中间 CA 证书，然后通过单击证书向导的主页上的**分配**分配证书。</span><span class="sxs-lookup"><span data-stu-id="8a1f4-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

