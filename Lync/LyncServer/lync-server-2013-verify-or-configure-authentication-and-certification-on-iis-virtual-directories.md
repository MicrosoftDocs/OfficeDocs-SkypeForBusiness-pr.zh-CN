---
title: Lync Server 2013：验证或配置 IIS 虚拟目录上的身份验证和证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28011a5eb436096d0d8486a6f05ac9024ac388d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="990b4-102">在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="990b4-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="990b4-103">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="990b4-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="990b4-104">使用以下过程可在 Internet Information Services （IIS）虚拟目录上配置证书，或验证证书是否已正确配置。</span><span class="sxs-lookup"><span data-stu-id="990b4-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="990b4-105">在内部 Lync Server 池中运行 IIS 的每台服务器和可选控制器（即控制器池服务器）上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="990b4-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="990b4-106">以下过程定义了一个过程，该过程将请求用于所有目的 Lync Server、内部网站和 IIS 中的外部网站的组合证书。</span><span class="sxs-lookup"><span data-stu-id="990b4-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="990b4-107">Lync Server 2010 引入了一组 Lync Server 命令行&nbsp;管理程序 Windows PowerShell cmdlet，用于管理证书请求、导入和分配的快速目的。</span><span class="sxs-lookup"><span data-stu-id="990b4-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="990b4-108">该过程假定存在可以处理该请求的内部部署证书颁发机构 (CA)。</span><span class="sxs-lookup"><span data-stu-id="990b4-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="990b4-109">如果您使用公共证书进行 Lync Server 目的，或者您的 CA 需要脱机请求，请参阅本主题中的详细语法，以获取有关– Output 参数的信息。</span><span class="sxs-lookup"><span data-stu-id="990b4-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="990b4-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">请求-Set-cscertificate</A></span><span class="sxs-lookup"><span data-stu-id="990b4-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="990b4-111">在 IIS 虚拟目录中配置身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="990b4-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="990b4-112">若要成功完成以下工作，您必须登录到安装了 web 服务的计算机（前端服务器或控制器），并将其作为本地管理员。</span><span class="sxs-lookup"><span data-stu-id="990b4-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="990b4-113">您必须具有将向其请求证书的证书颁发机构的**读取**和**注册**权限（如果该证书颁发机构是贵组织的证书颁发机构）。</span><span class="sxs-lookup"><span data-stu-id="990b4-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="990b4-114">如果您配置并发送脱机证书请求，则不需要证书颁发机构的权限。</span><span class="sxs-lookup"><span data-stu-id="990b4-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="990b4-115">单击“开始”\*\*\*\*，选择“所有程序”\*\*\*\*，选择“管理工具”\*\*\*\*，然后单击“Internet 信息服务(IIS)管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="990b4-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="990b4-p104">在“Internet 信息服务(IIS)管理器”\*\*\*\* 中，选择“服务器名称”\*\*\*\*。在“功能视图”\*\*\*\* 中，选择“服务器证书”\*\*\*\*，右键单击并选择“打开功能”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="990b4-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="990b4-p105">在“服务器证书功能视图”中，如果向服务器分配了证书，则这些证书会显示在此处。如果某证书与 IIS 中外部网站的要求匹配，您可以重新使用该证书。要查看证书，请右键单击相应证书并选择“查看…”<STRONG></STRONG></span><span class="sxs-lookup"><span data-stu-id="990b4-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="990b4-121">在要为其请求证书的前端服务器或控制器上，单击 "**开始**"，选择 "**所有程序**"，选择 " **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="990b4-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="990b4-122">在 Lync Server 命令行管理程序中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="990b4-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="990b4-p106">输出是当前位于服务器上计算机个人证书存储中的证书的列表。请注意，在组合证书（即默认情况下，Web 服务内部和 Web 服务外部均使用相同的证书）中，您将看到 Use 属性将由默认值 WebServicesInternal 和 WebServicesExternal 进行填充。另外，Thumbprint 属性对于每种 Use 类型都一样。此示例显示了 Get-CsCertificate 的示例输出：</span><span class="sxs-lookup"><span data-stu-id="990b4-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="990b4-127">![当前 scert 状态的 Set-cscertificate 信息](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "当前 scert 状态的 Set-cscertificate 信息")</span><span class="sxs-lookup"><span data-stu-id="990b4-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="990b4-128">在 Lync Server 命令行管理程序中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="990b4-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="990b4-129">其中，完整命令如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="990b4-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="990b4-p107">默认情况下，Request-CsCertificate 将使用服务器或池名称填充使用者名称，使用服务器 FQDN、池 FQDN、简单 URL FQDN 以及内部和外部 Web 服务 FQDN 填充使用者替代名称中的条目。它通过引用您的部署中的拓扑文档来执行此操作。如果缺少值并且您指定了 –Verbose 参数，那么将通知您替代名称的计算值和实际值不同，但不会告知您缺少哪些值。该命令会向您提供 cmdlet 引用的完整计算值。在输出中使用计算的替代名称字符串以重新请求包括所有值的新证书。</span><span class="sxs-lookup"><span data-stu-id="990b4-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="990b4-135">![使用请求-CsCertifica 的 cert 请求的输出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用请求-CsCertifica 的 cert 请求的输出")</span><span class="sxs-lookup"><span data-stu-id="990b4-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="990b4-136">在 Lync Server 命令行管理程序中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="990b4-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="990b4-137">其中，完整命令如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="990b4-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="990b4-138">Set-CsCertificate cmdlet 的输出将指示为默认 WebServicesExternal 和 WebServicesInternal 用法分配了相同的证书（通过证书的指纹识别）。</span><span class="sxs-lookup"><span data-stu-id="990b4-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="990b4-139">![IIS WebExt 上的 Set-cscertificate 中的输出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt 上的 Set-cscertificate 中的输出")</span><span class="sxs-lookup"><span data-stu-id="990b4-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="990b4-140">在 IIS 虚拟目录中验证或配置身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="990b4-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="990b4-141">单击“开始”\*\*\*\*，依次选择“所有程序”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“Internet 信息服务(IIS)管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="990b4-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="990b4-142">在**Internet Information Services （IIS）管理器**中，展开 "**服务器名称**"，然后展开 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="990b4-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="990b4-143">右键单击“Lync Server 外部网站”\*\*\*\*，然后单击“编辑绑定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="990b4-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="990b4-144">验证 https 是否与端口 4443 关联，然后单击“https”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="990b4-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="990b4-145">选择 HTTPS 条目，单击 "**编辑**"，然后验证是否已将 Lync Server WebServicesExternalCertificate 绑定到此协议。</span><span class="sxs-lookup"><span data-stu-id="990b4-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="990b4-146">比较来自 Set-CsCertificate cmdlet 的指纹以确保所需证书已与 HTTPS 绑定正确关联。</span><span class="sxs-lookup"><span data-stu-id="990b4-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="990b4-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="990b4-147">See Also</span></span>


[<span data-ttu-id="990b4-148">Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="990b4-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="990b4-149">Set-cscertificate</span><span class="sxs-lookup"><span data-stu-id="990b4-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

