---
title: Lync Server 2013：配置被动身份验证
description: Lync Server 2013：配置被动身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548288"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="b1305-103">配置 Lync Server 2013 被动身份验证</span><span class="sxs-lookup"><span data-stu-id="b1305-103">Configuring Lync Server 2013 passive authentication</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1305-104">_**上次修改的主题：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="b1305-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="b1305-105">下一节介绍如何使用累积更新配置 Lync Server 2013：7月2013以支持被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1305-105">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="b1305-106">一旦启用，启用了双重身份验证的 Lync 用户将需要使用物理或虚拟智能卡和有效 PIN，以使用使用 Lync 2013 的累积更新来登录：7月2013客户端。</span><span class="sxs-lookup"><span data-stu-id="b1305-106">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b1305-107">强烈建议客户在服务级别为注册器和 Web 服务启用被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1305-107">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="b1305-108">如果为全局级别的注册器和 Web 服务启用了被动身份验证，则可能会导致未使用 Lync 2013 以累积更新进行登录的用户对组织范围的身份验证失败：2013客户端桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="b1305-108">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="b1305-109">Web 服务配置</span><span class="sxs-lookup"><span data-stu-id="b1305-109">Web Service Configuration</span></span>

<span data-ttu-id="b1305-110">以下步骤介绍如何为控制器、企业池和 Standard Edition 服务器创建自定义 web 服务配置，这些服务器将启用被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1305-110">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="b1305-111">**创建自定义 web 服务配置**</span><span class="sxs-lookup"><span data-stu-id="b1305-111">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="b1305-112">使用 "Lync 管理员" 帐户通过累积更新登录到 Lync Server 2013：7月 2013 6 日前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b1305-112">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="b1305-113">启动 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b1305-113">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="b1305-114">在 Lync Server 命令行管理程序命令行中，通过运行以下命令为每个控制器、企业版池和 Standard Edition 服务器创建一个新的 Web 服务配置，该配置将启用被动身份验证：</span><span class="sxs-lookup"><span data-stu-id="b1305-114">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="b1305-115">WsFedPassiveMetadataUri FQDN 的值是 AD FS 2.0 服务器的联合身份验证服务名称。</span><span class="sxs-lookup"><span data-stu-id="b1305-115">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="b1305-116">在 AD FS 2.0 管理控制台中，可通过右键单击导航窗格中的 " <STRONG>服务</STRONG> "，然后选择 " <STRONG>编辑联合身份验证服务属性</STRONG>" 来找到联合身份验证服务名称值。</span><span class="sxs-lookup"><span data-stu-id="b1305-116">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="b1305-117">通过运行以下命令，验证是否正确设置了 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：</span><span class="sxs-lookup"><span data-stu-id="b1305-117">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="b1305-118">对于客户端，被动身份验证是 web 票证身份验证的最低首选身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="b1305-118">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="b1305-119">对于将为其启用被动身份验证的所有控制器、企业池和 Standard Edition 服务器，必须通过运行以下命令在 Lync Web 服务中禁用所有其他身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="b1305-119">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="b1305-120">通过运行以下命令验证是否已成功禁用所有其他身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="b1305-120">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="b1305-121">代理配置</span><span class="sxs-lookup"><span data-stu-id="b1305-121">Proxy Configuration</span></span>

<span data-ttu-id="b1305-122">如果禁用了 Lync Web 服务的证书身份验证，Lync 客户端将使用较少的首选身份验证类型（如 Kerberos 或 NTLM）对注册器服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1305-122">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="b1305-123">仍需要证书身份验证以允许 Lync 客户端检索 web 票证，但是，必须为注册器服务禁用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="b1305-123">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="b1305-124">以下步骤介绍了如何为将为被动身份验证启用的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。</span><span class="sxs-lookup"><span data-stu-id="b1305-124">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="b1305-125">**创建自定义代理配置**</span><span class="sxs-lookup"><span data-stu-id="b1305-125">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="b1305-126">在 Lync Server 命令行管理程序命令行中，使用累积更新为每个 Lync Server 2013 创建一个新的代理配置：通过运行以下命令，将启用被动身份验证的7月 2013 Edge Edge 池、企业版池和 Standard Edition 服务器：</span><span class="sxs-lookup"><span data-stu-id="b1305-126">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="b1305-127">通过运行以下命令验证是否已成功禁用所有其他代理身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="b1305-127">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

