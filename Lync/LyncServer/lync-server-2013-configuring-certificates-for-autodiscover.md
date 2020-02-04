---
title: Lync Server 2013：配置自动发现的证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="bd422-102">在 Lync Server 2013 中配置自动发现的证书</span><span class="sxs-lookup"><span data-stu-id="bd422-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd422-103">_**主题上次修改时间：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="bd422-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="bd422-104">Director 池、前端池和反向代理的证书需要其他使用者备用名称条目才能支持与 Lync 客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="bd422-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd422-105">你可以使用<STRONG>CsCertificate</STRONG> cmdlet 查看有关当前已分配证书的信息。</span><span class="sxs-lookup"><span data-stu-id="bd422-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="bd422-106">但是，默认视图将截断证书的属性，并且不显示 SubjectAlternativeNames 属性中的所有值。</span><span class="sxs-lookup"><span data-stu-id="bd422-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="bd422-107">你可以使用<STRONG>CsCertificate</STRONG> <STRONG>、CsCertificate 和</STRONG> <STRONG>CsCertificate</STRONG> cmdlet 查看某些信息以及申请和分配证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="bd422-108">但是，如果不确定当前证书上的主题备用名称（SAN）的属性，则不是最佳方法。</span><span class="sxs-lookup"><span data-stu-id="bd422-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="bd422-109">若要查看证书和所有属性成员，建议使用<EM>Microsoft 管理控制台（MMC）</EM>中的 "证书" 管理单元，或使用 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="bd422-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="bd422-110">在 Lync Server 部署向导中，可以使用证书向导查看证书属性。</span><span class="sxs-lookup"><span data-stu-id="bd422-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="bd422-111">以下过程详细介绍了如何使用 Lync Server 管理外壳和<EM>Microsoft 管理控制台（MMC）</EM>查看、请求和分配证书的过程。</span><span class="sxs-lookup"><span data-stu-id="bd422-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="bd422-112">若要使用 Lync Server 部署向导，请参阅此处的详细信息如果已部署可选控制器或控制器池，请执行以下操作：<A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中配置 Director 的证书</A>。</span><span class="sxs-lookup"><span data-stu-id="bd422-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="bd422-113">对于前端服务器或前端池，请参阅此处的详细信息：<A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中配置服务器的证书</A>。</span><span class="sxs-lookup"><span data-stu-id="bd422-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="bd422-114">此过程中的初始步骤是准备步骤，以指导你确定当前证书扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="bd422-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="bd422-115">默认情况下，证书将没有 lyncdiscover。&lt;sipdomain&gt;或 lyncdiscoverinternal。&lt;内部域名&gt;条目，除非您之前已安装移动服务或事先已准备好您的证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="bd422-116">此过程使用示例 SIP 域名 "contoso.com" 和示例内部域名 "contoso.net"。</span><span class="sxs-lookup"><span data-stu-id="bd422-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="bd422-117">Lync Server 2013 和 Lync Server 2010 的默认证书配置是将单个证书（名为 "Default"）用作默认值（对于除 web 服务之外的所有其他用途），WebServicesExternal 和 WebServicesInternal。</span><span class="sxs-lookup"><span data-stu-id="bd422-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="bd422-118">可选配置是对每个用途使用单独的证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="bd422-119">可通过使用 Lync Server Management Shell 和 Windows PowerShell cmdlet，或使用 Lync Server 部署向导中的证书向导来管理证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="bd422-120">使用 Lync Server 命令行管理程序使用新的主题替换名称更新证书</span><span class="sxs-lookup"><span data-stu-id="bd422-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="bd422-121">使用具有本地管理员权限和权限的帐户登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="bd422-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="bd422-122">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bd422-123">了解已分配给服务器的证书以及使用哪种类型的证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="bd422-124">在下一步中需要此信息来分配已更新的证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="bd422-125">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="bd422-126">查看上一步骤的输出，以查看是否为多个用途分配了一个证书，或者是否为每个使用分配了不同的证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="bd422-127">查看 "使用" 参数，了解如何使用证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="bd422-128">比较所显示的证书的指纹参数，以查看相同的证书是否有多个用途。</span><span class="sxs-lookup"><span data-stu-id="bd422-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="bd422-129">更新证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-129">Update the certificate.</span></span> <span data-ttu-id="bd422-130">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="bd422-131">例如，如果**CsCertificate** cmdlet 显示了使用默认值的证书，另一个使用了 WebServicesInternal 的证书，而另一个使用 WebServicesExternal，并且它们都具有相同的指纹值，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="bd422-132">**重要提示：**</span><span class="sxs-lookup"><span data-stu-id="bd422-132">**Important:**</span></span>
    
    <span data-ttu-id="bd422-133">如果为每个使用分配了单独的证书（指纹值对于每个证书而言不同），请务必不要使用多个类型运行**CsCertificate** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd422-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="bd422-134">在这种情况下，为每次使用单独运行**CsCertificate** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd422-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="bd422-135">例如：</span><span class="sxs-lookup"><span data-stu-id="bd422-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="bd422-136">若要查看证书，请单击 "**开始**"，单击 "**运行 ...**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="bd422-137">键入 MMC 以打开 Microsoft 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bd422-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="bd422-138">从 MMC 菜单中，选择 "**文件**"，选择 "**添加/删除管理单元 ...**"，然后选择 "证书"。</span><span class="sxs-lookup"><span data-stu-id="bd422-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="bd422-139">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd422-139">Click **Add**.</span></span> <span data-ttu-id="bd422-140">出现提示时，选择 "**计算机帐户**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="bd422-141">如果证书位于此计算机上，请选择 "**本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="bd422-142">如果证书位于另一台计算机上，请选择 "**另一**台计算机"，键入计算机的完全限定的域名，或单击 **"在输入要选择的对象名称"** 中的 "**浏览**"，键入计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="bd422-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="bd422-143">单击 "**检查姓名**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-143">Click **Check Names**.</span></span> <span data-ttu-id="bd422-144">当解析计算机的名称时，它将带有下划线。</span><span class="sxs-lookup"><span data-stu-id="bd422-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="bd422-145">单击 **"确定**"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="bd422-146">单击 **"确定"** 提交选定内容，然后关闭 "**添加或删除管理单元**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="bd422-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd422-147">如果该证书未显示在控制台中，请确保您没有选中 "用户或服务"。</span><span class="sxs-lookup"><span data-stu-id="bd422-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="bd422-148">您必须选择 "计算机"，否则您将无法找到 probper 证书。</span><span class="sxs-lookup"><span data-stu-id="bd422-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="bd422-149">若要查看证书的属性，请展开 "**证书**"，展开 "**个人**"，然后选择 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="bd422-150">选择要查看的证书，右键单击该证书，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="bd422-151">在 "**证书**" 视图中，选择 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="bd422-152">在此处，你可以通过选择 "**主题**"，然后显示 "分配的主题名称和关联的属性" 来选择证书主题名称。</span><span class="sxs-lookup"><span data-stu-id="bd422-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="bd422-153">若要查看分配的主题备用名称，请选择 "**主题备用名称**"。</span><span class="sxs-lookup"><span data-stu-id="bd422-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="bd422-154">显示所有指定的主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="bd422-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="bd422-155">默认情况下，在属性中找到的 "使用者替换名称" 是 " **DNS 名称**" 类型。</span><span class="sxs-lookup"><span data-stu-id="bd422-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="bd422-156">你应该会看到以下成员（所有这些成员都应是在 DNS 主机中表示的完全限定的域名（A 或 IPv6 AAAA）记录：</span><span class="sxs-lookup"><span data-stu-id="bd422-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="bd422-157">此池的池名称，如果这不是池，则为单个服务器名称</span><span class="sxs-lookup"><span data-stu-id="bd422-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="bd422-158">证书分配到的服务器名称</span><span class="sxs-lookup"><span data-stu-id="bd422-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="bd422-159">简单的 URL 记录，通常满足和拨入</span><span class="sxs-lookup"><span data-stu-id="bd422-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="bd422-160">Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），基于在拓扑生成器和 ridden 的 web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="bd422-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="bd422-161">如果已分配，则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="bd422-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="bd422-162">最后一项是你最感兴趣的项-如果存在 lyncdiscover 和 lyncdiscoverinternal SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="bd422-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="bd422-163">获得此信息后，您可以关闭 "证书" 视图和 MMC。</span><span class="sxs-lookup"><span data-stu-id="bd422-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="bd422-164">如果自动发现服务，即 lyncdiscover。\>域名\>和 lyncdiscoverinternal。\<域名\> （基于外部或内部证书）缺少使用者备用名称，并且你使用默认、WebServicesInternal 和 WebServiceExternal 类型的单个默认证书，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bd422-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="bd422-165">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="bd422-166">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="bd422-167">而是必须使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="bd422-168">使用 DomainName 参数时，必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bd422-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="bd422-169">例如：</span><span class="sxs-lookup"><span data-stu-id="bd422-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="bd422-170">若要分配证书，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="bd422-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="bd422-171">其中 "指纹" 是为新颁发的证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="bd422-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="bd422-172">对于在默认、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现主题备用名称，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bd422-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="bd422-173">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="bd422-174">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="bd422-175">而是必须使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="bd422-176">使用 DomainName 参数时，必须为 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="bd422-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="bd422-177">例如：</span><span class="sxs-lookup"><span data-stu-id="bd422-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="bd422-178">对于缺少的外部自动发现主题备用名称，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bd422-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="bd422-179">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="bd422-180">而是必须使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="bd422-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="bd422-181">使用 DomainName 参数时，必须为 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="bd422-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="bd422-182">例如：</span><span class="sxs-lookup"><span data-stu-id="bd422-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="bd422-183">若要分配单个证书类型，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="bd422-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="bd422-184">其中 "指纹" 是为新颁发的单个证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="bd422-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

