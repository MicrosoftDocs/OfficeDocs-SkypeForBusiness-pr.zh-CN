---
title: 在 Microsoft Teams 中授权来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200e0d94948d735786fd1775fc803c6017bd3100
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2019
ms.locfileid: "40019976"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中授权来宾访问
===========================================

为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。 所有这些授权级别都适用于你的 Office 365 租户。 每个授权级别按如下所示控制来宾体验：

- **Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。 此授权级别控制目录、租户和应用程序级别的来宾体验。
- **Microsoft Teams**：仅控制 Microsoft Teams 中的来宾体验。
- **Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。
- **SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。

这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。 例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，但想在组织中全面允许，只需在 Microsoft Teams 中关闭来宾访问即可。 其他示例：你可以在 Azure AD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。 SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。

> [!NOTE]
> 来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。 

下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。

![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)

下一张示意图概括性地显示了用户体验如何通过典型的来宾访问邀请和兑换流程与权限模型结合使用。

![显示邀请和兑换流程的示意图](media/authorize-guest-image1.png)

此处有必要注意的是，应用、机器人和连接器可能需要自己的一套特定于用户帐户的权限和/或同意。 这些可能需要单独授予。 同样，SharePoint 可能针对特定用户、用户组，甚至在站点级别设置了额外的外部共享界限。

上两张示意图还可在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中查看。

## <a name="control-guest-access-in-azure-active-directory"></a>控制 Azure Active Directory 中的条件访问

使用 Azure AD 来确定外部协作者能否受邀以来宾的身份加入你的租户以及如何加入。 有关 Azure B2B 来宾访问的详细信息，请参阅[什么是 Azure Active Directory B2B 中的来宾用户访问权限](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。 要了解 Azure AD 角色，请参阅[在 Azure Active Directory 租户中向来自合作伙伴组织的用户授予权限](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。

邀请设置在租户级别应用，可控制目标、租户和应用程序级别的来宾体验。 要在 Azure 门户中配置这些设置，请转到“**Azure Active Directory**” > “**用户**” > “**用户设置**”，再在“**外部用户**”下选择“**管理外部协作设置**”。

Azure AD 包含用于配置外部用户的以下设置：

- **限制来宾用户权限**：“**是**”表示来宾无权处理某些目录任务，例如枚举用户、组或其他目录资源。 此外，未将来宾分配到你目录中的管理角色。 “**否**”表示来宾与目录中的常规用户具有相同的目录数据访问权限。
- **管理员和具有“来宾邀请者”角色的用户可以邀请**：“**是**”表示管理员和具有“来宾邀请者”角色的用户将能够邀请来宾加入租户。 “**否**”表示管理员和用户不可邀请来宾加入租户。
- **成员可邀请**：“**是**”表示目录的非管理员成员可邀请来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。 “**否**”表示只有管理员可邀请来宾到你的目录。</br>
      
    > [!IMPORTANT]
    > 要让来宾访问可在 Teams 中正常工作，必须将“**成员可邀请**”设置为“**是**”。
- **来宾可邀请**：“**是**”表示目录中的来宾可邀请其他来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。 “**否**”表示来宾不可邀请其他来宾与你的组织协作。
    > [!IMPORTANT]
    > 目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。
 
要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

> [!NOTE]
> 还可管理可以来宾身份邀请哪些域加入你的租户。 请参阅[允许/阻止对 Office 365 组的来宾访问](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。

无需将用户来宾帐户手动添加到 Azure AD B2B 中，因为在你向 Teams 添加来宾时，该帐户将自动添加到目录中。

### <a name="licensing-for-guest-access"></a>来宾访问的许可
来宾访问许可是 Azure AD 许可的一部分。 来宾访问包含于所有 Office 365 商业高级版和 Office 365 企业版订阅之中。 有关许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。


> [!NOTE]
> 你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。 要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。 

## <a name="control-guest-access-in-teams"></a>控制 Teams 中的来宾访问

默认情况下，Teams 中的来宾访问处于关闭状态。 要启用来宾访问，请参阅[开启或关闭对 Microsoft Teams 的来宾访问](set-up-guests.md)。 


## <a name="control-guest-access-in-office-365-groups"></a>控制 Office 365 组中的来宾访问

从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 团队添加来宾用户和来宾访问。

1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 处使用 Office 365 全局管理员帐户进行登录。

2. 在左侧，依次选择“**设置**”和“**服务 &amp; 外接程序**”。

3. 选择“**Office 365 组**”。

     ![“设置”中“Office 365 组”的屏幕截图](media/authorize-guest-image2.png)
  
4. 在“Office 365 组”页面上，将开关设置为“**开**”或“**关**”，具体取决于你是否允许组织外部的团队和组所有者访问 Office 365 组。 单击或点击“**允许组所有者向组添加组织外部人员**”旁边的开关将其设置为“**开**”。 如果将此开关设置为“**开**”，则会看到另一个选项，它用于控制你是否允许组和团队所有者将组织外的人员添加到 Office 365 组和 Microsoft Teams。 如果你想让组和团队所有者添加来宾用户，请将此切换设置为“**开**”。 
 
   ![“Office 365 组”面板的屏幕截图，其中选项处于打开状态](media/authorize-guest-image3.png)

这些设置应用于租户级别，并控制 Office 365 组和 Teams 中的来宾体验。

要详细了解组中的来宾访问功能，例如来宾访问功能如何工作、如何管理来宾访问以及常见问题的解答，请参阅 [Office 365 组的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>控制对 SharePoint Online 和 OneDrive for Business 的来宾访问

Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。  

为了获得完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置进行配置：

- 在 SharePoint Online 中：选择“**现有来宾**”、“**新来宾和现有来宾**”或“**任何人**”。

    有关详细信息，请参阅[打开或关闭外部共享](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。

- 在 Office 365 组中：启用**允许组所有者将组织外部的人员添加到组**

    有关详细信息，请参阅上面的[控制 Office 365 组中的来宾访问](#control-guest-access-in-office-365-groups)。
  
这些设置应用于租户级别，并控制 SharePoint Online、OneDrive for Business、Office 365 组和 Teams 中的来宾体验。

你可以管理与 Teams 连接的团队网站的 SharePoint Online 外部用户设置。 要了解详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。

## <a name="external-access-federation-vs-guest-access"></a>外部访问（联合身份验证）与来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>相关主题

- [Microsoft 365 来宾共享设置参考](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
