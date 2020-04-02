---
title: 从 SharePoint Online 网站或页面创建团队 "Intranet 门户应用"
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 获取现有 SharePoint Online 网站或页面，并创建可用作您的组织的 Intranet 门户的独立静态选项卡。
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106629"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="d8d10-103">从 SharePoint Online 网站或页面创建团队 "Intranet 门户应用"</span><span class="sxs-lookup"><span data-stu-id="d8d10-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="d8d10-104">使用本文中的步骤在链接到您所在组织的 intranet 网站的团队内创建独立和静态应用。</span><span class="sxs-lookup"><span data-stu-id="d8d10-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="d8d10-105">创建 SharePoint intranet 网站的*团队个人应用*，并且将在团队内显示为选项卡。</span><span class="sxs-lookup"><span data-stu-id="d8d10-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="d8d10-106">此选项卡可能包含对所有团队用户重要的信息。</span><span class="sxs-lookup"><span data-stu-id="d8d10-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="d8d10-107">团队用户只需单击一下选项卡即可访问更新，这是一种快速且方便的方式。</span><span class="sxs-lookup"><span data-stu-id="d8d10-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="d8d10-108">请注意，所显示的流程\**必须使用\*\*\*新式*SharePoint 网站或页面才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="d8d10-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="d8d10-109">此流程不可用于*经典*网站或页面。</span><span class="sxs-lookup"><span data-stu-id="d8d10-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8d10-110">确保为你的租户启用团队应用的加载面。</span><span class="sxs-lookup"><span data-stu-id="d8d10-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="d8d10-111">根据在团队管理门户的迁移过程中所处的位置，你可能需要在 office 的 "团队 > 管理员" 或 "管理员 > 设置" > 服务和外接程序 "> Microsoft 团队 > 应用程序 > 外部应用" 中的 ""。</span><span class="sxs-lookup"><span data-stu-id="d8d10-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="d8d10-112">使用应用程序制作程序创建独立的 SharePoint Online 应用</span><span class="sxs-lookup"><span data-stu-id="d8d10-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="d8d10-113">' ' ' 开始之前：</span><span class="sxs-lookup"><span data-stu-id="d8d10-113">''' Before you begin:</span></span>
1. <span data-ttu-id="d8d10-114">你需要了解 SharePoint Online 新式通信或团队网站或页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="d8d10-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="d8d10-115">这些网站在其路径中将始终具有 */teams/* 或 */sites/* 。</span><span class="sxs-lookup"><span data-stu-id="d8d10-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="d8d10-116">你需要知道租户的子域，它将在占位符 **{{子域}}** 中使用。</span><span class="sxs-lookup"><span data-stu-id="d8d10-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="d8d10-117">本文将使用 **{{siteUrl}}** 占位符是你选择的网站或页面的*URL* 。</span><span class="sxs-lookup"><span data-stu-id="d8d10-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="d8d10-118">示例*url*： https://contoso.sharepoint.com/teams/Contoso*或*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="d8d10-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="d8d10-119">此外， **{{sitePath}}** 将用于表示 URL 的*路径*（例如：/teams/Contoso）。</span><span class="sxs-lookup"><span data-stu-id="d8d10-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="d8d10-120">示例*路径*：/Teams/Contoso*或*/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="d8d10-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="d8d10-121">请先按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d8d10-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="d8d10-122">转到 "团队" 存储。</span><span class="sxs-lookup"><span data-stu-id="d8d10-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="d8d10-123">安装或打开应用 Studio。</span><span class="sxs-lookup"><span data-stu-id="d8d10-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="d8d10-124">单击 "应用" 选项旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="d8d10-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="d8d10-125">在应用 Studio 打开的情况下，单击 "**清单编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="d8d10-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="d8d10-126">**创建新应用**。</span><span class="sxs-lookup"><span data-stu-id="d8d10-126">**Create a new app**.</span></span>

