---
title: 从 SharePoint Online 网站或页面创建 Teams Intranet 门户应用
author: cichur
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: 获取现有 SharePoint Online 网站或页面，并创建一个可用作组织 Intranet 门户的独立个人选项卡。
localization_priority: Priority
ms.openlocfilehash: c6d138b1bf95edb619de6563f644e76ec123e3c6
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607535"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="2b66f-103">从 SharePoint Online 网站或页面创建 Teams Intranet 门户应用</span><span class="sxs-lookup"><span data-stu-id="2b66f-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="2b66f-104">使用本文中的步骤，在 Teams 内创建一个链接到组织 Intranet 网站的独立和静态应用。</span><span class="sxs-lookup"><span data-stu-id="2b66f-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="2b66f-105">你的 SharePoint Intranet 网站 *Teams 个人应用* 创建完成，并在 Teams 内显示为一个选项卡。</span><span class="sxs-lookup"><span data-stu-id="2b66f-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="2b66f-106">此选项卡中可能包含对所有团队用户非常重要的信息。</span><span class="sxs-lookup"><span data-stu-id="2b66f-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="2b66f-107">只需单击一下选项卡，Teams 用户就可以快速方便地获取更新。</span><span class="sxs-lookup"><span data-stu-id="2b66f-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="2b66f-108">注意显示的过程 \**必须使用\*\*\*新式* SharePoint 网站或页面才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="2b66f-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="2b66f-109">此过程适用于 *经典* 网站或页面。</span><span class="sxs-lookup"><span data-stu-id="2b66f-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b66f-110">确保已为租户启用了旁加载 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="2b66f-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="2b66f-111">根据在 Teams Admin 门户迁移过程中所处的位置，在上一版本门户中，可能需要在Teams > “管理员” 或在 “管理员” > “设置” > “服务和加载项” > Microsoft Teams> “应用” > “外部应用”下进行启用！</span><span class="sxs-lookup"><span data-stu-id="2b66f-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="2b66f-112">使用 App Studio 创建独立 SharePoint Online 应用</span><span class="sxs-lookup"><span data-stu-id="2b66f-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="2b66f-113">开始之前：</span><span class="sxs-lookup"><span data-stu-id="2b66f-113">Before you begin:</span></span>

