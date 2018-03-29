---
title: 证书申请 （返回）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 联机的证书申请状态页将显示重要信息成功创建和颁发联机证书请求而产生。 此页提供唯一标识证书的证书指纹。 默认情况下被选中复选框分配到 Skype 业务服务器证书用途的证书。 如果您单击完成，该证书将自动分配给 Lync Server 2013 期间创建的证书申请的步骤定义的目的。 默认情况下，将分配证书的目的是：
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-returned"></a><span data-ttu-id="572df-107">证书申请 （返回）</span><span class="sxs-lookup"><span data-stu-id="572df-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="572df-108">**联机的证书申请状态**页将显示重要信息成功创建和颁发联机证书请求而产生。</span><span class="sxs-lookup"><span data-stu-id="572df-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="572df-109">此页提供唯一标识证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="572df-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="572df-110">默认情况下，**分配到企业服务器证书用途的 Skype 此证书**复选框被选中。</span><span class="sxs-lookup"><span data-stu-id="572df-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="572df-111">如果单击**完成**后，该证书将自动分配给 Lync Server 2013 期间创建的证书申请的步骤定义的目的。</span><span class="sxs-lookup"><span data-stu-id="572df-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="572df-112">默认情况下，将分配证书的目的是：</span><span class="sxs-lookup"><span data-stu-id="572df-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="572df-113">服务器默认值用于相互传输层安全性 (MTLS)-连接到客户端和其他服务器</span><span class="sxs-lookup"><span data-stu-id="572df-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="572df-114">内部的 web 服务在内部网站上的客户端和服务器连接的传输层安全性/安全套接字层 (TLS/SSL) 服务网站</span><span class="sxs-lookup"><span data-stu-id="572df-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="572df-115">外部的 web 服务在外部网站上的客户端和服务器连接的 TLS/SSL 服务网站</span><span class="sxs-lookup"><span data-stu-id="572df-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="572df-116">请单击要查看的证书，确认证书的属性是您想，且证书已准备好应用，并将投入使用的服务器上**查看证书详细信息**。</span><span class="sxs-lookup"><span data-stu-id="572df-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="572df-117">单击**完成**以完成联机证书请求过程。</span><span class="sxs-lookup"><span data-stu-id="572df-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="572df-118">如果您选择**分配到 Skype 业务服务器证书用法此证书**复选框，将自动分配证书。</span><span class="sxs-lookup"><span data-stu-id="572df-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="572df-119">如果您选择以清除此复选框，您必须分配一个单独的步骤中的证书。</span><span class="sxs-lookup"><span data-stu-id="572df-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="572df-120">如果颁发证书颁发机构 (CA) 的根证书没有在计算机的受信任根证书颁发机构存储中，或者如果中间 CA 证书不正确的存储区中，您将看到摘要状态，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="572df-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="572df-121">您没有选择将证书分配。</span><span class="sxs-lookup"><span data-stu-id="572df-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="572df-122">要完成证书分配过程中，必须颁发 CA 根证书和任何中间 CA 证书，导入，然后将证书分配主证书向导页面上单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="572df-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

