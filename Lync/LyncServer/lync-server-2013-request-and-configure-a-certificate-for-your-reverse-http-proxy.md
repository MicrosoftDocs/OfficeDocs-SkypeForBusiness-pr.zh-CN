---
title: 为 HTTP 反向代理请求和配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="c8787-102">在 Lync Server 2013 中为 HTTP 反向代理请求和配置证书</span><span class="sxs-lookup"><span data-stu-id="c8787-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8787-103">_**主题上次修改时间:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="c8787-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="c8787-104">对于向运行 Microsoft Lync 的内部服务器颁发服务器证书的 CA 基础结构, 您需要在运行 Microsoft Forefront 威胁管理网关2010或 IIS ARR 的服务器上安装根证书颁发机构 (CA) 证书服务器2013。</span><span class="sxs-lookup"><span data-stu-id="c8787-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="c8787-105">您还必须在反向代理服务器上安装公共 web 服务器证书。</span><span class="sxs-lookup"><span data-stu-id="c8787-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="c8787-106">此证书的主题备用名称应包含为用户启用远程访问的每个池的已发布外部完全限定的域名 (Fqdn), 以及将在其中使用的所有控制器或控制器池的外部 Fqdn。该 Edge 基础结构。</span><span class="sxs-lookup"><span data-stu-id="c8787-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="c8787-107">主题备用名称还必须包含会议简单 URL、拨入式简单 URL, 如果你要部署移动应用程序并计划使用自动发现, 请按下表所示使用 "外部自动发现服务" URL。</span><span class="sxs-lookup"><span data-stu-id="c8787-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c8787-108">值</span><span class="sxs-lookup"><span data-stu-id="c8787-108">Value</span></span></th>
<th><span data-ttu-id="c8787-109">示例</span><span class="sxs-lookup"><span data-stu-id="c8787-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8787-110">主题名称</span><span class="sxs-lookup"><span data-stu-id="c8787-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="c8787-111">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="c8787-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="c8787-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8787-113">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-114">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="c8787-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="c8787-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="c8787-116">主题名称还必须存在于 "主题备用名称" 中。</span><span class="sxs-lookup"><span data-stu-id="c8787-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8787-117">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-118">可选的主管 Web 服务 (如果已部署 Director)</span><span class="sxs-lookup"><span data-stu-id="c8787-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="c8787-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8787-120">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-121">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="c8787-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="c8787-122">所有会议简单 Url 必须位于主题备用名称中。</span><span class="sxs-lookup"><span data-stu-id="c8787-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="c8787-123">每个 SIP 域必须至少有一个活动会议简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c8787-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="c8787-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8787-125">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-126">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="c8787-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="c8787-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8787-128">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-129">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c8787-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="c8787-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8787-131">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="c8787-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="c8787-132">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="c8787-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c8787-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8787-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="c8787-134">如果你还在使用 Microsoft Exchange Server, 你还需要为 Exchange 自动发现和 web 服务 Url 配置反向代理规则。</span><span class="sxs-lookup"><span data-stu-id="c8787-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="c8787-135">如果内部部署包含多个标准版服务器或前端池, 则必须为每个外部 web 场 FQDN 配置 web 发布规则, 并且每个外部 web 场 FQDN 都需要一个证书和 web 侦听器, 或者必须获取证书其主题备用名称包含所有池使用的名称, 将其分配给 web 侦听器, 并在多个 web 发布规则之间共享。</span><span class="sxs-lookup"><span data-stu-id="c8787-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="c8787-136">创建证书请求</span><span class="sxs-lookup"><span data-stu-id="c8787-136">Create a Certificate Request</span></span>