6. <span data-ttu-id="d8d10-127">填写所有**应用详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d8d10-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="d8d10-128">单击 "功能" 下的**选项卡**。</span><span class="sxs-lookup"><span data-stu-id="d8d10-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="d8d10-129">单击 "个人" 选项卡下的 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="d8d10-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="d8d10-130">填写**名称**，然后选择**一个新的唯一实体 ID**。</span><span class="sxs-lookup"><span data-stu-id="d8d10-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="d8d10-131">填写**contentURL 和网站 URL**。</span><span class="sxs-lookup"><span data-stu-id="d8d10-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="d8d10-132">**contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx？SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="d8d10-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="d8d10-133">**web'iteUrl**： {{siteUrl}} ' ' 示例**contentURL**：https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="d8d10-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="d8d10-134">导航到 "**域和 Permissi'ns**"。</span><span class="sxs-lookup"><span data-stu-id="d8d10-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="d8d10-135">请确保有效的域部分包含您的 SharePoint online 域名。</span><span class="sxs-lookup"><span data-stu-id="d8d10-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="d8d10-136">' ' 示例： contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="d8d10-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="d8d10-137">添加以下 web 应用**单一登录**属性： "' 示例： ' ' ' ' **AAD 应用程序 ID**： 00000003-0000-0ff1-ce00-000000000000**资源 Url**： {{子域}} web.config" ![web APP 单一登录，其中包含 ID 和 Url。](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="d8d10-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="d8d10-138">**保存**这些属性，然后导航到 "**测试并分发**"。</span><span class="sxs-lookup"><span data-stu-id="d8d10-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="d8d10-139">安装应用以对应用程序进行个人测试。</span><span class="sxs-lookup"><span data-stu-id="d8d10-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8d10-140">如果未使用团队应用 Studio，则必须使用 .zip 清单。JSON 文件，请导航到团队中的应用商店，然后单击 "**上载自定义应用程序**" 链接（位于应用商店的右下角）。</span><span class="sxs-lookup"><span data-stu-id="d8d10-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="d8d10-141">这将使应用程序可供你使用。</span><span class="sxs-lookup"><span data-stu-id="d8d10-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="d8d10-142">现在，应用作为静态选项卡提供，供你在团队中加载和查看。</span><span class="sxs-lookup"><span data-stu-id="d8d10-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="d8d10-143">测试和查看新静态选项卡</span><span class="sxs-lookup"><span data-stu-id="d8d10-143">Test and view your new static tab</span></span>

<span data-ttu-id="d8d10-144">若要查看团队桌面上的新选项卡，请导航到应用栏左侧的省略号（**...**）。</span><span class="sxs-lookup"><span data-stu-id="d8d10-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="d8d10-145">查找你的新应用，加载它，并在团队中测试你的独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8d10-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="d8d10-146">如果要使新应用在较高位置的左侧菜单中可用，必须为此使用应用策略设置。</span><span class="sxs-lookup"><span data-stu-id="d8d10-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="d8d10-147">此设置可在 "团队管理员" 部分 > 应用策略 > 添加固定的应用程序中找到。</span><span class="sxs-lookup"><span data-stu-id="d8d10-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="d8d10-148">将策略分配给用户进行测试时，所做的更改将在24小时后显示。</span><span class="sxs-lookup"><span data-stu-id="d8d10-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="d8d10-149">考虑到这一点，请确定应用在最早的方便下应显示的位置，以帮助避免延迟。</span><span class="sxs-lookup"><span data-stu-id="d8d10-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="d8d10-150">若要在移动设备上查看和测试新应用，请点击屏幕底部选项卡栏上方的 v**^** 形（）打开应用抽屉。</span><span class="sxs-lookup"><span data-stu-id="d8d10-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="d8d10-151">查找你的应用并在移动设备上导航到该应用。</span><span class="sxs-lookup"><span data-stu-id="d8d10-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="d8d10-152">移动支持目前正在开发人员预览版中。</span><span class="sxs-lookup"><span data-stu-id="d8d10-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="d8d10-153">若要启用开发人员预览版，请导航到 "设置" > "，然后启用" 开发人员预览 "模式。</span><span class="sxs-lookup"><span data-stu-id="d8d10-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="d8d10-154">示例清单 JSON 文件</span><span class="sxs-lookup"><span data-stu-id="d8d10-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="d8d10-155">你生成的 JSO 文件将如下所示。</span><span class="sxs-lookup"><span data-stu-id="d8d10-155">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso" 

    },                     
                        
    "des    ription": {                 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 
''
    "staticTabs": [ 

        { 
                                       
                     "       nti        Id":       "com    unicat    onSi    eTab", 
                                       
            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```