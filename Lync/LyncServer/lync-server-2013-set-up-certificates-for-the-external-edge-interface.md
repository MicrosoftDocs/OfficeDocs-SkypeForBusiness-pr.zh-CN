---
title: Lync Server 2013：为外部边缘接口设置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="e53f1-102">为 Lync Server 2013 的外部边缘接口设置证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e53f1-103">_**主题上次修改时间:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e53f1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e53f1-104">当你运行证书向导时, 请确保你使用的帐户是已为你将使用的证书模板类型分配了相应权限的组的成员。</span><span class="sxs-lookup"><span data-stu-id="e53f1-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="e53f1-105">默认情况下, Lync Server 证书请求将使用 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="e53f1-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="e53f1-106">如果您使用的帐户是 RTCUniversalServerAdmins 组的成员以使用此模板申请证书, 请验证该组是否已分配使用该模板所需的注册权限。</span><span class="sxs-lookup"><span data-stu-id="e53f1-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="e53f1-107">每个边缘服务器在外围网络和 Internet 之间的接口上需要一个公共证书, 并且证书的 "使用者备用名称" 必须包含 "访问边缘" 服务和 "网络会议边缘" 服务的外部名称。完全限定的域名 (Fqdn)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="e53f1-108">有关此和其他证书要求的详细信息, 请参阅[Lync Server 2013 中的外部用户访问证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="e53f1-109">对于公共证书颁发机构 (Ca) 的列表, 该列表提供符合统一通信证书特定要求的证书, 并与 Microsoft 合作以确保它们能够使用 Lync Server 2013 证书向导, 请参阅Microsoft 知识库文章 929395, "适用于 Exchange Server 的统一通信证书合作伙伴和通信服务器", " [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)at"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="e53f1-110">在外部接口上配置证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="e53f1-111">若要在网站上的外部边缘界面上设置证书, 请使用本部分中的过程执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="e53f1-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="e53f1-112">为 Edge 服务器的外部接口创建证书请求。</span><span class="sxs-lookup"><span data-stu-id="e53f1-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="e53f1-113">向您的公共 CA 提交请求。</span><span class="sxs-lookup"><span data-stu-id="e53f1-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="e53f1-114">导入每个边缘服务器的外部接口的证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="e53f1-115">为每个边缘服务器的外部接口分配证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="e53f1-116">如果你的部署包含多台边缘服务器, 请导出证书及其私钥, 然后将其复制到其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="e53f1-117">然后, 对于每个边缘服务器, 将其导入并按上文所述进行分配。</span><span class="sxs-lookup"><span data-stu-id="e53f1-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="e53f1-118">对每个边缘服务器重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e53f1-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="e53f1-119">你可以直接从公共证书颁发机构 (CA) 请求公共证书 (如从公共 CA 的网站)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="e53f1-120">本部分中的过程对大多数证书任务使用证书向导。</span><span class="sxs-lookup"><span data-stu-id="e53f1-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="e53f1-121">如果您选择直接从公共 CA 申请证书, 则需要根据需要修改每个过程来请求、传输和导入证书, 还需要导入证书链。</span><span class="sxs-lookup"><span data-stu-id="e53f1-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="e53f1-122">从外部 CA 申请证书时, 所提供的凭据必须具有从该 CA 请求证书的权限。</span><span class="sxs-lookup"><span data-stu-id="e53f1-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="e53f1-123">每个 CA 都有一个安全策略, 用于定义允许哪些凭据 (即特定用户和组名称) 请求、颁发、管理或读取证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="e53f1-124">如果你决定使用证书 Microsoft 管理控制台 (MMC) 导入证书链和证书, 则必须将它们导入到计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="e53f1-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="e53f1-125">如果将它们导入到用户或服务证书存储, 则该证书在 Lync Server 2013 证书向导中将不可用于作业。</span><span class="sxs-lookup"><span data-stu-id="e53f1-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="e53f1-126">为边缘服务器的外部接口创建证书请求</span><span class="sxs-lookup"><span data-stu-id="e53f1-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="e53f1-127">在边缘服务器上的 "部署向导" 中, 在 "**步骤 3: 请求、安装或分配证书**" 旁边, 再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e53f1-128">如果您的组织希望支持使用 AOL 的公共即时消息 (IM) 连接, 则不能使用 Lync Server 部署向导申请证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="e53f1-129">请改为在本主题后面的 "为边缘服务器的外部接口创建证书请求以支持公共 IM 连接" 过程中执行 "为边缘服务器的外部接口创建证书请求" 中的步骤。</span><span class="sxs-lookup"><span data-stu-id="e53f1-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="e53f1-130">如果在池中的一个位置有多个边缘服务器, 则可以在任何一个边缘服务器上运行 Lync Server 2013 证书向导。</span><span class="sxs-lookup"><span data-stu-id="e53f1-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="e53f1-131">在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。</span><span class="sxs-lookup"><span data-stu-id="e53f1-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="e53f1-132">在 "**证书请求**" 页面上, 单击 "**外部边缘证书**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="e53f1-133">在 "**延迟或立即请求**" 页面上, 选中 "**立即准备请求, 但稍后发送"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e53f1-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="e53f1-134">在 "**证书请求文件**" 页面上, 键入要保存请求的文件的完整路径和文件名 (例如, c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="e53f1-135">在 "**指定备用证书模板**" 页面上, 若要使用默认 web 台模板之外的模板, 请选中 "**为所选证书颁发机构使用备用证书模板**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e53f1-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="e53f1-136">在 "**名称和安全设置**" 页面上, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="e53f1-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="e53f1-137">在 "**友好名称**" 中, 键入证书的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e53f1-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="e53f1-138">在 "**位长度**" 中, 指定位长度 (通常为默认值**2048**)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="e53f1-139">验证 "将**证书私钥标记为可导出**" 复选框是否已选中。</span><span class="sxs-lookup"><span data-stu-id="e53f1-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="e53f1-140">在 "**组织信息**" 页面上, 键入组织和组织单位的名称 (例如, "部门" 或 "部门")。</span><span class="sxs-lookup"><span data-stu-id="e53f1-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="e53f1-141">在 "**地理信息**" 页面上, 指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="e53f1-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="e53f1-142">在 "**主题名称/主题备用名称**" 页面上, 将显示要由向导自动填充的信息。</span><span class="sxs-lookup"><span data-stu-id="e53f1-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="e53f1-143">如果需要其他主题备用名称, 请在接下来的两个步骤中进行指定。</span><span class="sxs-lookup"><span data-stu-id="e53f1-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="e53f1-144">在 "**主题备用名称 (san)** " 页面上的 "SIP 域设置" 中, 选中 "域" 复选框以添加 SIP。\<sipdomain\>条目到 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="e53f1-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="e53f1-145">在 "**配置其他主题备用名称**" 页面上, 指定所需的任何其他主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="e53f1-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="e53f1-146">在 "**请求摘要**" 页面上, 查看要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="e53f1-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="e53f1-147">命令运行完毕后, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="e53f1-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="e53f1-148">若要查看证书请求的日志, 请单击 "**查看日志**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="e53f1-149">若要完成证书请求, 请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="e53f1-150">在 "**证书请求文件**" 页面上, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="e53f1-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="e53f1-151">若要查看生成的证书签名请求 (CSR) 文件, 请单击 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="e53f1-152">若要关闭向导，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="e53f1-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="e53f1-153">将输出文件复制到可将其提交到公共 CA 的位置。</span><span class="sxs-lookup"><span data-stu-id="e53f1-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="e53f1-154">为边缘服务器的外部接口创建证书请求以支持与 AOL 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="e53f1-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="e53f1-155">当需要的模板可供 CA 使用时, 请从 Edge 服务器使用以下 Windows PowerShell cmdlet 来申请证书:</span><span class="sxs-lookup"><span data-stu-id="e53f1-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="e53f1-156">Lync Server 2013 中提供的模板的默认证书名称是 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="e53f1-157">仅当需要\<使用不同\>于默认模板的模板时, 才指定模板名称。</span><span class="sxs-lookup"><span data-stu-id="e53f1-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e53f1-158">如果你的组织希望支持与 AOL 的公共 IM 连接, 你必须使用 Windows PowerShell 而不是证书向导请求将证书分配给访问边缘服务的外部边缘。</span><span class="sxs-lookup"><span data-stu-id="e53f1-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="e53f1-159">这是因为证书向导用于申请证书的 Lync Server 2013 Web 服务器模板不支持客户端 EKU 配置。</span><span class="sxs-lookup"><span data-stu-id="e53f1-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="e53f1-160">在使用 Windows PowerShell 创建证书之前, CA 管理员必须创建和部署支持客户端 EKU 的新模板。</span><span class="sxs-lookup"><span data-stu-id="e53f1-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="e53f1-161">将请求提交到公共证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="e53f1-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="e53f1-162">打开输出文件。</span><span class="sxs-lookup"><span data-stu-id="e53f1-162">Open the output file.</span></span>

2.  <span data-ttu-id="e53f1-163">复制并粘贴证书签名请求 (CSR) 的内容。</span><span class="sxs-lookup"><span data-stu-id="e53f1-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="e53f1-164">如果出现提示, 请指定以下内容:</span><span class="sxs-lookup"><span data-stu-id="e53f1-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="e53f1-165">**Microsoft**作为服务器平台。</span><span class="sxs-lookup"><span data-stu-id="e53f1-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="e53f1-166">作为版本的**IIS** 。</span><span class="sxs-lookup"><span data-stu-id="e53f1-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="e53f1-167">**Web 服务器**用作使用类型。</span><span class="sxs-lookup"><span data-stu-id="e53f1-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="e53f1-168">**PKCS7**作为响应格式。</span><span class="sxs-lookup"><span data-stu-id="e53f1-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="e53f1-169">当公共 CA 验证您的信息后, 您将收到一封电子邮件, 其中包含您的证书所需的文本。</span><span class="sxs-lookup"><span data-stu-id="e53f1-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="e53f1-170">复制电子邮件中的文本, 并将内容保存在本地计算机上的文本文件 (.txt) 中。</span><span class="sxs-lookup"><span data-stu-id="e53f1-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="e53f1-171">导入边缘服务器的外部接口的证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="e53f1-172">以管理员组的成员身份登录到创建证书请求的同一边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="e53f1-173">在部署向导的 "**部署边缘服务器**" 页面上, 在 "**步骤 3: 请求、安装或分配证书**" 旁边,**再次**单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="e53f1-174">在 "**可用证书任务**" 页面上, 单击 "**从 p7b、.pfx 或 .Cer 文件导入证书"**。</span><span class="sxs-lookup"><span data-stu-id="e53f1-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="e53f1-175">在 "**导入证书**" 页面上, 单击 "**浏览**" 以查找并选择你为 Edge 服务器的外部接口请求的证书 (或者, 你可以键入完整路径和文件名)。</span><span class="sxs-lookup"><span data-stu-id="e53f1-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="e53f1-176">如果证书包含私钥, 请选择 "**证书文件包含证书的私钥**", 然后键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="e53f1-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="e53f1-177">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-177">Click **Next**.</span></span>

5.  <span data-ttu-id="e53f1-178">在 "**导入证书摘要**" 页面上, 查看摘要, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="e53f1-179">在**执行命令**时, 查看导入的结果, 单击 "**查看日志**以了解详细信息", 然后单击 "**完成**" 以完成证书导入。</span><span class="sxs-lookup"><span data-stu-id="e53f1-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="e53f1-180">如果你要配置 Edge 服务器池, 请按照本主题后面部分的 "导出证书中包含 Edge 服务器的私钥" 过程中所述, 导出证书及其私钥。</span><span class="sxs-lookup"><span data-stu-id="e53f1-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="e53f1-181">将导出的证书文件复制到其他边缘服务器, 然后将其导入到每台边缘服务器上的计算机存储中。</span><span class="sxs-lookup"><span data-stu-id="e53f1-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="e53f1-182">导出具有池中的边缘服务器的私钥的证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="e53f1-183">以管理员组成员的身份登录到您在其中导入证书的同一边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="e53f1-184">单击 "**开始**", 单击 "**运行**", 然后键入 " **MMC**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="e53f1-185">在 Microsoft 管理控制台 (MMC) 控制台中, 单击 "**文件**", 然后单击 "**添加/删除管理单元**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="e53f1-186">在 "**添加或删除管理单元**" 中, 单击 "**证书**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="e53f1-187">在 "**证书**" 对话框中, 选择 "**计算机帐户**", 单击 "**下一步**", 选择 "**本地计算机:" (运行此控制台的计算机)** , 单击 "**完成**", 然后单击 **"确定"** 以\*\*\*\* 完整的 MMC 控制台配置。</span><span class="sxs-lookup"><span data-stu-id="e53f1-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="e53f1-188">双击 "**证书 (本地计算机)** " 以展开证书存储, 双击 "**个人**", 然后双击 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e53f1-189">如果本地计算机的 "证书个人" 存储中没有证书, 则没有与导入的证书相关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="e53f1-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="e53f1-190">查看请求和导入步骤。</span><span class="sxs-lookup"><span data-stu-id="e53f1-190">Review the request and import steps.</span></span> <span data-ttu-id="e53f1-191">如果问题仍然存在, 请联系您的证书颁发机构管理员或提供商。</span><span class="sxs-lookup"><span data-stu-id="e53f1-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="e53f1-192">在**本地计算机的 "证书个人" 存储**中, 右键单击要导出的证书, 单击 "**所有任务**", 然后单击 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="e53f1-193">在 "证书导出向导" 中, 单击 "**下一步**", 选择 **"是, 导出私钥**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e53f1-194">如果选择<STRONG>"是", 则导出私钥</STRONG>不可用, 与此证书关联的私钥未标记为 "导出"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="e53f1-195">您需要再次申请证书, 确保证书已标记为允许导出私钥, 然后您才能继续导出操作。</span><span class="sxs-lookup"><span data-stu-id="e53f1-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="e53f1-196">联系您的证书颁发机构管理员或提供商。</span><span class="sxs-lookup"><span data-stu-id="e53f1-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="e53f1-197">在 "导出文件格式" 对话框中, 选择 "**个人信息\#交换-PKCS 12 (。PFX)** , 然后选择以下操作:</span><span class="sxs-lookup"><span data-stu-id="e53f1-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="e53f1-198">如果可能, 包括证书路径中的所有证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="e53f1-199">导出所有扩展属性</span><span class="sxs-lookup"><span data-stu-id="e53f1-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="e53f1-200">从边缘服务器导出证书时, 如果导出成功, 请勿选择 "<STRONG>删除私钥"</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e53f1-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="e53f1-201">选择此选项将要求你将证书和私钥导入此 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="e53f1-202">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-202">Click **Next**.</span></span>

11. <span data-ttu-id="e53f1-203">键入私钥的密码, 再次键入密码进行确认, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="e53f1-204">为导出的证书键入路径和文件名，并使用文件扩展名 .pfx。</span><span class="sxs-lookup"><span data-stu-id="e53f1-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="e53f1-205">该路径必须可由池中的所有其他边缘服务器访问, 或可通过可移动媒体 (例如, USB 闪存驱动器) 进行传输。</span><span class="sxs-lookup"><span data-stu-id="e53f1-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="e53f1-206">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-206">Click **Next**.</span></span>

13. <span data-ttu-id="e53f1-207">查看**完成证书导出向导**中的摘要, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="e53f1-208">在 "成功导出" 对话框中, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e53f1-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="e53f1-209">按照本主题前面的 "导入用于边缘服务器的外部接口的证书" 过程中所述的步骤将导出的证书文件导入其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e53f1-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="e53f1-210">为边缘服务器的外部接口分配证书</span><span class="sxs-lookup"><span data-stu-id="e53f1-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="e53f1-211">在每个边缘服务器上的 "部署向导" 中, 在 "**步骤 3: 请求、安装或分配证书**" 旁边, 再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="e53f1-212">在 "**可用的证书任务**" 页面上, 单击 "**分配现有证书**"。</span><span class="sxs-lookup"><span data-stu-id="e53f1-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="e53f1-213">在 "**证书分配**" 页面上, 单击 "**外部边缘证书**", 然后选中 "**高级证书用法**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e53f1-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="e53f1-214">在 "**高级证书用法**" 页面上, 选中 "所有复选框" 为所有使用实例分配证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="e53f1-215">在 "**证书存储**" 页面上, 选择为 Edge 服务器的外部接口请求和导入的公共证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e53f1-216">如果您请求和导入的证书不在列表中, 则其中一种故障排除方法是验证证书的使用者名称和主题备用名称是否满足证书的所有要求, 以及是否手动导入证书和证书链, 而不是使用上述过程, 而是证书位于正确的证书存储 (计算机证书存储, 而不是用户或服务证书存储) 中。</span><span class="sxs-lookup"><span data-stu-id="e53f1-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="e53f1-217">在 "**证书分配摘要**" 页面上, 查看您的设置, 然后单击 "**下一步**" 以分配证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="e53f1-218">在向导完成页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="e53f1-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="e53f1-219">使用此过程分配边缘证书后, 在每台服务器上打开 "证书" 管理单元, 展开 "**证书 (本地计算机)**", 展开 "**个人**", 单击 "**证书**", 然后验证 "详细信息" 窗格中的已列出证书。</span><span class="sxs-lookup"><span data-stu-id="e53f1-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="e53f1-220">如果你的部署包含多个边缘服务器, 请为每个边缘服务器重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e53f1-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

