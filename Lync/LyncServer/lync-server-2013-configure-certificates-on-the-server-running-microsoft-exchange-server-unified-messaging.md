---
title: Lync Server 2013：在运行 Microsoft Exchange Server 统一消息的服务器上配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="99385-102">在运行 Microsoft Exchange Server 统一消息的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="99385-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99385-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="99385-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="99385-104">如果已部署 Exchange 统一消息（UM），如规划文档中的 "[在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 中所述，并且您希望向组织中的企业语音用户提供 exchange um 功能，则可以使用以下过程在运行 Exchange um 的服务器上配置证书。</span><span class="sxs-lookup"><span data-stu-id="99385-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99385-105">对于内部证书，运行 Lync Server 2013 的服务器和运行 Microsoft Exchange 的服务器都必须具有相互信任的受信任根证书颁发机构证书。</span><span class="sxs-lookup"><span data-stu-id="99385-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="99385-106">证书颁发机构（CA）可以是相同的，也可以是不同的证书颁发机构，前提是服务器在其受信任根证书颁发机构证书存储中注册了证书颁发机构的根证书。</span><span class="sxs-lookup"><span data-stu-id="99385-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="99385-107">必须使用服务器证书配置 Exchange 服务器才能连接到 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="99385-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="99385-108">为 Exchange Server 下载 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="99385-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="99385-109">为 Exchange Server 安装 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="99385-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="99385-110">确保该 CA 在 Exchange Server 的受信任的根 CA 列表中。</span><span class="sxs-lookup"><span data-stu-id="99385-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="99385-111">为 Exchange Server 创建证书请求并安装该证书。</span><span class="sxs-lookup"><span data-stu-id="99385-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="99385-112">为 Exchange Server 分配证书。</span><span class="sxs-lookup"><span data-stu-id="99385-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="99385-113">下载 CA 证书</span><span class="sxs-lookup"><span data-stu-id="99385-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="99385-114">在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，键入**发证 CA\>服务器\</Certsrv 的 http://名称**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="99385-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="99385-115">在 **“选择任务”** 下，单击 **“下载 CA 证书、证书链或 CRL”**。</span><span class="sxs-lookup"><span data-stu-id="99385-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="99385-116">在 "**下载 Ca 证书、证书链或 CRL**" 下，选择 "**编码方法为基本 64**"，然后单击 "**下载 CA 证书**"。</span><span class="sxs-lookup"><span data-stu-id="99385-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99385-117">您还可以在此步骤中指定可分辨编码规则（DER）编码。</span><span class="sxs-lookup"><span data-stu-id="99385-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="99385-118">如果选择 DER 编码，则本过程的下一步中和<STRONG>“安装 CA 证书”</STRONG>的步骤 10 中的文件类型为 .p7b，而非 .cer。</span><span class="sxs-lookup"><span data-stu-id="99385-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="99385-p103">在 **“文件下载”** 对话框中单击 **“保存”**，然后将文件保存到服务器上的硬盘中。（文件的扩展名将为 .cer 或 .p7b，具体取决于在上一步中选择的编码。）</span><span class="sxs-lookup"><span data-stu-id="99385-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="99385-121">安装 CA 证书</span><span class="sxs-lookup"><span data-stu-id="99385-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="99385-122">在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，在 "**打开**" 框中键入**MMC** ，然后单击 **"确定"**，以打开 Microsoft 管理控制台（MMC）。</span><span class="sxs-lookup"><span data-stu-id="99385-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="99385-123">在 **“文件”** 菜单上，单击 **“添加/删除管理单元”**，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="99385-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="99385-124">在 **“添加独立管理单元”** 框中，单击 **“证书”**，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="99385-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="99385-125">在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="99385-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="99385-126">在 "**选择计算机**" 对话框中，确认已选中 "**本地计算机：（运行此控制台的计算机）** " 复选框，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="99385-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="99385-127">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="99385-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="99385-128">在控制台树中，展开 **“证书(本地计算机)”**，展开 **“受信任的根证书颁发机构”**，然后单击 **“证书”**。</span><span class="sxs-lookup"><span data-stu-id="99385-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="99385-129">右键单击 **“证书”**，单击 **“全部任务”**，然后单击 **“导入”**。</span><span class="sxs-lookup"><span data-stu-id="99385-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="99385-130">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="99385-130">Click **Next**.</span></span>

