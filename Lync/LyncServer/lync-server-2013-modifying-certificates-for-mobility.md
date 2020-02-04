---
title: Lync Server 2013：修改证书以实现移动功能
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="ea797-102">在 Lync Server 2013 中修改证书以实现移动功能</span><span class="sxs-lookup"><span data-stu-id="ea797-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea797-103">_**主题上次修改时间：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="ea797-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="ea797-104">为了支持 Lync 环境和移动客户端之间的安全连接，你的控制器池、前端池和反向代理的安全套接字层（SSL）证书需要使用其他一些主题备用名称进行更新（SAN）条目。</span><span class="sxs-lookup"><span data-stu-id="ea797-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="ea797-105">如果需要查看有关移动性的证书要求的详细信息，请参阅在[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)中的 "证书要求" 部分，但基本上需要从证书颁发机构获取新的证书，包含其他的 SAN 条目，然后使用本文的步骤添加这些证书。</span><span class="sxs-lookup"><span data-stu-id="ea797-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="ea797-106">当然，在开始之前，最好知道您的证书已有哪些主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="ea797-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="ea797-107">如果您不确定已配置的内容，可以通过多种方式来了解。虽然该选项的运行**CsCertificate**和其他 PowerShell 命令可查看此信息（我们将在下面遍历），但默认情况下将截断数据，因此你可能无法看到所需的所有属性。</span><span class="sxs-lookup"><span data-stu-id="ea797-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="ea797-108">为了更好地查看证书及其所有属性，您可以转到 Microsoft 管理控制台（MMC）并加载 "证书" 管理单元（我们还将在下面遍历），或者只需在 Lync Server 部署向导中进行检查。</span><span class="sxs-lookup"><span data-stu-id="ea797-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="ea797-109">如上所述，以下步骤将指导你使用 Lync Server Management Shell 和 MMC 更新证书。</span><span class="sxs-lookup"><span data-stu-id="ea797-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="ea797-110">如果您对使用 Lync Server 部署向导中的 "证书向导" 感兴趣，则可以在 "服务主管" 或 "控制器" 池的 " [Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) out" 中检查控制器的证书，前提是您已配置了一个（可能没有）。</span><span class="sxs-lookup"><span data-stu-id="ea797-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="ea797-111">对于前端服务器或前端池，你需要[在 Lync server 2013 中查看 "配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)"。</span><span class="sxs-lookup"><span data-stu-id="ea797-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="ea797-112">需要记住的最后一件事是，你可能在 Lync Server 2013 环境中拥有单个默认证书，或者你可能具有单独的默认证书（即除 web 服务之外的所有内容）、WebServicesExternal 和 WebServicesInternal。</span><span class="sxs-lookup"><span data-stu-id="ea797-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="ea797-113">无论您的配置如何，这些步骤都应帮助您解决问题。</span><span class="sxs-lookup"><span data-stu-id="ea797-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="ea797-114">使用 Lync Server 命令行管理程序使用新的主题替换名称更新证书</span><span class="sxs-lookup"><span data-stu-id="ea797-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ea797-115">您需要使用具有本地管理员权限的帐户登录到您的 Lync Server 2013 服务器。</span><span class="sxs-lookup"><span data-stu-id="ea797-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="ea797-116">此外，如果你在步骤12和更高版本中运行 PowerShell**请求 CsCertificate** ，该帐户需要拥有指定的证书颁发机构（CA）的权限。</span><span class="sxs-lookup"><span data-stu-id="ea797-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="ea797-117">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ea797-118">在分配已更新的证书之前，需要了解已分配给服务器的证书以及使用的类型。</span><span class="sxs-lookup"><span data-stu-id="ea797-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="ea797-119">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="ea797-120">查看上一步的输出以查看是否已为多个使用分配了单个证书，或者是否为每个使用分配了不同的证书。</span><span class="sxs-lookup"><span data-stu-id="ea797-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="ea797-121">查看 "使用" 参数以了解使用证书的方式。</span><span class="sxs-lookup"><span data-stu-id="ea797-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="ea797-122">比较所显示的证书的指纹参数，以查看相同的证书是否有多个用途。</span><span class="sxs-lookup"><span data-stu-id="ea797-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="ea797-123">随时关注指纹参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="ea797-124">更新证书。</span><span class="sxs-lookup"><span data-stu-id="ea797-124">Update the certificate.</span></span> <span data-ttu-id="ea797-125">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="ea797-126">例如，如果**CsCertificate** cmdlet 显示了使用默认值的证书，而另一个使用了 WebServicesInternal 的证书，而另一个使用 WebServicesExternal，并且它们都具有相同的指纹值，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="ea797-127">**重要提示：**</span><span class="sxs-lookup"><span data-stu-id="ea797-127">**Important:**</span></span>
    
    <span data-ttu-id="ea797-128">如果为每个使用分配了单独的证书（因此您在上面检查的指纹值对于每个证书都不同），请务必**不要**运行具有多个类型的**CsCertificate** cmdlet，如上述示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ea797-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="ea797-129">在这种情况下，为每次使用单独运行**CsCertificate** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea797-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="ea797-130">例如：</span><span class="sxs-lookup"><span data-stu-id="ea797-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="ea797-131">要查看证书（或证书），请单击 "**开始**"，然后单击 "**运行 ...**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="ea797-132">键入 MMC 以打开 Microsoft 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ea797-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="ea797-133">从 MMC 菜单中，选择 "**文件**"，选择 "**添加/删除管理单元 ...**"，然后选择 "证书"。</span><span class="sxs-lookup"><span data-stu-id="ea797-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="ea797-134">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea797-134">Click **Add**.</span></span> <span data-ttu-id="ea797-135">出现提示时，选择 "**计算机帐户**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="ea797-136">如果这是证书所在的服务器，请选择 "**本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="ea797-137">如果证书位于另一台计算机上，你应该选择**另一台计算机**，然后可以键入计算机的完全限定的域名，**或单击** **"在输入对象名称进行选择"**，然后键入计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="ea797-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="ea797-138">单击 "**检查姓名**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-138">Click **Check Names**.</span></span> <span data-ttu-id="ea797-139">当计算机的名称解析时，它将带有下划线。</span><span class="sxs-lookup"><span data-stu-id="ea797-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="ea797-140">单击 **"确定**"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="ea797-141">单击 **"确定"** 提交选定内容，然后关闭 "**添加或删除管理单元**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="ea797-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="ea797-142">若要查看证书的属性，请展开 "**证书**"，展开 "**个人**"，然后选择 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="ea797-143">选择要查看的证书，右键单击该证书，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="ea797-144">在 "**证书**" 视图中，选择 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="ea797-145">在此处，你可以通过选择 "**主题**"，然后显示 "分配的主题名称和关联的属性" 来选择证书主题名称。</span><span class="sxs-lookup"><span data-stu-id="ea797-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="ea797-146">若要查看分配的主题备用名称，请选择 "**主题备用名称**"。</span><span class="sxs-lookup"><span data-stu-id="ea797-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="ea797-147">所有指定的主题备用名称都将显示在此处。</span><span class="sxs-lookup"><span data-stu-id="ea797-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="ea797-148">此处找到的 "主题备用名称" 默认为 " **DNS 名称**" 类型。</span><span class="sxs-lookup"><span data-stu-id="ea797-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="ea797-149">你应该会看到以下成员（所有这些成员都应是在 DNS 主机中表示的完全限定的域名（A 或 IPv6 AAAA）记录：</span><span class="sxs-lookup"><span data-stu-id="ea797-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="ea797-150">此池的池名称，如果不是池，则为单个服务器名称</span><span class="sxs-lookup"><span data-stu-id="ea797-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="ea797-151">证书分配到的服务器名称</span><span class="sxs-lookup"><span data-stu-id="ea797-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="ea797-152">简单的 URL 记录，通常满足和拨入</span><span class="sxs-lookup"><span data-stu-id="ea797-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="ea797-153">Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），基于在拓扑生成器和 ridden 的 web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="ea797-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="ea797-154">如果已分配，则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="ea797-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="ea797-155">最后一项是你最感兴趣的项-如果存在 lyncdiscover 和 lyncdiscoverinternal SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="ea797-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="ea797-156">如果您有多个要检查的证书，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ea797-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="ea797-157">获得此信息后，您可以关闭 "证书" 视图和 MMC。</span><span class="sxs-lookup"><span data-stu-id="ea797-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="ea797-158">如果缺少自动发现服务使用者备用名称，并且你对默认、WebServicesInternal 和 WebServiceExternal 类型使用的是单个默认证书，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea797-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="ea797-159">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="ea797-160">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="ea797-161">而是需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="ea797-162">使用 DomainName 参数时，您必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ea797-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="ea797-163">例如：</span><span class="sxs-lookup"><span data-stu-id="ea797-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="ea797-164">若要分配证书，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ea797-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="ea797-165">其中 "指纹" 是为新颁发的证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="ea797-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="ea797-166">对于在默认、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现 SAN，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea797-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="ea797-167">在 Lync Server Management Shell 命令行提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="ea797-168">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="ea797-169">而是需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="ea797-170">使用 DomainName 参数时，您必须为 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="ea797-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="ea797-171">例如：</span><span class="sxs-lookup"><span data-stu-id="ea797-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="ea797-172">对于缺少的外部自动发现主题备用名称，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ea797-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="ea797-173">如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="ea797-174">而是需要使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="ea797-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="ea797-175">使用 DomainName 参数时，您必须为 SIP 域 FQDN 使用适当的前缀。</span><span class="sxs-lookup"><span data-stu-id="ea797-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="ea797-176">例如：</span><span class="sxs-lookup"><span data-stu-id="ea797-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="ea797-177">若要分配单个证书类型，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ea797-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="ea797-178">其中 "指纹" 是为新颁发的单个证书显示的指纹。</span><span class="sxs-lookup"><span data-stu-id="ea797-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea797-179">请注意，仅当运行步骤12和13的帐户有权访问具有相应权限的证书颁发机构时，才应运行步骤12和13。</span><span class="sxs-lookup"><span data-stu-id="ea797-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="ea797-180">如果无法使用获得这些权限的帐户进行登录，或者如果你使用的是证书的公共或远程证书颁发机构，则需要通过 Lync Server 部署向导请求它们，该向导将在下文.</span><span class="sxs-lookup"><span data-stu-id="ea797-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

