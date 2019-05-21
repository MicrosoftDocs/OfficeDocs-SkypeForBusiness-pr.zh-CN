---
title: 证书向导
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: 要“请求”、“分配”、“删除”或“查看”证书，可使用证书向导。 必须以 RTCUniversalServerAdmins 组成员的身份登录。 要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。 若要向你的组织的公钥基础结构 (PKI) 申请证书, 你需要确认需要的其他 (如果有) 组成员身份。 在请求任务期间, 你可以输入将用于从你的 PKI 颁发 CA 申请证书的备用凭据。
ms.openlocfilehash: daafbdd6730b86b7509323528405bec5277d264d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298959"
---
# <a name="certificate-wizard"></a><span data-ttu-id="38fd1-107">证书向导</span><span class="sxs-lookup"><span data-stu-id="38fd1-107">Certificate Wizard</span></span>
 
<span data-ttu-id="38fd1-108">要“**请求**”、“**分配**”、“**删除**”或“**查看**”证书，可使用证书向导。</span><span class="sxs-lookup"><span data-stu-id="38fd1-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="38fd1-109">必须以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="38fd1-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="38fd1-110">要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。</span><span class="sxs-lookup"><span data-stu-id="38fd1-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="38fd1-111">若要向你的组织的公钥基础结构 (PKI) 申请证书, 你需要确认需要的其他 (如果有) 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="38fd1-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="38fd1-112">在请求任务期间, 你可以输入将用于从你的 PKI 颁发 CA 申请证书的备用凭据。</span><span class="sxs-lookup"><span data-stu-id="38fd1-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="38fd1-113">要请求新证书，请单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="38fd1-114">要分配尚未分配的证书，请单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="38fd1-115">要删除先前分配的证书，请单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38fd1-p103">仅当先前已分配证书时，“**删除**”按钮才可用。如果“**删除**”按钮不可用（灰显），则表明尚未分配任何证书。</span><span class="sxs-lookup"><span data-stu-id="38fd1-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="38fd1-118">要查看已分配的证书，请单击“**查看**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38fd1-p104">仅当先前已分配证书时，“**查看**”按钮才可用。如果“**查看**”按钮灰显，则表明尚未分配任何证书。</span><span class="sxs-lookup"><span data-stu-id="38fd1-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="38fd1-121">要刷新当前证书分配屏幕，请单击“**刷新**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="38fd1-122">要导入证书存储中没有的证书，请单击“**导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="38fd1-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38fd1-123">“**导入证书**”通常用于处理通过某个进程接收而非通过证书向导请求的证书。</span><span class="sxs-lookup"><span data-stu-id="38fd1-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="38fd1-124">例如，KPI 管理员会创建证书，然后提供给您使用。</span><span class="sxs-lookup"><span data-stu-id="38fd1-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="38fd1-125">使用**导入证书**将证书导入到计算机的证书存储中, 并使其可供 Skype For business 服务器分配。</span><span class="sxs-lookup"><span data-stu-id="38fd1-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="38fd1-p106">要完成需要 CA 管理员批准的从组织中的 CA 请求证书的过程，请单击“**处理待处理的请求**”。证书请求应该返回待处理状态，并显示待处理请求的标识号。要继续处理待处理状态的证书，请单击“**刷新**”以启用“**处理待处理的请求**”按钮。“**处理待处理的请求**”按钮将变得可用（不再灰显）。然后您就可以尝试检索待处理的请求，但是请求状态仍将保持为待处理，直至 CA 管理员颁发或拒绝该证书。如果不存在证书向导创建的有效的待处理请求，则此按钮将不可用。</span><span class="sxs-lookup"><span data-stu-id="38fd1-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

