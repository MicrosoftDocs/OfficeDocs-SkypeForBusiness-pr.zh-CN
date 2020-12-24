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
description: 获取现有 SharePoint Online 网站或页面，并创建一个可用作组织 Intranet 门户的独立静态选项卡。
localization_priority: Priority
ms.openlocfilehash: 1b89a17f81024fba05a1be9fb1dc4d59b1aceafd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731110"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>从 SharePoint Online 网站或页面创建 Teams Intranet 门户应用

使用本文中的步骤，在 Teams 内创建一个链接到组织 Intranet 网站的独立和静态应用。

你的 SharePoint Intranet 网站 *Teams 个人应用* 创建完成，并在 Teams 内显示为一个选项卡。 此选项卡中可能包含对所有团队用户非常重要的信息。 只需单击一下选项卡，Teams 用户就可以快速方便地获取更新。

注意显示的过程 **必须使用***新式* SharePoint 网站或页面才能正常工作。 此过程适用于 *经典* 网站或页面。

> [!IMPORTANT]
> 确保已为租户启用了旁加载 Teams 应用。 根据在 Teams Admin 门户迁移过程中所处的位置，在上一版本门户中，可能需要在Teams > “管理员” 或在 “管理员” > “设置” > “服务和加载项” > Microsoft Teams> “应用” > “外部应用”下进行启用！

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>使用 App Studio 创建独立 SharePoint Online 应用

开始之前：

1. 需要知道 SharePoint Online 新式通信或 Team 网站或页面的 URL。
    - 这些网站在路径中始终包含 */teams/* 或 */sites/*。

2. 需要知道在占位符 **{{subdomain}}** 中使用的租户子域。

3. 本文将使用占位符 **{{siteUrl}}** 作为所选网站或页面的 *URL*。
    - 示例 *URL*：`https://contoso.sharepoint.com/teams/Contoso`
        *或* `https://contoso.sharepoint.com/sites/Contoso`
4. 此外，**{{sitePath}}** 将用于表示 URL 的 *路径*（例如： /teams/Contoso）。
    - 示例 *路径*：   /teams/Contoso   *或* /sites/Contoso

首先按照以下步骤进行操作：

1. 转到 “Teams Store”。

2. 安装或打开 App Studio。

3. 单击应用选项旁的“**打开**”。

4. App Studio 打开时，单击“**清单编辑器**”。

5. **新建应用**。

6. 填写所有“**应用详细信息**”。

7. 单击功能下的“**选项卡**”。

8. 单击“个人选项卡”下的“**添加**”。

9. 输入“**名称**”并选择“**新实体唯一 ID**”。

10. 输入“**contentURL 和网站 URL**。

- **contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**： {{siteUrl}}

    示例 **contentURL**： `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. 导航至“**域和权限**”。 确保有效的域部分包含你的 SharePoint online 域名。

    示例：`contoso.sharepoint.com`

12. 添加下列 web 应用 **单一登录** 属性：

     示例：**AAD application ID**：00000003-0000-0ff1-ce00-000000000000  **资源 Url**：{{subdomain}}.sharepoint.com

    ![Web 应用单一登录（使用 ID 和 URL）。](media/personal-app.png)

13. **保存** 这些属性，然后导航到“**测试并分发**”。

14. 安装此应用以亲自测试。

> [!IMPORTANT]
> 如果没使用 Teams App Studio，必须压缩刚创建的 manifest.JSON 文件，导航到Teams 中的 App Store，然后单击“**上传自定义应用**”链接（位于 App Store 右下角）。 然后可以使用此应用。

15. 现在此应用程序可用作静态选项卡，供你在 Teams 中加载和查看。

## <a name="test-and-view-your-new-static-tab"></a>测试并查看新静态选项卡

若要在 Teams 桌面上查看新选项卡，请导航至应用栏左侧的省略号 (**…**)。 查找新应用程序、加载、然后在 Teams 中测试你的独立应用。

如果要使新应用在更高位置的左侧菜单中可用，必须为其使用应用程序策略设置。 可以在“团队管理员”部分 > “应用策略” > “添加固定应用”下找到此设置。 将策略分配给用户进行测试时，更改将在几个小时后显示。 考虑到这一点，请确定应尽早在哪里显示此应用程序，以帮助避免延迟。

如果要在移动设备上查看和测试新应用，请点击屏幕底部附近选项卡栏上方的人字形(**^**)，打开应用列表。 查找你的应用程序，然后在移动设备上导航到此应用。

> [!CAUTION]
> 移动支持目前仅限开发人员预览模式。 若要启用开发人员预览，请导航到“设置” > “关于”，然后启用“开发人员预览”模式。

## <a name="a-sample-manifestjson-file"></a>示例清单 JSON 文件

生成的 JSON 文件如下所示。

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
