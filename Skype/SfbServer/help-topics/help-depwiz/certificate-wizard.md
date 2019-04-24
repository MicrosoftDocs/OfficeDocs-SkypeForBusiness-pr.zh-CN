---
title: 证书向导
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: 要“请求”、“分配”、“删除”或“查看”证书，可使用证书向导。 必须以 RTCUniversalServerAdmins 组成员的身份登录。 要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。 若要从您的组织的公钥基础结构 (PKI) 申请证书，您需要确认什么其他 — 如果任何 — 组需要的成员身份。 期间请求任务中，您可以输入备用凭据将用于请求来自 PKI 证书的颁发 CA。
ms.openlocfilehash: 7d20fe489928a430c972c7e48e0938ff1eb1622d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220443"
---
# <a name="certificate-wizard"></a><span data-ttu-id="2f526-107">证书向导</span><span class="sxs-lookup"><span data-stu-id="2f526-107">Certificate Wizard</span></span>
 
<span data-ttu-id="2f526-108">要“**请求**”、“**分配**”、“**删除**”或“**查看**”证书，可使用证书向导。</span><span class="sxs-lookup"><span data-stu-id="2f526-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="2f526-109">必须以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2f526-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="2f526-110">要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。</span><span class="sxs-lookup"><span data-stu-id="2f526-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="2f526-111">若要从您的组织的公钥基础结构 (PKI) 申请证书，您需要确认什么其他 — 如果任何 — 组需要的成员身份。</span><span class="sxs-lookup"><span data-stu-id="2f526-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="2f526-112">期间请求任务中，您可以输入备用凭据将用于请求来自 PKI 证书的颁发 CA。</span><span class="sxs-lookup"><span data-stu-id="2f526-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="2f526-113">要请求新证书，请单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="2f526-114">要分配尚未分配的证书，请单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="2f526-115">要删除先前分配的证书，请单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f526-p103">仅当先前已分配证书时，“**删除**”按钮才可用。如果“**删除**”按钮不可用（灰显），则表明尚未分配任何证书。</span><span class="sxs-lookup"><span data-stu-id="2f526-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="2f526-118">要查看已分配的证书，请单击“**查看**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f526-p104">仅当先前已分配证书时，“**查看**”按钮才可用。如果“**查看**”按钮灰显，则表明尚未分配任何证书。</span><span class="sxs-lookup"><span data-stu-id="2f526-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="2f526-121">要刷新当前证书分配屏幕，请单击“**刷新**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="2f526-122">要导入证书存储中没有的证书，请单击“**导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="2f526-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f526-123">“**导入证书**”通常用于处理通过某个进程接收而非通过证书向导请求的证书。</span><span class="sxs-lookup"><span data-stu-id="2f526-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="2f526-124">例如，KPI 管理员会创建证书，然后提供给您使用。</span><span class="sxs-lookup"><span data-stu-id="2f526-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="2f526-125">使用**导入证书**，以将证书导入计算机的证书存储并使其可供业务服务器分配的 Skype。</span><span class="sxs-lookup"><span data-stu-id="2f526-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="2f526-p106">要完成需要 CA 管理员批准的从组织中的 CA 请求证书的过程，请单击“**处理待处理的请求**”。证书请求应该返回待处理状态，并显示待处理请求的标识号。要继续处理待处理状态的证书，请单击“**刷新**”以启用“**处理待处理的请求**”按钮。“**处理待处理的请求**”按钮将变得可用（不再灰显）。然后您就可以尝试检索待处理的请求，但是请求状态仍将保持为待处理，直至 CA 管理员颁发或拒绝该证书。如果不存在证书向导创建的有效的待处理请求，则此按钮将不可用。</span><span class="sxs-lookup"><span data-stu-id="2f526-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

