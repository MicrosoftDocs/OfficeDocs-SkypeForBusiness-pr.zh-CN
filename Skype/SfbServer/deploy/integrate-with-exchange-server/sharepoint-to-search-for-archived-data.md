---
title: 配置 SharePoint Server 以搜索存档的 Skype for Business 数据
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 摘要： 配置 SharePoint Server 以搜索存档的 Exchange Server 和 Skype 业务服务器的数据。
ms.openlocfilehash: b9e08c5681b35b71ac7543115ee008a97e207bb7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216856"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="77966-103">配置 SharePoint Server 以搜索存档的 Skype for Business 数据</span><span class="sxs-lookup"><span data-stu-id="77966-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="77966-104">**摘要：** 配置 SharePoint Server 以搜索存档的 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="77966-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="77966-105">在 Exchange 存储即时消息和 Web 会议脚本的主要优点之一而不是 Skype 业务服务器的服务器是，在相同位置中存储数据，管理员可以使用单个工具搜索存档 Exchange 数据和/或存档的 Skype Business Server 数据。</span><span class="sxs-lookup"><span data-stu-id="77966-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="77966-106">因为所有的数据存储在同一个放置 (Exchange) 可以存档 Exchange 数据来搜索任何工具还可以搜索业务服务器数据的存档 Skype。</span><span class="sxs-lookup"><span data-stu-id="77966-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="77966-107">更加方便地搜索的存档数据的一个工具是 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77966-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="77966-108">如果您想要使用 SharePoint Business Server 数据的 Skype 搜索，您必须首先完成所有配置 Exchange 存档中 Skype Business Server 所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="77966-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="77966-109">已成功集成 Exchange Server 和 Skype 业务服务器后，然后必须在 SharePoint 服务器上安装 Exchange [Web Services 托管 API](https://go.microsoft.com/fwlink/p/?LinkId=258305) 。</span><span class="sxs-lookup"><span data-stu-id="77966-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="77966-110">下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="77966-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="77966-111">下载文件后，在 SharePoint 服务器上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="77966-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="77966-112">打开命令窗口，方法是依次单击“**开始**”、“**所有程序**”、“**附件**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="77966-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="77966-113">在命令窗口中，使用 cd 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="77966-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="77966-114">例如，如果已将文件保存到 C:\Downloads 在命令窗口中键入以下命令，然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="77966-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="77966-115">若要安装该 API，键入以下命令，然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="77966-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="77966-116">安装该 API 后，重置 IIS，通过键入以下命令并按 Enter:</span><span class="sxs-lookup"><span data-stu-id="77966-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="77966-117">安装 Exchange Web 服务之后，您必须然后配置 SharePoint Server 和 Exchange Server 之间的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="77966-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="77966-118">若要执行此操作，首先打开 SharePoint Management Shell 并运行以下命令集：</span><span class="sxs-lookup"><span data-stu-id="77966-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="77966-119">务必要使用自动发现服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="77966-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="77966-120">不使用示例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="77966-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="77966-121">您已创建的令牌颁发者并配置令牌服务之后，运行以下命令，确保用您的 SharePoint 网站的 URL 替代示例 urlhttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="77966-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="77966-122">若要配置 Exchange server 的服务器到服务器身份验证，打开 Exchange Management Shell 并运行类似如下的命令 （假定 c： 驱动器上安装了 Exchange，并使其使用的默认文件夹路径）：</span><span class="sxs-lookup"><span data-stu-id="77966-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="77966-123">配置合作伙伴应用程序后建议您停止并在所有 Exchange 邮箱和客户端访问服务器上重新启动 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="77966-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="77966-124">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="77966-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="77966-125">在 Exchange 命令行管理程序中或从任何其他命令窗口，可以从运行此命令。</span><span class="sxs-lookup"><span data-stu-id="77966-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="77966-126">接下来，运行类似以下内容，这将使指定的用户 （在本例中为 kenmyer） 进行 Exchange 上的发现的权限的命令：</span><span class="sxs-lookup"><span data-stu-id="77966-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="77966-127">Exchange 和 SharePoint 之间建立服务器到服务器身份验证后下, 一步是在 SharePoint 中创建的电子数据展示网站。</span><span class="sxs-lookup"><span data-stu-id="77966-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="77966-128">可通过运行类似于以下从 SharePoint 命令行管理程序命令：</span><span class="sxs-lookup"><span data-stu-id="77966-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="77966-129">“eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。</span><span class="sxs-lookup"><span data-stu-id="77966-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="77966-130">新的网站准备就绪后下, 一步是配置 Exchange Server for SharePoint 操作结果源。</span><span class="sxs-lookup"><span data-stu-id="77966-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="77966-131">通过完成以下过程从 SharePoint 管理中心页上，可以执行的操作：</span><span class="sxs-lookup"><span data-stu-id="77966-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="77966-132">在“管理中心”页上，单击“**管理服务应用程序**”，然后单击“**Search Service 应用程序**”。</span><span class="sxs-lookup"><span data-stu-id="77966-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="77966-133">在“Search Service 应用程序：搜索管理”页上，单击“**结果源**”，然后单击“**新建结果源**”。</span><span class="sxs-lookup"><span data-stu-id="77966-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="77966-134">在“**新建结果源**”窗格中，在“**名称**”框中输入新结果源的名称（例如，“**Microsoft Exchange**”）。</span><span class="sxs-lookup"><span data-stu-id="77966-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="77966-135">选择**Exchange**作为结果源**协议**，并为您的 Exchange 服务器，在**Exchange 源 URL**框中输入 web 服务源 URL。</span><span class="sxs-lookup"><span data-stu-id="77966-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="77966-136">该源 URL 应类似如下：</span><span class="sxs-lookup"><span data-stu-id="77966-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="77966-137">确保未选择“**使用自动发现**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="77966-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="77966-138">最后，创建新的电子数据展示案例和新的电子数据展示 （例如，完成以下过程从 SharePoint 发现网站集https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="77966-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="77966-139">在“网站内容”页上，单击“**创建新的案例**”。</span><span class="sxs-lookup"><span data-stu-id="77966-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="77966-p110">在“网站内容：新建 SharePoint 网站”页上，在“**标题**”框中输入用户的电子邮件别名（例如，“**kenmyer**”），然后将同一 URL 添加至“**网站地址**”框中。这将产生一个类似如下的 URL：</span><span class="sxs-lookup"><span data-stu-id="77966-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="77966-142">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="77966-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="77966-143">当电子数据展示集页出现时，单击“**标识和保留：发现集**”下的“**新建项目**”。</span><span class="sxs-lookup"><span data-stu-id="77966-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="77966-144">在“新建：发现集”页上的“**发现集名称**”框中输入用户的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="77966-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="77966-145">输入**电子数据展示 Lync\\*\*\*\*\*筛选器**在框中，然后单击**添加&amp;管理源**。</span><span class="sxs-lookup"><span data-stu-id="77966-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="77966-146">在添加&amp;管理源页上，在**邮箱**下的第一个文本框中输入用户的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="77966-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="77966-147">单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="77966-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="77966-148">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="77966-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="77966-149">在“电子数据展示集”页上，单击“**保存**”，以保存新的电子数据展示集。</span><span class="sxs-lookup"><span data-stu-id="77966-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="77966-150">此时，您可以搜索指定的邮箱 (kenmyer) 和/或启用就地保留相同的方式的任何其他 SharePoint 内容或结果源。</span><span class="sxs-lookup"><span data-stu-id="77966-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

