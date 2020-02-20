---
title: Lync Server 2013：删除现有的 Web 服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1e112fec8430a342a956653f99a6b4fff4ceb3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="90654-102">在 Lync Server 2013 中删除现有的 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="90654-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90654-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="90654-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="90654-104">按照以下步骤删除 web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="90654-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="90654-105">删除 web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="90654-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="90654-106">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="90654-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="90654-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="90654-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90654-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="90654-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90654-109">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“Web 服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90654-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="90654-110">在“Web 服务”\*\*\*\* 页上的搜索字段中，键入要删除的策略的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="90654-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="90654-111">在策略列表中，单击所需的策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90654-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="90654-112">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90654-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90654-113">使用 Windows PowerShell Cmdlet 删除 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="90654-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90654-114">您可以使用 Windows PowerShell 和**CsWebServiceConfiguration** cmdlet 删除 web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="90654-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="90654-115">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90654-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="90654-116">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="90654-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="90654-117">删除特定的 Web 服务配置设置集合</span><span class="sxs-lookup"><span data-stu-id="90654-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="90654-118">以下命令会删除应用到 Redmond 站点的 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="90654-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="90654-119">删除应用于网站范围的所有 web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="90654-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="90654-120">以下命令会删除应用到服务范围的所有 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="90654-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="90654-121">删除允许证书身份验证的所有 web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="90654-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="90654-122">以下命令会删除允许使用证书身份验证的所有 Web 服务安全设置：</span><span class="sxs-lookup"><span data-stu-id="90654-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="90654-123">有关详细信息，请参阅[CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="90654-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90654-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90654-124">See Also</span></span>


[<span data-ttu-id="90654-125">在 Lync Server 2013 控制面板中配置身份验证</span><span class="sxs-lookup"><span data-stu-id="90654-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

