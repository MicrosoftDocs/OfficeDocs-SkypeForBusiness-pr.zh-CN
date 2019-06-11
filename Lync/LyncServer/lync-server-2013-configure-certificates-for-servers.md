---
title: Lync Server 2013：为服务器配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="8d7e9-102">在 Lync Server 2013 中为服务器配置证书</span><span class="sxs-lookup"><span data-stu-id="8d7e9-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d7e9-103">_**主题上次修改时间:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="8d7e9-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="8d7e9-104">若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录, 或者委派正确的权限。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="8d7e9-105">有关委派权限的详细信息, 请参阅[Lync Server 2013 中的委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="8d7e9-106">根据您的组织和申请证书的要求, 您可能需要其他组成员身份。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="8d7e9-107">咨询管理公钥基础结构 (PKI) 证书颁发机构 (CA) 的组。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d7e9-108">Lync Server 2013 包括对 SHA-1 套件的支持 (SHA-2 对来自运行 Windows 7、Windows Server 512 R2、Windows Server 2008、windows Vista 的客户端的连接) 的摘要哈希和签名算法使用摘要式哈希和签名算法的摘要 384 256 224 长度Windows XP 操作系统, 除了 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="8d7e9-109">要支持使用 SHA-2 套件进行外部访问，外部证书必须由公共 CA 颁发，公共 CA 也可颁发具有相同位长度摘要的证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="8d7e9-110">选择哪种哈希摘要和签名算法取决于将使用证书的客户端和服务器，客户端和服务器将与其通信的其他计算机和设备也必须知道如何使用证书中所用的算法。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="8d7e9-111">有关操作系统和某些客户端应用程序支持哪些摘要长度的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="8d7e9-112">每个标准版服务器或前端服务器最多需要四个证书: oAuthTokenIssuer 证书、默认证书、web 内部证书和 web 外部证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="8d7e9-113">但是, 可以使用相应的主题可选名称条目以及 oAuthTokenIssuer 证书请求和分配单个默认证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="8d7e9-114">有关证书要求的详细信息, 请参阅[Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="8d7e9-115">有关请求、分配和安装 oAuthTokenIssuer 证书的详细信息, 请参阅[在 Lync server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="8d7e9-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="8d7e9-116">使用以下过程请求、分配和安装标准版服务器或前端服务器证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="8d7e9-117">对每个前端服务器重复该过程。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8d7e9-118">以下过程介绍了如何从由组织部署的内部企业 PKI 以及通过脱机请求处理来配置证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="8d7e9-119">有关从公共 CA 获取证书的信息, 请参阅规划文档中<A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 内部服务器的证书要求</A>。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="8d7e9-120">此外, 此过程还介绍了如何在设置前端服务器的过程中请求、分配和安装证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="8d7e9-121">如果你提前申请证书, 如本部署文档的<A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 的 "提前申请证书 (可选)</A> " 部分中所述, 或者你不使用组织中部署的内部企业 PKI 获取证书, 则必须根据需要修改此过程。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="8d7e9-122">配置前端服务器的证书</span><span class="sxs-lookup"><span data-stu-id="8d7e9-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="8d7e9-123">在 Lync Server 部署向导中, 单击**步骤 3: "请求, 安装或分配证书"** 旁边的 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="8d7e9-124">在“**证书向导**”页上，单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="8d7e9-125">在 "**证书请求**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="8d7e9-p107">在“**延迟的请求或即时请求**”页上，可通过单击“**下一步**”接受默认的“**立即将请求发送给联机证书颁发机构**”选项。如果选择此选项，具有自动联机注册的内部 CA 必须可用。如果选择了延迟请求的选项，系统将提示您输入用于保存证书请求文件的名称和位置。证书请求必须由组织内部的 CA 或公共 CA 提出和处理。然后您需要导入证书响应并将其分配给适当的证书角色。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="8d7e9-131">在 "**选择证书颁发机构 (CA)** " 页面上, 选择 "**从你的环境中检测到的列表中选择一个 CA** " 选项, 然后从列表中选择一个已知 (通过注册 Active DIRECTORY 域服务) ca。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="8d7e9-132">或者，选择“**指定其他证书颁发机构**”选项，在框中输入其他 CA 的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="8d7e9-133">在“**证书颁发机构帐户**”页上，将提示您提供凭据，以在 CA 中请求证书和处理证书请求。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="8d7e9-134">您应该已经确定提前请求证书是否需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="8d7e9-135">您的 CA 管理员将拥有所需的信息, 并且可能需要在此步骤中为您提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="8d7e9-136">如果需要提供备用凭据，请选中相应的复选框，在文本框中输入用户名和密码，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="8d7e9-137">在“**指定替代证书模板**”页上，要使用默认的 Web 服务器模板，请单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d7e9-p110">如果组织已经创建了模板，以用作默认 Web 服务器 CA 模板的备用模板，请选中相应的复选框，然后输入备用模板的名称。您将需要 CA 管理员定义的模板名称。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="8d7e9-140">在 "**名称和安全设置**" 页面上, 指定允许你标识证书和用途的**友好名称**。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="8d7e9-141">如果将此处留空，则系统会自动生成一个名称。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="8d7e9-142">设置密钥的“**位长度**”，或接受默认值 2048 位。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="8d7e9-143">如果您确定需要将证书和私钥移动或复制到其他系统中，请选择“**将证书的私钥标记为可导出**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d7e9-144">Lync Server 2013 对可导出私钥的要求很少。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="8d7e9-145">其中一个可导出的位置是池中的边缘服务器，在这里媒体中继身份验证服务使用证书副本，而不是对池中的每个实例都分别使用单个证书。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="8d7e9-146">在“**组织信息**”页上，可选择提供组织信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="8d7e9-147">在“**地理信息**”页上，可选择提供地理信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="8d7e9-148">在“**使用者名称/使用者替代名称**”页上，检查将添加的使用者替代名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="8d7e9-149">在“**SIP 域设置**”页上，选择“**SIP 域**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="8d7e9-150">在“**配置其他使用者替代名称**”页上，添加其他任何需要的使用者替代名称，包括将来其他 SIP 域可能需要的使用者替代名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="8d7e9-p113">在“**证书请求摘要**”页上，检查摘要中的信息。如果信息正确，请单击“**下一步**”。如果需要更正或修改设置，请单击“**上一步**”返回相应的页面进行更正或修改。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="8d7e9-154">在“**正在执行命令**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="8d7e9-155">On the **Online Certificate Request Status** page, review the information returned.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="8d7e9-156">You should note that the certificate was issued and installed into the local certificate store.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="8d7e9-157">如果报告为已颁发并已安装, 但无效, 请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="8d7e9-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="8d7e9-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="8d7e9-160">默认情况下, 选中 "**将证书分配给 Lync Server 证书使用**情况" 复选框。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="8d7e9-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="8d7e9-162">如果已清除 "**将证书分配给上一页的 Lync Server 证书使用**情况" 复选框, 则会显示 "**证书分配**" 页面。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="8d7e9-163">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-163">Click **Next**.</span></span>

18. <span data-ttu-id="8d7e9-p116">在“**证书存储**”页上，选择已请求的证书。如果要查看证书，请单击“**查看证书详细信息**”，然后单击“**下一步**”继续。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d7e9-166">如果 "<STRONG>联机证书请求状态</STRONG>" 页面报告了证书的问题 (例如证书无效), 查看实际证书可帮助解决问题。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="8d7e9-167">可能导致证书无效的两个具体问题为：先前提到的受信任根 CA 证书缺失，与证书相关联的私钥缺失。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="8d7e9-168">有关如何解决这两个问题的信息，请参阅 CA 文档。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="8d7e9-169">在“**证书分配摘要**”页上，检查显示的信息以确保此证书是应分配的证书，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="8d7e9-p118">在“**正在执行命令**”页上，检查命令的输出。如果要检查分配过程或查看是否出现错误或警告，请单击“**查看日志**”。检查完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="8d7e9-173">在 "**证书向导**" 页面上, 验证证书的**状态**是否为 "已分配", 然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8d7e9-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d7e9-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d7e9-174">See Also</span></span>


[<span data-ttu-id="8d7e9-175">Lync Server 2013 的证书基础结构要求</span><span class="sxs-lookup"><span data-stu-id="8d7e9-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

