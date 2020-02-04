---
title: Lync Server 2013：验证或配置 IIS 虚拟目录的身份验证和认证
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
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="1db2c-102">在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和认证</span><span class="sxs-lookup"><span data-stu-id="1db2c-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1db2c-103">_**主题上次修改时间：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="1db2c-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="1db2c-104">使用以下过程在 Internet Information Services （IIS）虚拟目录上配置证书或验证证书的配置是否正确。</span><span class="sxs-lookup"><span data-stu-id="1db2c-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="1db2c-105">在内部 Lync 服务器池中运行 IIS 的每台服务器以及可选 Director 或控制器池服务器上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="1db2c-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1db2c-106">下面的过程定义一个过程，用于请求一个用于所有用途的证书的合并证书，该证书用于所有用途的 Lync Server、内部网站和 IIS 中的外部网站。</span><span class="sxs-lookup"><span data-stu-id="1db2c-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="1db2c-107">Lync Server 2010 引入了一组 Lync Server Management Shell&nbsp;Windows PowerShell cmdlet，用于管理证书请求、导入和作业的快速目的。</span><span class="sxs-lookup"><span data-stu-id="1db2c-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="1db2c-108">该过程假设有一个内部部署的证书颁发机构（CA）可以处理请求。</span><span class="sxs-lookup"><span data-stu-id="1db2c-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="1db2c-109">如果你为 Lync Server 目的使用公共证书，或者你的 CA 需要脱机请求，请参阅本主题中的详细语法，了解有关-Output 参数的信息。</span><span class="sxs-lookup"><span data-stu-id="1db2c-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="1db2c-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">请求-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="1db2c-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="1db2c-111">在 IIS 虚拟目录上配置身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="1db2c-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="1db2c-112">若要成功完成以下操作，必须登录到安装了 web 服务的计算机（前端服务器或控制器），并且是本地管理员。</span><span class="sxs-lookup"><span data-stu-id="1db2c-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="1db2c-113">如果证书颁发机构是您所在组织的证书颁发机构，则您必须在您将申请证书的证书颁发机构上拥有 "**读取**" 和 "**注册**" 权限。</span><span class="sxs-lookup"><span data-stu-id="1db2c-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="1db2c-114">如果你要配置和发送脱机证书请求，则不需要对证书颁发机构的权限。</span><span class="sxs-lookup"><span data-stu-id="1db2c-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="1db2c-115">单击 "**开始**"，选择 "**所有程序**"，选择 "**管理工具**"，然后单击 " **Internet 信息服务（IIS）管理器**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="1db2c-116">在 " **Internet 信息服务（IIS）管理器**" 中，选择 "**服务器名**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="1db2c-117">在 "**功能" 视图**中，选择 "**服务器证书**"，右键单击，然后选择 "**打开功能**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1db2c-118">在 "服务器证书" 功能视图中，如果有证书分配给服务器，它们将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="1db2c-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="1db2c-119">如果存在与 IIS 中的外部网站要求相匹配的证书，则可以重新使用该证书。</span><span class="sxs-lookup"><span data-stu-id="1db2c-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="1db2c-120">要查看证书，请右键单击证书，然后选择 "<STRONG>查看 ...</STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="1db2c-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="1db2c-121">在请求证书的前端服务器或控制器上，单击 "**开始**"，选择 "**所有程序**"，选择 " **Microsoft lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="1db2c-122">在 Lync Server 命令行管理器中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1db2c-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="1db2c-123">输出是当前在计算机个人证书存储中的服务器上的证书的列表。</span><span class="sxs-lookup"><span data-stu-id="1db2c-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="1db2c-124">请注意，在合并的证书（即，默认情况下，内部 web 服务内部和 web 服务外部使用相同的证书）中，你将看到 Use 属性将使用 Default、WebServicesInternal 和 WebServicesExternal 填充。</span><span class="sxs-lookup"><span data-stu-id="1db2c-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="1db2c-125">此外，每个使用类型的 Thumbprint 属性都是相同的。</span><span class="sxs-lookup"><span data-stu-id="1db2c-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="1db2c-126">此示例中显示了 CsCertificate 的示例输出：</span><span class="sxs-lookup"><span data-stu-id="1db2c-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="1db2c-127">![当前 scert 状态的 CsCertificate 信息](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "当前 scert 状态的 CsCertificate 信息")</span><span class="sxs-lookup"><span data-stu-id="1db2c-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="1db2c-128">在 Lync Server 命令行管理器中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1db2c-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="1db2c-129">将出现完整命令的位置，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="1db2c-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1db2c-130">默认情况下，请求-CsCertificate 将使用服务器或池名称填充主题名称，并使用服务器 FQDN、池 FQDN、简单 URL Fqdn 以及内部和外部 web 服务 Fqdn 填充主题备用名称中的条目。</span><span class="sxs-lookup"><span data-stu-id="1db2c-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="1db2c-131">它通过在你的部署中引用拓扑文档来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1db2c-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="1db2c-132">如果缺少值，并且指定了-Verbose 参数，则系统将通知你替换名称的计算值和实际值不同，但不会通知你缺少哪些值。</span><span class="sxs-lookup"><span data-stu-id="1db2c-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="1db2c-133">它将为你提供 cmdlet 引用的整个计算值。</span><span class="sxs-lookup"><span data-stu-id="1db2c-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="1db2c-134">使用 "输出" 中的 "计算出的替换名称" 字符串重新请求将包含所有值的新证书。</span><span class="sxs-lookup"><span data-stu-id="1db2c-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="1db2c-135">![使用请求-CsCertifica 的证书请求的输出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用请求-CsCertifica 的证书请求的输出")</span><span class="sxs-lookup"><span data-stu-id="1db2c-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="1db2c-136">在 Lync Server 命令行管理器中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1db2c-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="1db2c-137">将出现完整命令的位置，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="1db2c-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="1db2c-138">CsCertificate cmdlet 的输出将显示相同的证书（由证书的指纹所标识）分配给默认、WebServicesExternal 和 WebServicesInternal 用法。</span><span class="sxs-lookup"><span data-stu-id="1db2c-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="1db2c-139">![IIS WebExt 上的 CsCertificate 设置输出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt 上的 CsCertificate 设置输出")</span><span class="sxs-lookup"><span data-stu-id="1db2c-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="1db2c-140">在 IIS 虚拟目录上验证或配置身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="1db2c-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="1db2c-141">单击 "**开始**"，选择 "**所有程序**"，选择 "**管理工具**"，然后单击 " **Internet 信息服务（IIS）管理器**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="1db2c-142">在 " **Internet 信息服务（IIS）管理器**" 中，展开 "**服务器名**"，然后展开 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="1db2c-143">右键单击 " **Lync 服务器外部网站**"，然后单击 "**编辑绑定**"</span><span class="sxs-lookup"><span data-stu-id="1db2c-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="1db2c-144">验证 https 是否与端口4443关联，然后单击 " **https**"。</span><span class="sxs-lookup"><span data-stu-id="1db2c-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="1db2c-145">选择 HTTPS 条目，单击 "**编辑**"，然后验证 Lync Server WebServicesExternalCertificate 是否绑定到此协议。</span><span class="sxs-lookup"><span data-stu-id="1db2c-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="1db2c-146">比较 CsCertificate cmdlet 中的指纹，以确保预期的证书与 HTTPS 绑定正确关联。</span><span class="sxs-lookup"><span data-stu-id="1db2c-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1db2c-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1db2c-147">See Also</span></span>


[<span data-ttu-id="1db2c-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1db2c-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="1db2c-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1db2c-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