<span data-ttu-id="c8787-137">在反向代理服务器上创建证书请求。</span><span class="sxs-lookup"><span data-stu-id="c8787-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="c8787-138">在另一台计算机上创建一个请求, 但必须使用私钥导出签名的证书, 并在从公共证书颁发机构收到该证书后将其导入到反向代理。</span><span class="sxs-lookup"><span data-stu-id="c8787-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c8787-139">证书申请或证书签名请求 (CSR) 是对受信任的公共证书颁发机构 (CA) 的请求, 用于验证和签名请求计算机的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="c8787-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="c8787-140">当生成证书时, 将创建一个公钥和一个私钥。</span><span class="sxs-lookup"><span data-stu-id="c8787-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="c8787-141">仅共享和签名公钥。</span><span class="sxs-lookup"><span data-stu-id="c8787-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="c8787-142">正如名称所示, 公钥可用于任何公共请求。</span><span class="sxs-lookup"><span data-stu-id="c8787-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="c8787-143">公钥供客户、服务器和其他申请者使用, 这些申请者需要安全地交换信息并验证计算机的标识。</span><span class="sxs-lookup"><span data-stu-id="c8787-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="c8787-144">私钥保持安全, 并且仅由创建密钥对的计算机使用, 用于解密使用其公钥加密的消息。</span><span class="sxs-lookup"><span data-stu-id="c8787-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="c8787-145">私钥可用于其他用途。</span><span class="sxs-lookup"><span data-stu-id="c8787-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="c8787-146">对于反向代理目的, 数据加密是主要用途。</span><span class="sxs-lookup"><span data-stu-id="c8787-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="c8787-147">Secondarily, 证书密钥级别的证书身份验证是另一种用途, 仅限于验证请求者拥有计算机的公钥, 或者你拥有公钥的计算机实际上是它所声明的计算机。</span><span class="sxs-lookup"><span data-stu-id="c8787-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="c8787-148">如果同时计划 Edge 服务器证书和反向代理证书, 应注意两种证书要求之间有很大的相似性。</span><span class="sxs-lookup"><span data-stu-id="c8787-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="c8787-149">配置和请求 Edge 服务器证书时, 请结合边缘服务器和反向代理主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="c8787-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="c8787-150">如果你导出证书和私钥并将导出的文件复制到反向代理, 然后导入证书/密钥对并在即将进行的过程中根据需要分配证书/密钥对, 则可以为反向代理使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="c8787-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="c8787-151">请参阅 lync server 2013 中的边缘服务器&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">计划</A>和反向代理<A href="lync-server-2013-certificate-summary-reverse-proxy.md">证书摘要-lync server 2013 中的反向</A>代理服务器证书的证书要求。</span><span class="sxs-lookup"><span data-stu-id="c8787-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="c8787-152">请确保使用可导出的私钥创建证书。</span><span class="sxs-lookup"><span data-stu-id="c8787-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="c8787-153">使用池边缘服务器创建证书和证书请求时需要具有可导出的私钥, 因此这是一种正常做法, 在 "Lync Server 部署向导" 中的 "证书向导" 中, 边缘服务器将允许你设置<STRONG>可导出的私钥</STRONG>标志。</span><span class="sxs-lookup"><span data-stu-id="c8787-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="c8787-154">从公共证书颁发机构收到证书申请后, 您将导出证书和私钥。</span><span class="sxs-lookup"><span data-stu-id="c8787-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="c8787-155">有关如何使用私钥创建和导出您的证书的详细信息, 请参阅主题为<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部边缘界面设置</A>证书中的 "导出证书并为该池的私钥" 部分。</span><span class="sxs-lookup"><span data-stu-id="c8787-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="c8787-156">证书的扩展名应为<STRONG>.pfx</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c8787-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="c8787-157">若要在将分配证书和私钥的计算机上生成证书签名请求, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c8787-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="c8787-158">**创建证书签名请求**</span><span class="sxs-lookup"><span data-stu-id="c8787-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="c8787-159">打开 Microsoft 管理控制台 (MMC) 并添加 "证书" 管理单元, 然后选择 "**计算机**", 然后展开 "**个人**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="c8787-160">有关如何在 Microsoft 管理控制台 (MMC) 中创建证书控制台的详细信息, 请参阅[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)。</span><span class="sxs-lookup"><span data-stu-id="c8787-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="c8787-161">右键单击 "**证书**", 单击 "**所有任务**", 单击 "**高级操作**", 然后单击 "**创建自定义请求**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="c8787-162">在 "**证书注册**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="c8787-163">在 "**选择证书注册策略**" 页面的 "**自定义请求**" 下, 选择 "**继续, 不包含注册策略**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="c8787-164">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-164">Click **Next**.</span></span>

5.  <span data-ttu-id="c8787-165">在 "**自定义请求**" 页面上, 对于**模板**选择 " **(无模板) 旧版密钥**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="c8787-166">除非您的证书提供商另有通知, 否则请保留**取消选中默认扩展名**和**PKCS \#10**上的**请求格式**选择。</span><span class="sxs-lookup"><span data-stu-id="c8787-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="c8787-167">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-167">Click **Next**.</span></span>

