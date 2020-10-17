---
title: Lync Server 2013：为内部边缘接口设置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f8c5c41eba828cb6514ba6963167d708ed203d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509889"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="b14e1-102">在 Lync Server 2013 中为内部边缘接口设置证书</span><span class="sxs-lookup"><span data-stu-id="b14e1-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b14e1-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b14e1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b14e1-104">在运行证书向导时，请确保您使用作为组（已为其分配您将使用的证书模板类型的适当权限）的成员的帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="b14e1-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="b14e1-105">默认情况下，Lync Server 2013 证书请求将使用 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="b14e1-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="b14e1-106">如果您使用作为 RTCUniversalServerAdmins 组的成员的帐户来通过此模板请求证书，请确保已为该组分配使用此模板所需的注册权限。</span><span class="sxs-lookup"><span data-stu-id="b14e1-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="b14e1-p102">每台边缘服务器的内部接口都需要一个证书。内部接口的证书可以由内部企业证书颁发机构 (CA) 或公共 CA 颁发。如果组织已部署内部 CA，则通过使用内部 CA 为内部接口颁发证书可以节省使用公用证书的开支。可以使用内部 Windows Server 2008 CA 或 Windows Server 2008 R2 CA 创建这些证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="b14e1-111">有关此证书和其他证书要求的详细信息，请参阅 [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b14e1-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="b14e1-112">要设置某个站点的内部边缘接口上的证书，请使用本节中的过程执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b14e1-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="b14e1-113">将内部接口的 CA 证书链下载到每台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b14e1-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="b14e1-114">在每台边缘服务器上为内部接口导入 CA 证书链。</span><span class="sxs-lookup"><span data-stu-id="b14e1-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="b14e1-115">在一台边缘服务器（称为第一台边缘服务器）上为内部接口创建证书请求。</span><span class="sxs-lookup"><span data-stu-id="b14e1-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="b14e1-116">在第一台边缘服务器上为内部接口导入证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="b14e1-117">在此站点（或部署在此负载平衡器之后）的其他边缘服务器上导入该证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="b14e1-118">为每台边缘服务器的内部接口分配证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="b14e1-119">如果多个站点都有边缘服务器（即多站点边缘拓扑），或不同组的边缘服务器部署在不同的负载平衡器之后，则需要按照上述步骤对每个有边缘服务器的站点以及每组部署在不同负载平衡器之后的边缘服务器进行操作。</span><span class="sxs-lookup"><span data-stu-id="b14e1-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b14e1-120">本节中的过程步骤基于以下各项：使用 Windows Server &nbsp; 2008 ca、Windows server &nbsp; 2008 &nbsp; R2 Ca、WINDOWS server 2012 Ca 或 Windows SERVER 2012 R2 ca 为每个边缘服务器创建证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="b14e1-121">有关任何其他 CA 的分步指南，请参考该 CA 的文档。</span><span class="sxs-lookup"><span data-stu-id="b14e1-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="b14e1-122">默认情况下，所有通过身份验证的用户都具有请求证书的适当用户权限。</span><span class="sxs-lookup"><span data-stu-id="b14e1-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="b14e1-p104">本节中的过程是以在部署边缘服务器的过程中在边缘服务器上创建证书请求为前提的。可以使用前端服务器创建证书请求。可以在开始部署边缘服务器之前执行此操作，以在规划和部署过程早期完成证书请求。为此，必须确保请求的证书是使用可导出的私钥定义的。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="b14e1-p105">本节中的过程介绍使用 .cer 和 .p7b 文件作为证书。如果使用其他类型的文件，请根据需要修改这些过程。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="b14e1-129">使用 certsrv 网站为内部接口下载 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="b14e1-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="b14e1-130">登录到内部网络中的 Lync Server 2013 服务器 (即，不是边缘服务器) 为 **Administrators** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b14e1-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="b14e1-131">在命令提示符下运行以下命令，方法是单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*，然后键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b14e1-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="b14e1-132">例如：</span><span class="sxs-lookup"><span data-stu-id="b14e1-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b14e1-133">如果您使用的是 Windows Server 2008 或 Windows Server 2008 R2 企业 CA，则必须使用 https，而非 http。</span><span class="sxs-lookup"><span data-stu-id="b14e1-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="b14e1-134">在发证 CA 的 certsrv 网页上，在“选择任务”\*\*\*\* 下，单击“下载 CA 证书、证书链或 CRL”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="b14e1-135">在“下载 CA 证书、证书链或 CRL”\*\*\*\* 下，单击“下载 CA 证书链”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="b14e1-136">在“文件下载”\*\*\*\* 对话框中，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="b14e1-137">将 .p7b 文件保存到服务器的硬盘上，然后将其复制到每台边缘服务器的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b14e1-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b14e1-p106">.p7b 文件包含证书路径中的所有证书。若要查看证书路径，请打开服务器证书，然后单击证书路径。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="b14e1-140">使用 MMC 为内部接口下载 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="b14e1-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="b14e1-141">您可以使用 Microsoft 管理控制台 (MMC) 从任何已加入域的计算机导出 CA 根证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="b14e1-142">单击“开始”\*\*\*\*，单击“运行”\*\*\*\*，然后键入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="b14e1-143">在 MMC 控制台中，单击“文件”\*\*\*\*，再单击“添加/删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="b14e1-p108">从“添加或删除管理单元”\*\*\*\* 对话框列表中，选择“证书”\*\*\*\*，然后单击“添加”\*\*\*\*。系统提示时，选择“计算机帐户”\*\*\*\*。在“选择计算机”\*\*\*\* 对话框中，选择“本地计算机”\*\*\*\*。单击“完成”\*\*\*\*。单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="b14e1-p109">展开“证书(本地计算机)”\*\*\*\*。展开“受信任的根证书颁发机构”\*\*\*\*，选择“证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="b14e1-p110">单击由 CA 颁发的根证书。右键单击该证书，选择“所有任务”\*\*\*\*，选择“导出”\*\*\*\*。将打开“证书导出向导”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="b14e1-154">在“证书导出向导”\*\*\*\* 中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="b14e1-155">打开“导出文件格式”\*\*\*\* 对话框，选择要导出到的格式。</span><span class="sxs-lookup"><span data-stu-id="b14e1-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="b14e1-156">建议将 \*\*加密邮件语法标准– PKCS \# 7 证书 (。P7B) \*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="b14e1-157">如果选择 " \*\*加密邮件语法标准– PKCS \# 7 证书 ("。P7B) \*\*，选择 " **如果可能，则包含证书路径中的所有证书** " 复选框以导出证书链，包括根 ca 证书和任何中间 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="b14e1-158">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-158">Click **Next**.</span></span>

8.  <span data-ttu-id="b14e1-p112">在“要导出的文件”\*\*\*\* 对话框的文件名条目中，为导出的证书键入路径和文件名（默认扩展名为 .p7b）。或者，也可以单击“浏览”\*\*\*\*，找到放置导出的证书的目录并为导出的证书提供名称。单击“保存”\*\*\*\*。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="b14e1-p113">查看操作摘要，然后单击“完成”\*\*\*\* 以完成证书的导出。单击“确定”\*\*\*\* 确认导出成功。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="b14e1-165">为内部接口导入 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="b14e1-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="b14e1-166">在每台边缘服务器上打开 Microsoft 管理控制台 (MMC)，方法是依次单击“开始”\*\*\*\*、“运行”\*\*\*\*，在“打开”\*\*\*\* 框中键入 **mmc**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="b14e1-167">在“文件”\*\*\*\* 菜单上，单击“添加/删除管理单元”\*\*\*\*，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="b14e1-168">在 **“添加独立管理单元”** 框中，单击 **“证书”**，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="b14e1-169">在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="b14e1-170">在 **“选择计算机”** 对话框中，确保选中 **“本地计算机: (运行此控制台的计算机)”** 复选框，然后单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="b14e1-171">单击“关闭”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="b14e1-172">在控制台树中，展开“证书(本地计算机)”\*\*\*\*，右键单击“受信任的根证书颁发机构”\*\*\*\*，指向“所有任务”\*\*\*\*，然后单击“导入”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="b14e1-173">在向导的“要导入的文件”\*\*\*\* 中，指定证书的文件名（即在前面过程中为内部接口下载 CA 证书链时指定的名称）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="b14e1-174">在每台边缘服务器上重复此过程。</span><span class="sxs-lookup"><span data-stu-id="b14e1-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="b14e1-175">为内部接口创建证书申请</span><span class="sxs-lookup"><span data-stu-id="b14e1-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="b14e1-176">在其中一台边缘服务器上启动部署向导，然后单击“步骤 3: 请求、安装或分配证书”\*\*\*\* 旁边的“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b14e1-177">如果多台边缘服务器位于一个池中的同一个位置，则可以在任意一台边缘服务器上运行证书向导。</span><span class="sxs-lookup"><span data-stu-id="b14e1-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="b14e1-178">首次运行步骤 3 后，按钮会更改为“再次运行”<STRONG></STRONG>，且只有在请求、安装和分配全部所需证书后，才会显示指示任务成功完成的绿色复选标记。</span><span class="sxs-lookup"><span data-stu-id="b14e1-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="b14e1-179">在“可用的证书任务”\*\*\*\* 页上，单击“创建新的证书请求”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="b14e1-180">在“证书请求”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="b14e1-181">在“延迟的请求或即时请求”\*\*\*\* 页上，单击“现在准备请求，但稍后发送”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="b14e1-182">在 " **证书请求文件** " 页上，键入请求要保存到的完整路径和文件名 (例如， **c： \\ cert \_ internal \_ edge .cer**) 。</span><span class="sxs-lookup"><span data-stu-id="b14e1-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="b14e1-183">在“指定替代证书模板”\*\*\*\* 页上，要使用除默认 WebServer 模板之外的模板，请选中“使用选定证书颁发机构的备用证书模板”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b14e1-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="b14e1-184">在“名称和安全设置”\*\*\*\* 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b14e1-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="b14e1-185">在“友好名称”\*\*\*\* 中，键入证书的显示名称（例如，内部边缘）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="b14e1-186">在“位长度”\*\*\*\* 中，指定位长度（通常为默认值“2048”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b14e1-187">较高的位长度更为安全，但是会对速度产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="b14e1-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="b14e1-188">要使证书可以导出，请选中“将证书的私钥标记为可导出”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b14e1-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="b14e1-189">在“组织信息”\*\*\*\* 页上，键入组织名称和组织单位 (OU)（例如分部或部门）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="b14e1-190">在“地理信息”\*\*\*\* 页上，指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="b14e1-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="b14e1-191">在“使用者名称/使用者替代名称”\*\*\*\* 页上，将显示向导自动填充的信息。</span><span class="sxs-lookup"><span data-stu-id="b14e1-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="b14e1-192">在“配置其他使用者替代名称”\*\*\*\* 页上，指定所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="b14e1-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="b14e1-193">在“请求摘要”\*\*\*\* 页上，检查要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="b14e1-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="b14e1-194">完成命令后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b14e1-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="b14e1-195">要查看证书请求的日志，请单击“查看日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="b14e1-196">要完成证书请求，请单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="b14e1-197">在 **“证书请求文件”** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b14e1-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="b14e1-198">要查看生成的证书签名请求 (CSR) 文件，请单击 **“查看”**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="b14e1-199">要关闭向导，请单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="b14e1-200">将此文件提交给 CA（通过电子邮件或组织对企业 CA 支持的其他方法），并在收到回复文件时将新证书复制到此计算机，以使该证书可供导入。</span><span class="sxs-lookup"><span data-stu-id="b14e1-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="b14e1-201">为内部接口导入证书</span><span class="sxs-lookup"><span data-stu-id="b14e1-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="b14e1-202">以本地 Administrators 组成员的身份登录到在其上创建了证书请求的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b14e1-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="b14e1-203">在部署向导中，单击“步骤 3: 请求、安装或分配证书”\*\*\*\* 旁边的“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="b14e1-204">首次运行步骤 3 后，按钮会更改为“再次运行”\*\*\*\*，但只有在请求、安装和分配所有所需证书后，才会显示绿色复选标记（指示任务成功完成）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="b14e1-205">在“可用的证书任务”\*\*\*\* 页上，单击“从 .P7b、.pfx 或 .cer 文件导入证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="b14e1-206">在“导入证书”\*\*\*\* 页上，键入为此边缘服务器的内部接口请求并接收的证书的完整路径和文件名（或单击“浏览”\*\*\*\* 找到并选择该证书）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="b14e1-207">如果要为池中的其他成员导入证书，且证书包含私钥，请选中“证书文件包含证书的私钥”\*\*\*\* 复选框并指定密码。</span><span class="sxs-lookup"><span data-stu-id="b14e1-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="b14e1-208">为池中的边缘服务器导出包含私钥的证书</span><span class="sxs-lookup"><span data-stu-id="b14e1-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="b14e1-209">以 Administrators 组成员的身份登录到导入了证书的同一台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b14e1-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="b14e1-210">依次单击“开始”\*\*\*\* 和“运行”\*\*\*\*，再键入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="b14e1-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="b14e1-211">从 MMC 控制台中，单击“文件”\*\*\*\*，再单击“添加/删除管理单元”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="b14e1-212">从“添加或删除管理单元”页中，单击“证书”\*\*\*\*，再单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="b14e1-p114">在“证书管理单元”对话框中，选择“计算机帐户”\*\*\*\*。单击“下一步”\*\*\*\*。在“选择计算机”中，选择“本地计算机: (运行此控制台的计算机)”\*\*\*\*。单击“完成”\*\*\*\*。单击“确定”\*\*\*\* 完成对 MMC 控制台的配置。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="b14e1-p115">双击“证书(本地计算机)”\*\*\*\* 扩展证书存储。双击“个人”\*\*\*\*，然后双击“证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b14e1-p116">如果本地计算机的证书个人存储中没有证书，则表示未导入与证书关联的私钥。请检查请求和导入步骤。如果问题仍然存在，请联系您的证书颁发机构管理员或提供商。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="b14e1-p117">在本地计算机的证书个人存储中，右键单击要导出的证书。单击“所有任务”\*\*\*\*，再单击“导出”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="b14e1-p118">在证书导出向导中，单击“下一步”\*\*\*\*。选择“是，导出私钥”\*\*\*\*。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b14e1-p119">如果“是，导出私钥”<STRONG></STRONG>选择不可用，则没有将与该证书关联的私钥标记为导出。您将需要再次请求该证书，并确保该证书已标记为允许导出私钥，然后您才能继续导出操作。请与您的证书颁发机构管理员或提供商联系。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="b14e1-231">在 "导出文件格式" 对话框中，选择 " \*\*个人信息交换– PKCS \# 12 ("。PFX) \*\* 然后选择以下命令：</span><span class="sxs-lookup"><span data-stu-id="b14e1-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="b14e1-232">如果可能，则数据包括证书路径中的所有证书</span><span class="sxs-lookup"><span data-stu-id="b14e1-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="b14e1-233">导出所有扩展属性</span><span class="sxs-lookup"><span data-stu-id="b14e1-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="b14e1-p120">从边缘服务器导出证书时，请勿选择“如果导出成功，删除私钥”<STRONG></STRONG>。如果选择此选项，您将需要将证书和私钥导入到此边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="b14e1-236">单击“下一步”\*\*\*\* 继续。</span><span class="sxs-lookup"><span data-stu-id="b14e1-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="b14e1-p121">如果要分配密码以保护私钥，则键入私钥的密码。重新输入该密码以进行确认。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="b14e1-p122">为导出的证书键入路径和文件名，并使用文件扩展名 .pfx。该路径必须可由池中的所有其他边缘服务器访问，或者可通过可移动媒体（例如，USB 闪存驱动器）传输。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="b14e1-p123">查看“正在完成证书导出向导”对话框中的摘要。单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="b14e1-245">在成功导出对话框中单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="b14e1-246">按照 [为 Lync Server 2013 过程的外部边缘接口设置证书](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) 中所述的步骤，将导出的证书文件导入其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b14e1-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="b14e1-247">在边缘服务器上分配内部证书</span><span class="sxs-lookup"><span data-stu-id="b14e1-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="b14e1-248">对于每台边缘服务器，在部署向导中，单击“步骤 3: 请求、安装或分配证书”\*\*\*\* 旁边的“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="b14e1-249">在“可用的证书任务”\*\*\*\* 页上，单击“分配现有证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="b14e1-250">在“证书分配”\*\*\*\* 页上，选择列表中的“边缘内部”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="b14e1-251">在“证书存储”\*\*\*\* 页上，选择为内部边缘导入的证书（在前面过程中）。</span><span class="sxs-lookup"><span data-stu-id="b14e1-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="b14e1-252">在“证书分配摘要”\*\*\*\* 页上，检查设置，然后单击“下一步”\*\*\*\* 以分配证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="b14e1-253">在向导完成页上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b14e1-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="b14e1-254">使用此过程分配内部边缘证书后，在每台服务器上打开“证书”管理单元，依次展开“证书(本地计算机)”\*\*\*\*、“个人”\*\*\*\*，单击“证书”\*\*\*\*，然后确认详细信息窗格中是否列出了内部边缘证书。</span><span class="sxs-lookup"><span data-stu-id="b14e1-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="b14e1-255">如果部署中包含多台边缘服务器，请对每台边缘服务器重复此过程。</span><span class="sxs-lookup"><span data-stu-id="b14e1-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

