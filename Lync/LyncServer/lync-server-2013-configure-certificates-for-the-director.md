---
title: Lync Server 2013：为控制器配置证书
description: Lync Server 2013：为控制器配置证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cadc3f51b036120e21c3f1e6201f872aacafef69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578068"
---
# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="06f6b-103">在 Lync Server 2013 中为控制器配置证书</span><span class="sxs-lookup"><span data-stu-id="06f6b-103">Configure certificates for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06f6b-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="06f6b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="06f6b-105">在运行证书向导时，请确保您使用作为组（已为其分配您将使用的证书模板类型的适当权限）的成员的帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="06f6b-105">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="06f6b-106">默认情况下，Lync Server 2013 证书请求将使用 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="06f6b-106">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="06f6b-107">如果您使用作为 RTCUniversalServerAdmins 组的成员的帐户来通过此模板请求证书，则请确保已为该组分配使用此模板所需的注册权限。</span><span class="sxs-lookup"><span data-stu-id="06f6b-107">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="06f6b-108">每个控制器都需要默认证书、Web 内部证书和 Web 外部证书。</span><span class="sxs-lookup"><span data-stu-id="06f6b-108">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="06f6b-109">有关控制器的证书要求的详细信息，请参阅规划文档中的 [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="06f6b-109">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="06f6b-p103">使用以下过程配置控制器证书。对每台控制器重复此过程。此过程的步骤介绍如何在组织部署的内部企业根证书颁发机构 (CA) 中通过脱机请求处理来配置证书。有关从外部 CA 获取证书的详细信息，请与支持团队联系。</span><span class="sxs-lookup"><span data-stu-id="06f6b-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="06f6b-114">为控制器或控制器池配置证书</span><span class="sxs-lookup"><span data-stu-id="06f6b-114">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="06f6b-115">在 "Lync Server 部署向导" 的 " **步骤3：请求、安装或分配证书**" 旁边，单击 " **运行**"。</span><span class="sxs-lookup"><span data-stu-id="06f6b-115">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="06f6b-116">在 **“证书向导”** 页上，单击 **“请求”**。</span><span class="sxs-lookup"><span data-stu-id="06f6b-116">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="06f6b-117">在“证书请求”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-117">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="06f6b-118">在“延迟的请求或即时请求”\*\*\*\* 页上，接受默认的“立即将请求发送至联机证书颁发机构”\*\*\*\* 选项，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-118">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="06f6b-119">在“选择证书颁发机构(CA)”\*\*\*\* 页上，单击要使用的内部 Windows 证书颁发机构，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-119">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="06f6b-120">如果登录时使用的帐户没有足够的权限请求证书，则在“证书颁发机构帐户”\*\*\*\* 页上，指定要使用的备用凭据，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-120">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="06f6b-121">在“指定替代证书模板”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-121">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="06f6b-122">在“名称和安全设置”\*\*\*\* 页上，可以指定一个“友好名称”\*\*\*\*，并接受 2048 位密钥长度，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-122">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="06f6b-123">在“组织信息”\*\*\*\* 页上，可选择指定组织信息，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-123">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="06f6b-124">在“地理信息”\*\*\*\* 页上，可选择指定地理信息，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-124">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="06f6b-125">在“使用者名称/使用者替代名称”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-125">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06f6b-126">使用者替代名称列表应包含要安装控制器的计算机的名称（如果是单个控制器）或控制器池名称，以及为组织配置的简单 URL 名称。</span><span class="sxs-lookup"><span data-stu-id="06f6b-126">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="06f6b-127">在“使用者替代名称(SAN)的 SIP 域设置”\*\*\*\* 页上，为希望控制器处理的所有域选择“已配置的 SIP 域”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-127">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="06f6b-128">在“配置其他使用者替代名称”\*\*\*\* 页上，添加所需的任何其他使用者替代名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-128">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="06f6b-129">在“证书请求摘要”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-129">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="06f6b-130">命令运行完以后，在“正在执行命令”\*\*\*\* 页上单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-130">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="06f6b-131">在“联机证书请求状态”\*\*\*\* 页上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-131">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="06f6b-132">在“证书分配”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-132">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06f6b-133">如果要查看证书，请在列表中双击相应的证书。</span><span class="sxs-lookup"><span data-stu-id="06f6b-133">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="06f6b-134">在“证书分配摘要”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-134">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="06f6b-135">命令运行完以后，在“正在执行命令”\*\*\*\* 页上单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-135">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="06f6b-136">在“证书向导”\*\*\*\* 页上，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06f6b-136">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