1. <span data-ttu-id="2b66f-114">需要知道 SharePoint Online 新式通信或 Team 网站或页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="2b66f-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>

   <span data-ttu-id="2b66f-115">这些网站在路径中始终包含 */teams/* 或 */sites/*。</span><span class="sxs-lookup"><span data-stu-id="2b66f-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="2b66f-116">需要知道在占位符 **{{subdomain}}** 中使用的租户子域。</span><span class="sxs-lookup"><span data-stu-id="2b66f-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="2b66f-117">本文将使用占位符 **{{siteUrl}}** 作为所选网站或页面的 *URL*。</span><span class="sxs-lookup"><span data-stu-id="2b66f-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>

   <span data-ttu-id="2b66f-118">示例 *URL*：</span><span class="sxs-lookup"><span data-stu-id="2b66f-118">Example *URLs*:</span></span>
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/><span data-ttu-id="2b66f-119">*或者*</span><span class="sxs-lookup"><span data-stu-id="2b66f-119">*or*</span></span>
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. <span data-ttu-id="2b66f-120">此外，**{{sitePath}}** 将用于表示 URL 的 *路径*（例如：/teams/Contoso）。</span><span class="sxs-lookup"><span data-stu-id="2b66f-120">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>

   <span data-ttu-id="2b66f-121">示例 *路径*：</span><span class="sxs-lookup"><span data-stu-id="2b66f-121">Example *paths*:</span></span>
   
   - <span data-ttu-id="2b66f-122">/teams/Contoso</span><span class="sxs-lookup"><span data-stu-id="2b66f-122">/teams/Contoso</span></span>
     <br/><span data-ttu-id="2b66f-123">*或者*</span><span class="sxs-lookup"><span data-stu-id="2b66f-123">*or*</span></span>
   - <span data-ttu-id="2b66f-124">/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="2b66f-124">/sites/Contoso</span></span>

<span data-ttu-id="2b66f-125">首先按照以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="2b66f-125">Begin by following the steps below:</span></span>

1. <span data-ttu-id="2b66f-126">转到 “Teams Store”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-126">Go to the Teams Store.</span></span>

2. <span data-ttu-id="2b66f-127">安装或打开 App Studio。</span><span class="sxs-lookup"><span data-stu-id="2b66f-127">Install or open App Studio.</span></span>

3. <span data-ttu-id="2b66f-128">单击应用选项旁的“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-128">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="2b66f-129">App Studio 打开时，单击“**清单编辑器**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-129">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="2b66f-130">**新建应用**。</span><span class="sxs-lookup"><span data-stu-id="2b66f-130">**Create a new app**.</span></span>

6. <span data-ttu-id="2b66f-131">填写所有“**应用详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-131">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="2b66f-132">单击功能下的“**选项卡**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-132">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="2b66f-133">单击“个人选项卡”下的“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-133">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="2b66f-134">输入“**名称**”并选择“**新实体唯一 ID**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-134">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="2b66f-135">输入“**contentURL 和网站 URL**。</span><span class="sxs-lookup"><span data-stu-id="2b66f-135">Fill in the **contentURL and Website URL**.</span></span>

    - <span data-ttu-id="2b66f-136">**contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="2b66f-136">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
    
    - <span data-ttu-id="2b66f-137">**websiteUrl**： {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="2b66f-137">**websiteUrl**: {{siteUrl}}</span></span>

      <span data-ttu-id="2b66f-138">示例 **contentURL**：</span><span class="sxs-lookup"><span data-stu-id="2b66f-138">Example **contentURL**:</span></span>
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. <span data-ttu-id="2b66f-139">导航至“**域和权限**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-139">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="2b66f-140">确保有效的域部分包含你的 SharePoint online 域名。</span><span class="sxs-lookup"><span data-stu-id="2b66f-140">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="2b66f-141">示例：`contoso.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="2b66f-141">Example: `contoso.sharepoint.com`</span></span>

12. <span data-ttu-id="2b66f-142">添加下列 web 应用 **单一登录** 属性：</span><span class="sxs-lookup"><span data-stu-id="2b66f-142">Add the following web app **single sign-on** properties:</span></span>

    <span data-ttu-id="2b66f-143">示例：</span><span class="sxs-lookup"><span data-stu-id="2b66f-143">Example:</span></span>
    
    - <span data-ttu-id="2b66f-144">**AAD 应用程序 ID**：00000003-0000-0ff1-ce00-000000000000</span><span class="sxs-lookup"><span data-stu-id="2b66f-144">**AAD application ID**: 00000003-0000-0ff1-ce00-000000000000</span></span>
    
    - <span data-ttu-id="2b66f-145">**资源 Url**：{{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="2b66f-145">**Resource Url**: {{subdomain}}.sharepoint.com</span></span>

      ![Web 应用单一登录（使用 ID 和 URL）。](media/personal-app.png)

13. <span data-ttu-id="2b66f-147">**保存** 这些属性，然后导航到“**测试并分发**”。</span><span class="sxs-lookup"><span data-stu-id="2b66f-147">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="2b66f-148">安装此应用以亲自测试。</span><span class="sxs-lookup"><span data-stu-id="2b66f-148">Install the app to test the application personally.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2b66f-149">如果没使用 Teams App Studio，必须压缩刚创建的 manifest.JSON 文件，导航到Teams 中的 App Store，然后单击“**上传自定义应用**”链接（位于 App Store 右下角）。</span><span class="sxs-lookup"><span data-stu-id="2b66f-149">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="2b66f-150">然后可以使用此应用。</span><span class="sxs-lookup"><span data-stu-id="2b66f-150">This will make the app available to you.</span></span>

15. <span data-ttu-id="2b66f-151">现在此应用程序可用作个人选项卡，供你在 Teams 中加载和查看。</span><span class="sxs-lookup"><span data-stu-id="2b66f-151">Now the app is available as a personal tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-personal-tab"></a><span data-ttu-id="2b66f-152">测试并查看新个人选项卡</span><span class="sxs-lookup"><span data-stu-id="2b66f-152">Test and view your new personal tab</span></span>

<span data-ttu-id="2b66f-153">若要在 Teams 桌面上查看新选项卡，请导航至应用栏左侧的省略号 (**…**)。</span><span class="sxs-lookup"><span data-stu-id="2b66f-153">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="2b66f-154">查找新应用程序、加载、然后在 Teams 中测试你的独立应用。</span><span class="sxs-lookup"><span data-stu-id="2b66f-154">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="2b66f-155">如果要使新应用在更高位置的左侧菜单中可用，必须为其使用应用程序策略设置。</span><span class="sxs-lookup"><span data-stu-id="2b66f-155">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="2b66f-156">可以在“团队管理员”部分 > “应用策略” > “添加固定应用”下找到此设置。</span><span class="sxs-lookup"><span data-stu-id="2b66f-156">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="2b66f-157">将策略分配给用户进行测试时，更改将在几个小时后显示。</span><span class="sxs-lookup"><span data-stu-id="2b66f-157">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="2b66f-158">考虑到这一点，请确定应尽早在哪里显示此应用程序，以帮助避免延迟。</span><span class="sxs-lookup"><span data-stu-id="2b66f-158">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="2b66f-159">如果要在移动设备上查看和测试新应用，请点击屏幕底部附近选项卡栏上方的人字形(**^**)，打开应用列表。</span><span class="sxs-lookup"><span data-stu-id="2b66f-159">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="2b66f-160">查找你的应用程序，然后在移动设备上导航到此应用。</span><span class="sxs-lookup"><span data-stu-id="2b66f-160">Find your app and navigate to it on your mobile device.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="2b66f-161">示例清单 JSON 文件</span><span class="sxs-lookup"><span data-stu-id="2b66f-161">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="2b66f-162">生成的 JSON 文件如下所示。</span><span class="sxs-lookup"><span data-stu-id="2b66f-162">The JSON file you generate will look something like the one below.</span></span>

```json
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.9/MicrosoftTeams.schema.json",

    "manifestVersion": "1.9",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso",

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet",

        "full": "Intranet Portal for Contoso"

    },

    "description": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

            "entityId": "communicationSiteTab",

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