10. <span data-ttu-id="99385-p104">单击 **“浏览”** 找到文件，然后单击 **“下一步”**。（文件的扩展名将为 .cer 或 .p7b，具体取决于在 **“下载 CA 证书”** 的步骤 3 中选择的编码。）</span><span class="sxs-lookup"><span data-stu-id="99385-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="99385-133">单击 **“将所有证书放入下列存储区”**。</span><span class="sxs-lookup"><span data-stu-id="99385-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="99385-134">单击 **“浏览”**，然后选择 **“受信任的根证书颁发机构”**。</span><span class="sxs-lookup"><span data-stu-id="99385-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="99385-135">单击 **“下一步”** 以验证设置，然后单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="99385-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="99385-136">确认该 CA 在受信任的根 CA 列表中</span><span class="sxs-lookup"><span data-stu-id="99385-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="99385-137">在运行 Exchange UM 的服务器上，在 MMC 中展开 "**证书（本地计算机）**"，展开 "**受信任的根证书颁发机构**"，然后单击 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="99385-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="99385-138">在详细信息窗格中，验证您的 CA 是否位于受信任的 CA 列表中。</span><span class="sxs-lookup"><span data-stu-id="99385-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="99385-139">使用 Lync Server 配置 Exchange Server 2013 UM</span><span class="sxs-lookup"><span data-stu-id="99385-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="99385-140">有关详细信息，请参阅 Exchange Server 文档中的 "将 Exchange 2013 UM 与 Lync Server [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)集成"。</span><span class="sxs-lookup"><span data-stu-id="99385-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="99385-141">创建证书请求并在 Exchange Server 2007 (SP1) 中安装证书</span><span class="sxs-lookup"><span data-stu-id="99385-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="99385-142">在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，键入发证 CA 服务器**\>/certsrv**的**http://\<** 名称，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="99385-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="99385-143">在 **“选择任务”** 下，单击 **“请求证书”**。</span><span class="sxs-lookup"><span data-stu-id="99385-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="99385-144">在 **“请求证书”** 下，单击 **“高级证书申请”**。</span><span class="sxs-lookup"><span data-stu-id="99385-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="99385-145">在 **“高级证书申请”** 下，单击 **“创建并向此 CA 提交一个请求”**。</span><span class="sxs-lookup"><span data-stu-id="99385-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="99385-146">在 **“高级证书申请”** 下，选择 **“Web 服务器”** 或为服务器身份验证配置的其他服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="99385-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="99385-147">在 "**标识脱机模板的信息**" 下的 "**名称**" 框中，键入 Exchange 服务器的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="99385-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99385-148">必须输入 Exchange Server 的 FQDN 才能进行通信。</span><span class="sxs-lookup"><span data-stu-id="99385-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="99385-149">在 **“密钥选项”** 下单击 **“将证书保存在本地计算机证书存储中”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="99385-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="99385-150">单击网页底部的 **“提交”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="99385-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="99385-151">此时将打开一个要求确认的对话框，从中单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="99385-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="99385-152">在“证书已颁发”页上的 **“证书已颁发”** 下单击 **“安装此证书”**。</span><span class="sxs-lookup"><span data-stu-id="99385-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="99385-153">此时将打开一个要求确认的对话框，从中单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="99385-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="99385-154">确认显示 "您的新证书已成功安装" 消息。</span><span class="sxs-lookup"><span data-stu-id="99385-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="99385-155">在 Exchange Server 2010 上创建证书</span><span class="sxs-lookup"><span data-stu-id="99385-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="99385-156">使用适当的用户权限登录到运行 Exchange UM 的服务器。</span><span class="sxs-lookup"><span data-stu-id="99385-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="99385-157">有关详细信息，请参阅中的 "客户[https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)端访问权限"。</span><span class="sxs-lookup"><span data-stu-id="99385-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="99385-158">请参阅以下过程来创建证书：</span><span class="sxs-lookup"><span data-stu-id="99385-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="99385-159">"在处创建新的 Exchange 证书"[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="99385-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="99385-160">"导入 Exchange 证书"[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="99385-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99385-161">对于证书<STRONG>主题名称</STRONG>，必须输入 Exchange SERVER 的 FQDN，才能使通信正常工作。</span><span class="sxs-lookup"><span data-stu-id="99385-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="99385-162">在 Exchange Server 2007 （SP1）上分配证书</span><span class="sxs-lookup"><span data-stu-id="99385-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="99385-163">在运行 Exchange UM 的服务器上，打开 "MMC"。</span><span class="sxs-lookup"><span data-stu-id="99385-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="99385-164">在控制台树中，展开 "**个人**"，然后单击 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="99385-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="99385-165">在 "详细信息" 窗格中，验证是否显示 "个人证书"。</span><span class="sxs-lookup"><span data-stu-id="99385-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="99385-166">双击该证书以阅读其详细信息，并验证该证书是否有效。</span><span class="sxs-lookup"><span data-stu-id="99385-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99385-167">可能需要几分钟的时间才能将证书显示为有效。</span><span class="sxs-lookup"><span data-stu-id="99385-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="99385-168">重新启动 Microsoft Exchange 统一消息服务。</span><span class="sxs-lookup"><span data-stu-id="99385-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99385-169">运行 Exchange Server 2007 SP1 统一消息的服务器将自动检索正确的证书。</span><span class="sxs-lookup"><span data-stu-id="99385-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="99385-170">打开事件查看器并查找事件 ID 1112，它指定运行 Exchange Server 2007 SP1 统一消息的服务器已检索的证书。</span><span class="sxs-lookup"><span data-stu-id="99385-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="99385-171">在 Exchange Server 2010 上分配证书</span><span class="sxs-lookup"><span data-stu-id="99385-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="99385-172">使用适当的用户权限登录到运行 Exchange UM 的服务器。</span><span class="sxs-lookup"><span data-stu-id="99385-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="99385-173">有关详细信息，请参阅中的 "客户[https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)端访问权限"。</span><span class="sxs-lookup"><span data-stu-id="99385-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="99385-174">有关分配证书的过程，请参阅处[https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)的 "将服务分配给证书"。</span><span class="sxs-lookup"><span data-stu-id="99385-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

