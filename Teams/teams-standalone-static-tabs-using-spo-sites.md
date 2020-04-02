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
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100352"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>从 SharePoint Online 网站或页面创建团队 "Intranet 门户应用"

使用本文中的步骤在链接到您所在组织的 intranet 网站的团队内创建独立和静态应用。

创建 SharePoint intranet 网站的*团队个人应用*，并且将在团队内显示为选项卡。 此选项卡可能包含对所有团队用户重要的信息。 团队用户只需单击一下选项卡即可访问更新，这是一种快速且方便的方式。

请注意，所显示的流程**必须使用***新式*SharePoint 网站或页面才能正常工作。 此流程不可用于*经典*网站或页面。

> [!IMPORTANT]
> 确保为你的租户启用团队应用的加载面。 根据在团队管理门户的迁移过程中所处的位置，你可能需要在 office 的 "团队 > 管理员" 或 "管理员 > 设置" > 服务和外接程序 "> Microsoft 团队 > 应用程序 > 外部应用" 中的 ""。 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>使用应用程序制作程序创建独立的 SharePoint Online 应用

开始之前：
1. 你需要了解 SharePoint Online 新式通信或团队网站或页面的 URL。
    - 这些网站在其路径中将始终具有 */teams/* 或 */sites/* 。

2. 你需要知道租户的子域，它将在占位符 **{{子域}}** 中使用。

3. 本文将使用 **{{siteUrl}}** 占位符是你选择的网站或页面的*URL* 。
    - 示例*url*： https://contoso.sharepoint.com/teams/Contoso*或*   https://contoso.sharepoint.com/sites/Contoso 
4. 此外， **{{sitePath}}** 将用于表示 URL 的*路径*（例如：/teams/Contoso）。
    - 示例*路径*：/Teams/Contoso*或*/sites/Contoso 

请先按照以下步骤操作：

1. 转到 "团队" 存储。

2. 安装或打开应用 Studio。

3. 单击 "应用" 选项旁边的 "**打开**"。

4. 在应用 Studio 打开的情况下，单击 "**清单编辑器**"。

5. **创建新应用**。

6. 填写所有**应用详细信息**。

7. 单击 "功能" 下的**选项卡**。

8. 单击 "个人" 选项卡下的 "**添加**"。

9. 填写**名称**，然后选择**一个新的唯一实体 ID**。

10. 填写**contentURL 和网站 URL**。 

- **contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx？SPFX = true&dest = {{sitePath}}  
- **websiteUrl**： {{siteUrl}} 

    示例**contentURL**：https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. 导航到 "**域和权限**"。 请确保有效的域部分包含您的 SharePoint online 域名。

    示例： contoso.sharepoint.com

12. 添加以下 web 应用**单一登录**属性： 
     
     示例： **AAD 应用程序 ID**： 00000003-0000-0Ff1-ce00-000000000000**资源 Url**： {{子域}} .com

    ![具有 ID 和 URL 的 Web 应用单一登录。](media/personal-app.png)

13. **保存**这些属性，然后导航到 "**测试并分发**"。 

14. 安装应用以对应用程序进行个人测试。

> [!IMPORTANT]
> 如果未使用团队应用 Studio，则必须使用 .zip 清单。JSON 文件，请导航到团队中的应用商店，然后单击 "**上载自定义应用程序**" 链接（位于应用商店的右下角）。 这将使应用程序可供你使用。

15. 现在，应用作为静态选项卡提供，供你在团队中加载和查看。

## <a name="test-and-view-your-new-static-tab"></a>测试和查看新静态选项卡

若要查看团队桌面上的新选项卡，请导航到应用栏左侧的省略号（**...**）。 查找你的新应用，加载它，并在团队中测试你的独立应用程序。

如果要使新应用在较高位置的左侧菜单中可用，必须为此使用应用策略设置。 此设置可在 "团队管理员" 部分 > 应用策略 > 添加固定的应用程序中找到。 将策略分配给用户进行测试时，所做的更改将在24小时后显示。 考虑到这一点，请确定应用在最早的方便下应显示的位置，以帮助避免延迟。

若要在移动设备上查看和测试新应用，请点击屏幕底部选项卡栏上方的 v**^** 形（）打开应用抽屉。 查找你的应用并在移动设备上导航到该应用。

> [!CAUTION]
> 移动支持目前正在开发人员预览版中。 若要启用开发人员预览版，请导航到 "设置" > "，然后启用" 开发人员预览 "模式。

## <a name="a-sample-manifestjson-file"></a>示例清单 JSON 文件

你生成的 JSON 文件将如下所示。

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

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

            "entityId": "communicationSiteTab", 

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