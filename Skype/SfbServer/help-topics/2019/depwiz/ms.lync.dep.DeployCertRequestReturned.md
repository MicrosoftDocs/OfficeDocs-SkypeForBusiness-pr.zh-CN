---
title: 证书请求（已返回）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: "\"联机证书请求状态\" 页面向你显示成功创建和发出在线证书请求所产生的重要信息。 此页面提供唯一标识证书的证书指纹。 默认情况下, 将选中 \"将此证书分配给 Skype for business 服务器证书使用情况\" 复选框。 如果单击 \"完成\", 则证书将自动分配给 Skype for business 服务器, 目的是在证书请求的创建步骤中定义。 默认情况下, 将分配证书的目的是:"
ms.openlocfilehash: 02d114ff55360f3e88a866485759510ce5f107c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278019"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="6ff76-107">证书请求（已返回）</span><span class="sxs-lookup"><span data-stu-id="6ff76-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="6ff76-108">"**联机证书请求状态**" 页面向你显示成功创建和发出在线证书请求所产生的重要信息。</span><span class="sxs-lookup"><span data-stu-id="6ff76-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="6ff76-109">此页面提供唯一标识证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="6ff76-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="6ff76-110">默认情况下, 将选中 "**将此证书分配给 Skype for Business 服务器证书使用**情况" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6ff76-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="6ff76-111">如果单击 "**完成**", 则证书将自动分配给 Skype For business 服务器, 目的是在证书请求的创建步骤中定义。</span><span class="sxs-lookup"><span data-stu-id="6ff76-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="6ff76-112">默认情况下, 将分配证书的目的是:</span><span class="sxs-lookup"><span data-stu-id="6ff76-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="6ff76-113">相互传输层安全性 (MTLS) 的服务器默认值-与客户端和其他服务器的连接</span><span class="sxs-lookup"><span data-stu-id="6ff76-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="6ff76-114">Web 服务内部-用于传输层安全/安全套接字层 (TLS/SSL) 的内部 Web 服务网站上的客户端和服务器连接</span><span class="sxs-lookup"><span data-stu-id="6ff76-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="6ff76-115">适用于 TLS/SSL 的外部 Web 服务网站上的 Web 服务外部客户端和服务器连接</span><span class="sxs-lookup"><span data-stu-id="6ff76-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="6ff76-116">单击 "**查看证书详细信息**" 以查看证书, 以确认证书的属性是否符合你的要求, 以及证书是否已准备好进行应用, 并将其放入服务器上使用。</span><span class="sxs-lookup"><span data-stu-id="6ff76-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="6ff76-117">单击 "**完成**" 以完成联机证书请求过程。</span><span class="sxs-lookup"><span data-stu-id="6ff76-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="6ff76-118">如果选中 "**将此证书分配给 Skype for Business 服务器证书使用**情况" 复选框, 则会自动分配证书。</span><span class="sxs-lookup"><span data-stu-id="6ff76-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="6ff76-119">如果您选择清除此复选框, 则必须在单独的步骤中分配证书。</span><span class="sxs-lookup"><span data-stu-id="6ff76-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6ff76-120">如果颁发证书颁发机构 (CA) 根证书不在计算机的受信任的根证书颁发机构存储中, 或者中间 CA 证书不在正确的应用商店中, 你将看到摘要状态, 如下图所示。</span><span class="sxs-lookup"><span data-stu-id="6ff76-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="6ff76-121">您没有分配证书的选项。</span><span class="sxs-lookup"><span data-stu-id="6ff76-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="6ff76-122">若要完成证书分配过程, 必须导入颁发 CA 根证书和任何中间 CA 证书, 然后通过单击 "主证书向导" 页面上的 "**分配**" 来分配证书。</span><span class="sxs-lookup"><span data-stu-id="6ff76-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

