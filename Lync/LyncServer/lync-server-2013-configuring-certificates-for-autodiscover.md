---
title: Lync Server 2013：为自动发现配置证书
description: Lync Server 2013：配置用于自动发现的证书。
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
ms.openlocfilehash: 98ab9eca92685eef8bccc500dc4a91efa891dec6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568718"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="680ce-103">在 Lync Server 2013 中配置自动发现的证书</span><span class="sxs-lookup"><span data-stu-id="680ce-103">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="680ce-104">_**上次修改的主题：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="680ce-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="680ce-105">您的控制器池、前端池和反向代理的证书需要其他使用者备用名称条目以支持与 Lync 客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="680ce-105">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="680ce-106">您可使用 <STRONG>Get-CsCertificate</STRONG> cmdlet 查看有关当前分配的证书的信息。</span><span class="sxs-lookup"><span data-stu-id="680ce-106">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="680ce-107">但是，默认视图将截断证书的属性并且不会显示 SubjectAlternativeNames 属性的所有值。</span><span class="sxs-lookup"><span data-stu-id="680ce-107">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="680ce-108">您可使用 <STRONG>Get-CsCertificate</STRONG>、<STRONG>Request-</STRONG>CsCertificate 和 <STRONG>Set-CsCertificate</STRONG> cmdlet 查看部分信息和请求与分配证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-108">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="680ce-109">但是，如果您不确定当前证书上使用者替代名称 (SAN) 的属性，则这不是最佳使用方法。</span><span class="sxs-lookup"><span data-stu-id="680ce-109">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="680ce-110">若要查看证书和所有属性成员，建议使用 <EM>Microsoft 管理控制台 (MMC) </EM> 中的 "证书" 管理单元，或使用 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="680ce-110">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="680ce-111">在 Lync Server 部署向导中，可以使用证书向导查看证书属性。</span><span class="sxs-lookup"><span data-stu-id="680ce-111">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="680ce-112">以下过程详细介绍了如何使用 Lync Server 命令行管理程序和 <EM>Microsoft 管理控制台 (MMC) </EM> 查看、请求和分配证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-112">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="680ce-113">若要使用 Lync Server 部署向导，请参阅此处的详细信息如果已部署可选控制器或控制器池： <A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中为控制器配置证书</A>。</span><span class="sxs-lookup"><span data-stu-id="680ce-113">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="680ce-114">对于前端服务器或前端池，请参阅此处的详细信息： <A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中配置服务器的证书</A>。</span><span class="sxs-lookup"><span data-stu-id="680ce-114">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="680ce-115">此过程中的初始步骤为准备步骤，以便为您确定当前证书扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="680ce-115">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="680ce-116">默认情况下，证书将不具有 lyncdiscover.。 &lt;sipdomain &gt; 或 lyncdiscoverinternal.。 &lt;内部域名 &gt; 条目，除非您之前已安装移动服务或事先已准备好证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-116">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="680ce-117">此过程使用示例 SIP 域名“contoso.com”和示例内部域名“contoso.net”。</span><span class="sxs-lookup"><span data-stu-id="680ce-117">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="680ce-118">Lync Server 2013 和 Lync Server 2010 的默认证书配置是使用名为 "Default" 的单个证书 () ，除了 web 服务) 、WebServicesExternal 和 WebServicesInternal 之外，其他所有用途的用途都是默认 (。</span><span class="sxs-lookup"><span data-stu-id="680ce-118">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="680ce-119">可选配置是对每种用途使用单独的证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-119">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="680ce-120">可以使用 Lync Server 命令行管理程序和 Windows PowerShell cmdlet，或使用 Lync Server 部署向导中的证书向导来管理证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-120">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="680ce-121">使用 Lync Server 命令行管理程序将证书更新为新的使用者可选名称</span><span class="sxs-lookup"><span data-stu-id="680ce-121">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="680ce-122">使用具有本地管理员权限的帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="680ce-122">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="680ce-123">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="680ce-p104">查明已为服务器分配哪些证书并将这些证书用于哪些类型的使用情况。您在下一个步骤中需要使用此信息来分配更新后的证书。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="680ce-p105">查看上一步骤中的输出内容以了解是否为多种使用情况分配了一个证书，或是否为每种使用情况分配了不同的证书。查看 Use 参数以了解证书的用法。比较显示的证书的 Thumbprint 参数以了解同一个证书是否有多种用途。</span><span class="sxs-lookup"><span data-stu-id="680ce-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="680ce-p106">更新证书。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="680ce-132">例如，如果 **Get-CsCertificate** cmdlet 显示了一个用于默认使用情况的证书、一个用于 WebServicesInternal 的证书和一个用于 WebServicesExternal 的证书，并且这些证书都具有相同的 Thumbprint 值，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-132">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="680ce-133">**重要说明：**</span><span class="sxs-lookup"><span data-stu-id="680ce-133">**Important:**</span></span>
    
    <span data-ttu-id="680ce-134">如果为每种使用情况分配一个单独的证书（每个证书的 Thumbprint 值不同），则请不要对多种类型运行 **Set-CsCertificate** cmdlet，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="680ce-134">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="680ce-135">在此情况下，请对每种使用情况单独运行 **Set-CsCertificate** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="680ce-135">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="680ce-136">例如：</span><span class="sxs-lookup"><span data-stu-id="680ce-136">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="680ce-p108">若要查看证书，请单击“开始”\*\*\*\*，再单击“运行…”\*\*\*\*。键入 MMC 以打开 Microsoft 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="680ce-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="680ce-p109">从 MMC 菜单中，依次选择“文件”\*\*\*\*、“添加/删除管理单元...”\*\*\*\* 和“证书”。单击“添加”\*\*\*\*。出现提示时，请选择“计算机帐户”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="680ce-142">如果证书位于此计算机上，请选择 " **本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="680ce-142">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="680ce-143">如果证书位于其他计算机上，请选择“其他计算机”\*\*\*\*，键入计算机的完全限定域名或单击“输入要选择的对象名称”\*\*\*\* 中的“浏览”\*\*\*\*，键入计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="680ce-143">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="680ce-144">单击“检查名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-144">Click **Check Names**.</span></span> <span data-ttu-id="680ce-145">解析计算机的名称时，计算机名称将带下划线。</span><span class="sxs-lookup"><span data-stu-id="680ce-145">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="680ce-146">单击“确定”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-146">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="680ce-147">单击“确定”\*\*\*\* 以提交选项并关闭“添加或删除管理单元”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="680ce-147">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="680ce-148">如果证书未显示在控制台中，请确保未选择 "用户" 或 "服务"。</span><span class="sxs-lookup"><span data-stu-id="680ce-148">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="680ce-149">您必须选择 "计算机"，否则将无法找到 probper 证书。</span><span class="sxs-lookup"><span data-stu-id="680ce-149">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="680ce-p112">若要查看证书的属性，请展开“证书”\*\*\*\*、“个人”\*\*\*\*，然后选择“证书”\*\*\*\*。选择要查看的证书，右键单击证书并选择“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="680ce-p113">在“证书”\*\*\*\* 视图中，选择“详细信息”\*\*\*\*。从此处，您可通过选择“使用者”\*\*\*\* 来选择证书的使用者名称，这将显示分配的使用者名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="680ce-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="680ce-154">若要查看分配的使用者替代名称，请选择“使用者替代名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="680ce-154">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="680ce-155">这将显示分配的所有使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="680ce-155">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="680ce-156">默认情况下，这将是在类型“DNS 名称”\*\*\*\* 的属性中找到的使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="680ce-156">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="680ce-157">您应看到下列成员（所有成员应是 DNS 主机中显示的完全限定域名）（A；如果是 IPv6，则为 AAAA）记录：</span><span class="sxs-lookup"><span data-stu-id="680ce-157">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="680ce-158">此池的池名称；如果它不是一个池，则为单台服务器名称</span><span class="sxs-lookup"><span data-stu-id="680ce-158">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="680ce-159">证书将分配到的服务器名称</span><span class="sxs-lookup"><span data-stu-id="680ce-159">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="680ce-160">简单 URL 记录，一般为 meet 和 dialin</span><span class="sxs-lookup"><span data-stu-id="680ce-160">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="680ce-161">Web 服务内部和 Web 服务外部名称 (例如，webpool01.contoso.net、webpool01.contoso.com) ，具体取决于在拓扑生成器和替代 Web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="680ce-161">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="680ce-162">如果已分配，则为 lyncdiscover.。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="680ce-162">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="680ce-163">和 lyncdiscoverinternal.。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="680ce-163">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="680ce-164">记录.</span><span class="sxs-lookup"><span data-stu-id="680ce-164">records.</span></span>
    
    <span data-ttu-id="680ce-165">最后一项是您最关注的内容 – 是否存在 lyncdiscover 和 lyncdiscoverinternal SAN 项。</span><span class="sxs-lookup"><span data-stu-id="680ce-165">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="680ce-166">了解此信息后，您可关闭证书视图和 MMC。</span><span class="sxs-lookup"><span data-stu-id="680ce-166">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="680ce-167">如果自动发现服务（即 lyncdiscover.）。 \>域名 \> 和 lyncdiscoverinternal.。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="680ce-167">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="680ce-168"> (基于是否为外部或内部证书) 使用者备用名称缺失，并且您对默认的 WebServicesInternal 和 WebServiceExternal 类型使用了单个默认证书，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="680ce-168">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="680ce-169">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-169">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="680ce-170">如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="680ce-170">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="680ce-171">相反，您必须使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="680ce-171">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="680ce-172">使用 DomainName 参数时，必须为 lyncdiscoverinternal. 和 lyncdiscover. 记录定义 FQDN。</span><span class="sxs-lookup"><span data-stu-id="680ce-172">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="680ce-173">例如：</span><span class="sxs-lookup"><span data-stu-id="680ce-173">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="680ce-174">若要分配证书，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="680ce-174">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="680ce-175">其中“Thumbprint”是新颁发的证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="680ce-175">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="680ce-176">对于对 Default、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现使用者替代名称的情况，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="680ce-176">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="680ce-177">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-177">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="680ce-p118">如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。相反，您必须使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：</span><span class="sxs-lookup"><span data-stu-id="680ce-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="680ce-182">对于缺少的外部自动发现服务使用者替代名称，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="680ce-182">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="680ce-p119">如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。相反，您必须使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：</span><span class="sxs-lookup"><span data-stu-id="680ce-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="680ce-187">若要分配单独的证书类型，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="680ce-187">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="680ce-188">其中“Thumbprint”是新颁发的独立证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="680ce-188">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