6.  <span data-ttu-id="c8787-168">在 "**证书信息**" 页面上, 单击 "**详细信息**", 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="c8787-169">在 "**证书属性**" 页面上 "**常规**" 选项卡上的 "**友好名称**" 字段中, 键入此证书的名称。</span><span class="sxs-lookup"><span data-stu-id="c8787-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="c8787-170">(可选) 在 "**说明**" 字段中键入说明。</span><span class="sxs-lookup"><span data-stu-id="c8787-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="c8787-171">管理员通常使用友好名称和描述来标识证书用途, 例如**Lync Server 的反向代理侦听器**。</span><span class="sxs-lookup"><span data-stu-id="c8787-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="c8787-172">选择 "**主题**" 选项卡。在**类型**的 "**主题名称**" 下, 选择 "主题名称" 类型的 "**公用名**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="c8787-173">对于 "**值**", 请键入将用于反向代理的主题名称, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="c8787-174">在本主题的表所提供的示例中, 主题名称是 webext.contoso.com, 并将键入到主题名称的值字段中。</span><span class="sxs-lookup"><span data-stu-id="c8787-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="c8787-175">在 "**其他名称**" 下的 "**主题**" 选项卡上, 从 "**类型**" 下拉列表中选择 " **DNS** "。</span><span class="sxs-lookup"><span data-stu-id="c8787-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="c8787-176">对于证书上所需的每个已定义的主题备用名称, 请键入完全限定的域名, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="c8787-177">例如, 在表中有三个主题可选名称、meet.contoso.com、dialin.contoso.com 和 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c8787-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="c8787-178">在 "**值**" 字段中, 键入 meet.contoso.com, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="c8787-179">对你需要定义的每个主题的备用名称重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="c8787-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="c8787-180">在 "**证书属性**" 页面上, 单击 "**扩展**" 选项卡。在此页面上, 你将定义**密钥用法**中的加密密钥用途以及**扩展密钥用法 (应用程序策略)** 中的扩展密钥用法。</span><span class="sxs-lookup"><span data-stu-id="c8787-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="c8787-181">单击 "**密钥用法**" 箭头以显示**可用选项**。</span><span class="sxs-lookup"><span data-stu-id="c8787-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="c8787-182">在 "可用选项" 下, 单击 "**数字签名**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="c8787-183">单击 "**密钥译码**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="c8787-184">如果未选中 "**使这些密钥用法关键**" 的复选框处于未选中状态, 请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="c8787-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="c8787-185">单击 "**扩展密钥用法" (应用程序策略)** 箭头以显示**可用选项**。</span><span class="sxs-lookup"><span data-stu-id="c8787-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="c8787-186">在 "可用选项" 下, 单击 "**服务器身份验证**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="c8787-187">单击 "**客户端身份验证**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="c8787-188">如果选中 "**使扩展密钥用法为关键"** 的复选框, 请取消选中复选框。</span><span class="sxs-lookup"><span data-stu-id="c8787-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="c8787-189">与 "密钥用法" 复选框相反 (必须选中), 必须确保未选中 "扩展密钥用法" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c8787-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="c8787-190">在 "**证书属性**" 页上, 单击 "**私钥**" 选项卡。单击 "**键选项**" 箭头。</span><span class="sxs-lookup"><span data-stu-id="c8787-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="c8787-191">对于**密钥大小**, 请从下拉列表中选择**2048** 。</span><span class="sxs-lookup"><span data-stu-id="c8787-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="c8787-192">如果你在此证书所针对的反向代理以外的计算机上生成此密钥对和 CSR, 请选择 "**使私钥可导出**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="c8787-194">安全说明:</span><span class="sxs-lookup"><span data-stu-id="c8787-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="c8787-195">当在服务器场中拥有多个反向代理时, 通常会建议选择 "<strong>使私钥可导出</strong>", 因为你将把证书和私钥复制到服务器场中的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="c8787-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="c8787-196">如果你确实允许可导出的私钥, 则必须对证书以及生成它的计算机额外小心。</span><span class="sxs-lookup"><span data-stu-id="c8787-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="c8787-197">私钥 (如受损) 将使证书不会被公开, 并且可能会将计算机或计算机暴露给外部访问和其他安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="c8787-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="c8787-198">在 "**专用密钥**" 选项卡上, 单击 "**键类型**" 箭头。</span><span class="sxs-lookup"><span data-stu-id="c8787-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="c8787-199">选择 " **Exchange** " 选项。</span><span class="sxs-lookup"><span data-stu-id="c8787-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="c8787-200">单击 **"确定"** 保存已设置的**证书属性**。</span><span class="sxs-lookup"><span data-stu-id="c8787-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="c8787-201">在 "**证书注册**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="c8787-202">在 "**你想要在何处保存脱机请求？** " 页面上, 系统将提示你\*\*\*\* 输入文件名和用于保存证书签名请求的**文件格式**。</span><span class="sxs-lookup"><span data-stu-id="c8787-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="c8787-203">在 " \*\*\*\* 文件名输入" 字段中, 键入请求的路径和文件名, 或单击 "**浏览**" 以选择文件的位置, 然后键入请求的文件名。</span><span class="sxs-lookup"><span data-stu-id="c8787-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="c8787-204">对于**文件格式**, 请单击 "**基本 64** " 或 "**二进制**"。</span><span class="sxs-lookup"><span data-stu-id="c8787-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="c8787-205">选择 "**基本 64** ", 除非您被您的证书的供应商指示。</span><span class="sxs-lookup"><span data-stu-id="c8787-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="c8787-206">找到您在上一步中保存的请求文件。</span><span class="sxs-lookup"><span data-stu-id="c8787-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="c8787-207">提交到公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="c8787-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c8787-208">Microsoft 已确定满足统一通信要求的公共 Ca。</span><span class="sxs-lookup"><span data-stu-id="c8787-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="c8787-209">以下知识库文章中将保留列表。</span><span class="sxs-lookup"><span data-stu-id="c8787-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

