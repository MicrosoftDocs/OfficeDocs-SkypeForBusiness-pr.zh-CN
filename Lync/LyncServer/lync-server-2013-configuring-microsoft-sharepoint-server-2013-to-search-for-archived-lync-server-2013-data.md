---
title: Lync Server 2013：配置 Microsoft SharePoint Server 2013 以搜索存档的 Lync Server 2013 数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d831638cf25df4f9c1b792c34815e8bed8c15e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525869"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="cd25e-102">配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据</span><span class="sxs-lookup"><span data-stu-id="cd25e-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd25e-103">_**上次修改的主题：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="cd25e-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="cd25e-104">将即时消息和 Web 会议脚本存储在 Microsoft Exchange Server 2013 而不是 Microsoft Lync Server 2013 中的主要优势之一是，将数据存储在相同位置，使管理员能够使用单个工具搜索已存档的 Exchange 数据和/或存档的 Lync Server 数据。</span><span class="sxs-lookup"><span data-stu-id="cd25e-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="cd25e-105">由于所有数据都存储在 Exchange)  (的同一位置，因此任何可以搜索存档的 Exchange 数据的工具也可以搜索存档的 Lync Server 数据。</span><span class="sxs-lookup"><span data-stu-id="cd25e-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="cd25e-106">一种便于搜索存档数据的工具是 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="cd25e-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="cd25e-107">如果要使用 SharePoint 搜索 Lync Server 数据，则必须先完成在 Lync Server 中配置 Exchange 存档所涉及的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="cd25e-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="cd25e-108">成功集成 Exchange 2013 和 Lync Server 2013 之后，您必须在 SharePoint 服务器上安装 Exchange Web 服务托管 API 版本 2.0;可以从 Microsoft 下载中心 () 下载该 API 的安装程序 [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) 。</span><span class="sxs-lookup"><span data-stu-id="cd25e-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="cd25e-109">下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd25e-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="cd25e-110">下载文件后，在 SharePoint 服务器上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="cd25e-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="cd25e-111">打开命令窗口，方法是依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“附件”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="cd25e-112">在命令窗口中，使用 **cd** 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd25e-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="cd25e-113">例如，如果您已将文件保存到 C：下载，请 \\ 在命令窗口中键入以下命令，然后按 enter：</span><span class="sxs-lookup"><span data-stu-id="cd25e-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="cd25e-114">若要安装该 API，请键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="cd25e-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="cd25e-115">在安装该 API 后，通过键入以下命令然后按 Enter 来重置 IIS：</span><span class="sxs-lookup"><span data-stu-id="cd25e-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="cd25e-116">安装 Exchange Web 服务后，必须在 SharePoint Server 2013 和 Exchange 2013 之间配置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="cd25e-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="cd25e-117">若要执行此操作，请首先打开 SharePoint 2013 命令行管理程序，并运行以下命令集：</span><span class="sxs-lookup"><span data-stu-id="cd25e-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="cd25e-118">务必要使用自动发现服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="cd25e-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="cd25e-119">请勿使用示例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 。</span><span class="sxs-lookup"><span data-stu-id="cd25e-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="cd25e-120">创建令牌颁发者并配置令牌服务后，运行这些命令，确保将 SharePoint 网站的 URL 替换为示例 URL http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="cd25e-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="cd25e-121">若要为 Exchange 2013 配置服务器到服务器身份验证，请打开 Exchange 命令行管理程序，并运行与此 (类似的命令（假设 Exchange 已安装在驱动器 C：上，并使用默认文件夹路径) ：</span><span class="sxs-lookup"><span data-stu-id="cd25e-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="cd25e-122">在配置合作伙伴应用程序之后，建议您在所有 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务 (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="cd25e-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="cd25e-123">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="cd25e-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="cd25e-124">可以从 Exchange 命令行管理程序或任何其他命令窗口中运行此命令。</span><span class="sxs-lookup"><span data-stu-id="cd25e-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="cd25e-125">接下来，运行如下所示的命令，该命令使指定的用户 (在此示例中，kenmyer) 在 Exchange 上执行发现的权限：</span><span class="sxs-lookup"><span data-stu-id="cd25e-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="cd25e-126">在 Exchange 和 SharePoint 之间建立了服务器到服务器身份验证之后，下一步是在 SharePoint 中创建电子数据展示网站。</span><span class="sxs-lookup"><span data-stu-id="cd25e-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="cd25e-127">可以通过在 SharePoint 命令行管理程序中运行类似以下的命令来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="cd25e-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="cd25e-128">“eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。</span><span class="sxs-lookup"><span data-stu-id="cd25e-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="cd25e-129">当新网站准备就绪后，下一步是配置 Exchange 2013 以充当 SharePoint 的结果源。</span><span class="sxs-lookup"><span data-stu-id="cd25e-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="cd25e-130">若要执行此操作，可以通过以下过程从 SharePoint 2013 管理中心页面完成：</span><span class="sxs-lookup"><span data-stu-id="cd25e-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="cd25e-131">在“管理中心”页上，单击“管理服务应用程序”\*\*\*\*，然后单击“Search Service 应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="cd25e-132">在“Search Service 应用程序: 搜索管理”页上，单击“结果源”\*\*\*\*，然后单击“新建结果源”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="cd25e-133">在“新建结果源”\*\*\*\* 窗格中，在“名称”\*\*\*\* 框中输入新结果源的名称（例如，“Microsoft Exchange”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="cd25e-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="cd25e-134">选择 " **exchange** " 作为结果源 **协议**，然后在 " **exchange 源 url** " 框中输入您的 EXCHANGE 服务器的 web 服务源 url。</span><span class="sxs-lookup"><span data-stu-id="cd25e-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="cd25e-135">该源 URL 应类似如下：</span><span class="sxs-lookup"><span data-stu-id="cd25e-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="cd25e-136">确保未选择“使用自动发现”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="cd25e-137">最后，通过在 SharePoint 发现网站中完成以下过程来创建新的电子数据展示事例和新的电子数据展示集 (例如， https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="cd25e-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="cd25e-138">在“网站内容”页上，单击“创建新的案例”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="cd25e-p110">在“网站内容: 新建 SharePoint 网站”页上，在“标题”\*\*\*\* 框中输入用户的电子邮件别名（例如，“kenmyer”\*\*\*\*），然后将同一 URL 添加至“网站地址”\*\*\*\* 框中。这将产生一个类似如下的 URL：</span><span class="sxs-lookup"><span data-stu-id="cd25e-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="cd25e-141">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-141">Click **Create**.</span></span>

4.  <span data-ttu-id="cd25e-142">当电子数据展示集页出现时，单击“标识和保留: 发现集”\*\*\*\* 下的“新建项目”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="cd25e-143">在“新建: 发现集”页上的“发现集名称”\*\*\*\* 框中输入用户的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="cd25e-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="cd25e-144">在 "**筛选器**" 框中输入**电子数据展示 Lync \* \*\* ，然后单击 "**添加 & 管理源\*\*"。</span><span class="sxs-lookup"><span data-stu-id="cd25e-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="cd25e-p112">在“添加和管理源”页上，在“邮箱”\*\*\*\* 下的第一个文本框中输入用户的电子邮件别名。单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd25e-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="cd25e-147">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd25e-147">Click **OK**.</span></span>

8.  <span data-ttu-id="cd25e-148">在“电子数据展示集”页上，单击“保存”\*\*\*\*，以保存新的电子数据展示集。</span><span class="sxs-lookup"><span data-stu-id="cd25e-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="cd25e-149">此时，您可以 (kenmyer 中搜索指定的邮箱) 和/或启用对任何其他 SharePoint 内容或结果源的 In-Place 保留方式。</span><span class="sxs-lookup"><span data-stu-id="cd25e-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

