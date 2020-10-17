---
title: Lync Server 2013：修改用于移动性的证书
description: Lync Server 2013：修改用于移动性的证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555848"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="1f858-103">在 Lync Server 2013 中修改证书的移动性</span><span class="sxs-lookup"><span data-stu-id="1f858-103">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f858-104">_**上次修改的主题：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="1f858-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="1f858-105">为了支持 Lync 环境与移动客户端之间的安全连接，必须使用其他一些使用者备用名称 (SAN) 条目来更新安全套接字层 (SSL) 的控制器池、前端池和反向代理的证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-105">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="1f858-106">如果您需要查看有关移动性的证书要求的更多详细信息，请参阅在 [Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)中的证书要求部分，但基本上您需要从证书颁发机构获取新证书和包含的其他 SAN 条目，然后使用本文的步骤添加这些证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-106">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="1f858-107">当然，在开始之前，通常最好知道证书已拥有的备选主题名称。</span><span class="sxs-lookup"><span data-stu-id="1f858-107">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="1f858-108">如果您不确定已配置的内容，可以通过多种方式来确定。虽然该选项的运行 **set-cscertificate** 和其他 PowerShell 命令可查看此信息 (，但在默认情况下我们会通过) 的数据将被截断，因此您可能无法看到所需的所有属性。</span><span class="sxs-lookup"><span data-stu-id="1f858-108">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="1f858-109">为了充分了解证书及其所有属性，可以转到 Microsoft 管理控制台 (MMC) 并加载 "证书" 管理单元， (我们还将在) 中执行此操作，也可以仅签入 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="1f858-109">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="1f858-110">如前所述，以下步骤将指导您使用 Lync Server 命令行管理程序和 MMC 更新证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-110">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="1f858-111">如果您想要改用 Lync Server 部署向导中的证书向导，则可以检查为 Director 或控制器池 [配置 Lync server 2013 中的 director 的证书](lync-server-2013-configure-certificates-for-the-director.md) ，如果您配置了一个 (可能没有) 。</span><span class="sxs-lookup"><span data-stu-id="1f858-111">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="1f858-112">对于前端服务器或前端池，您需要 [在 Lync Server 2013 中查看 "配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)"。</span><span class="sxs-lookup"><span data-stu-id="1f858-112">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="1f858-113">要记住的最后一件事是，您可能在 Lync Server 2013 环境中有一个默认证书，也可能有默认 (的单独证书，这是除 web 服务) 、WebServicesExternal 和 WebServicesInternal 的所有内容。</span><span class="sxs-lookup"><span data-stu-id="1f858-113">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="1f858-114">无论您是什么配置，这些步骤都应帮助您解决。</span><span class="sxs-lookup"><span data-stu-id="1f858-114">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="1f858-115">使用 Lync Server 命令行管理程序将证书更新为新的使用者可选名称</span><span class="sxs-lookup"><span data-stu-id="1f858-115">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="1f858-116">您需要使用具有本地管理员权限和权限的帐户登录到 Lync Server 2013 服务器。</span><span class="sxs-lookup"><span data-stu-id="1f858-116">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="1f858-117">此外，如果在步骤12和更高版本中运行 PowerShell **请求-set-cscertificate** ，该帐户需要拥有对指定证书颁发机构 (CA) 的权限。</span><span class="sxs-lookup"><span data-stu-id="1f858-117">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="1f858-118">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1f858-119">在分配更新的证书之前，需要找出已分配给服务器的证书以及使用的类型。</span><span class="sxs-lookup"><span data-stu-id="1f858-119">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="1f858-120">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-120">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="1f858-121">查看上一步的输出，以查看是否已为多个使用分配了单个证书，或者是否为每个使用分配了不同的证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-121">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="1f858-122">查看 Use 参数以了解如何使用证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-122">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="1f858-123">比较显示的证书的 Thumbprint 参数以了解同一个证书是否有多种用途。</span><span class="sxs-lookup"><span data-stu-id="1f858-123">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="1f858-124">关注指纹参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-124">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="1f858-125">更新证书。</span><span class="sxs-lookup"><span data-stu-id="1f858-125">Update the certificate.</span></span> <span data-ttu-id="1f858-126">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-126">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="1f858-127">例如，如果 **set-cscertificate** Cmdlet 显示使用 "默认" 的证书，另一个使用了 WebServicesInternal，另一个使用了 WebServicesExternal，而另一个使用的是相同的指纹值，则应在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-127">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="1f858-128">**重要说明：**</span><span class="sxs-lookup"><span data-stu-id="1f858-128">**Important:**</span></span>
    
    <span data-ttu-id="1f858-129">如果为每个使用分配了单独的证书 (因此您在上面检查的每个证书) 的指纹值是不同的， **set-cscertificate** cmdlet**不能**运行多个类型，这一点非常重要，如上面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1f858-129">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="1f858-130">在此情况下，请对每种使用情况单独运行 **Set-CsCertificate** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1f858-130">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="1f858-131">例如：</span><span class="sxs-lookup"><span data-stu-id="1f858-131">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="1f858-132">若要查看证书 (或证书) ，请单击 " **开始**"，然后单击 " **运行 ...**"。</span><span class="sxs-lookup"><span data-stu-id="1f858-132">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="1f858-133">键入 MMC 以打开 Microsoft 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1f858-133">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="1f858-134">从 MMC 菜单中，依次选择“文件”\*\*\*\*、“添加/删除管理单元...”\*\*\*\* 和“证书”。</span><span class="sxs-lookup"><span data-stu-id="1f858-134">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="1f858-135">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-135">Click **Add**.</span></span> <span data-ttu-id="1f858-136">出现提示时，请选择“计算机帐户”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-136">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="1f858-137">如果这是证书所在的服务器，请选择 " **本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="1f858-137">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="1f858-138">如果证书位于另一台计算机上，则应选择 **另一台计算机**，然后可以键入计算机的完全限定域名，或者单击 " **浏览** **" 以选择 "要选择的对象名称**"，然后键入计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="1f858-138">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="1f858-139">单击“检查名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-139">Click **Check Names**.</span></span> <span data-ttu-id="1f858-140">当计算机的名称解析时，它将带下划线。</span><span class="sxs-lookup"><span data-stu-id="1f858-140">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="1f858-141">单击“确定”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-141">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="1f858-142">单击“确定”\*\*\*\* 以提交选项并关闭“添加或删除管理单元”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="1f858-142">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="1f858-p113">若要查看证书的属性，请展开“证书”\*\*\*\*、“个人”\*\*\*\*，然后选择“证书”\*\*\*\*。选择要查看的证书，右键单击证书并选择“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="1f858-p114">在“证书”\*\*\*\* 视图中，选择“详细信息”\*\*\*\*。从此处，您可通过选择“使用者”\*\*\*\* 来选择证书的使用者名称，这将显示分配的使用者名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="1f858-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="1f858-147">若要查看分配的使用者替代名称，请选择“使用者替代名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f858-147">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="1f858-148">此处显示所有分配的主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="1f858-148">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="1f858-149">此处找到的主题备用名称默认为 " **DNS 名称** " 类型。</span><span class="sxs-lookup"><span data-stu-id="1f858-149">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="1f858-150">您应看到下列成员（所有成员应是 DNS 主机中显示的完全限定域名）（A；如果是 IPv6，则为 AAAA）记录：</span><span class="sxs-lookup"><span data-stu-id="1f858-150">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="1f858-151">此池的池名称，如果不是池，则为单个服务器名称</span><span class="sxs-lookup"><span data-stu-id="1f858-151">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="1f858-152">证书将分配到的服务器名称</span><span class="sxs-lookup"><span data-stu-id="1f858-152">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="1f858-153">简单 URL 记录，一般为 meet 和 dialin</span><span class="sxs-lookup"><span data-stu-id="1f858-153">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="1f858-154">Web 服务内部和 Web 服务外部名称 (例如，webpool01.contoso.net、webpool01.contoso.com) ，具体取决于在拓扑生成器和替代 Web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="1f858-154">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="1f858-155">如果已分配，则为 lyncdiscover.。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="1f858-155">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="1f858-156">和 lyncdiscoverinternal.。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="1f858-156">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="1f858-157">记录.</span><span class="sxs-lookup"><span data-stu-id="1f858-157">records.</span></span>
    
    <span data-ttu-id="1f858-158">最后一项是你最感兴趣的内容–如果有 lyncdiscover. 和 lyncdiscoverinternal. SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="1f858-158">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="1f858-159">如果您有多个要检查的证书，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="1f858-159">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="1f858-160">了解此信息后，您可关闭证书视图和 MMC。</span><span class="sxs-lookup"><span data-stu-id="1f858-160">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="1f858-161">如果缺少自动发现服务使用者替代名称，并且要对 Default、WebServicesInternal 和 WebServiceExternal 类型使用单独的默认证书，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1f858-161">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="1f858-162">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-162">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1f858-163">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-163">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1f858-164">相反，您需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-164">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1f858-165">使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1f858-165">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="1f858-166">例如：</span><span class="sxs-lookup"><span data-stu-id="1f858-166">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="1f858-167">若要分配证书，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="1f858-167">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="1f858-168">其中“Thumbprint”是新颁发的证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="1f858-168">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="1f858-169">对于在将单独的证书用于默认值、WebServicesInternal 和 WebServicesExternal 时缺少内部自动发现 SAN，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1f858-169">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="1f858-170">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-170">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1f858-171">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-171">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1f858-172">相反，您需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-172">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1f858-173">使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="1f858-173">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="1f858-174">例如：</span><span class="sxs-lookup"><span data-stu-id="1f858-174">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="1f858-175">对于缺少的外部自动发现服务使用者替代名称，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="1f858-175">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1f858-176">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-176">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1f858-177">相反，您需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="1f858-177">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1f858-178">使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="1f858-178">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="1f858-179">例如：</span><span class="sxs-lookup"><span data-stu-id="1f858-179">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="1f858-180">若要分配单独的证书类型，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="1f858-180">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="1f858-181">其中“Thumbprint”是新颁发的独立证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="1f858-181">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f858-182">应注意的是，仅当运行这些步骤的帐户具有适当权限的证书颁发机构的访问权限时，才应运行步骤12和13。</span><span class="sxs-lookup"><span data-stu-id="1f858-182">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="1f858-183">如果您无法使用获得这些权限的帐户登录，或者如果您使用的是证书的公用或远程证书颁发机构，则需要通过 Lync Server 部署向导请求它们，这在本文的顶部进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="1f858-183">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

