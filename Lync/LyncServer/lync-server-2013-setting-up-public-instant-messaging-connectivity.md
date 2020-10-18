---
title: Lync Server 2013：设置公共即时消息连接
description: Lync Server 2013：设置公共即时消息连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2f11c5e01de697b97395b6bc52815fadedff5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580108"
---
# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="12b64-103">在 Lync Server 2013 中设置公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="12b64-103">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b64-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="12b64-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="12b64-p101">如果组织希望支持与 AOL 的公共即时消息 (IM) 连接，则不能使用 Lync Server 部署向导请求证书。而是应执行以下过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="12b64-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="12b64-107">设置公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="12b64-107">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="12b64-p102">在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击您的边缘服务器或边缘服务器池。选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="12b64-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="12b64-p103">在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟(端口 5061)”。单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="12b64-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="12b64-p104">单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="12b64-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="12b64-p105">在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="12b64-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="12b64-p106">在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="12b64-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="12b64-123">为边缘服务器的外部接口创建证书请求以支持与 AOL 的公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="12b64-123">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="12b64-124">如果所需模板可供 CA 使用，请使用以下 Windows PowerShell cmdlet 在边缘服务器上请求证书：</span><span class="sxs-lookup"><span data-stu-id="12b64-124">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="12b64-125">用于 Lync Server 的模板的默认证书名称是 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="12b64-125">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="12b64-126">仅 \<template name\> 当需要使用与默认模板不同的模板时才指定。</span><span class="sxs-lookup"><span data-stu-id="12b64-126">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12b64-127">如果您的组织想要支持与 AOL 的公共 IM 连接，则必须使用 Windows PowerShell 而不是证书向导请求将证书分配给访问边缘服务的外部边缘。</span><span class="sxs-lookup"><span data-stu-id="12b64-127">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="12b64-128">这是因为证书向导用于请求证书的证书颁发机构 (CA) Web 服务器模板不支持客户端 EKU 配置。</span><span class="sxs-lookup"><span data-stu-id="12b64-128">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="12b64-129">在使用 Windows PowerShell 创建证书之前，CA 管理员必须创建和部署支持客户端 EKU 的新模板。</span><span class="sxs-lookup"><span data-stu-id="12b64-129">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

