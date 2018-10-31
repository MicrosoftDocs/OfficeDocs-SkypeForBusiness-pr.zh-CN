---
title: 在 Microsoft Teams 中授权来宾访问
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4fe71b4126a5fb9024de78b696383c0e2f65307
ms.sourcegitcommit: 360b4507c89255b61ee7204ee077200c44961f3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25846428"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中授权来宾访问
===========================================

为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。 所有这些授权级别都适用于你的 Office 365 租户。 每个授权级别按如下所示控制来宾体验：
- **Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。 控制目录、租户和应用程序级别的来宾体验。 
- **Microsoft Teams**：仅控制 Microsoft Teams。 
- **Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。
- **SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。

这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。 例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，只需在 Microsoft Teams 中关闭来宾访问即可。 其他示例：你可以在 AAD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。 可能你不使用 Office 365 组。 SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。 

> [!NOTE]
> 来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。 

  下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。


![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a>Azure Active Directory

有了 Azure AD 企业到企业 (B2B) 协作，向潜在来宾用户发送邀请的操作将不局限于租户管理员。 你可以使用策略将发送邀请的任务委派给角色允许其发送邀请的用户。

用于邀请的设置在租户级别应用，并在目录、租户和应用程序级别控制来宾体验。 至少支持来宾**成员可以邀请**必须设置为**是**。


![Azure Active Directory 门户中用户设置的屏幕截图。](media/teams_dependencies_image2.png)

Azure AD 包括以下设置来配置外部用户：
- **来宾用户权限被限制**:**是**意味着来宾不具有某些目录任务权限，如枚举用户、 组或其他目录资源。 此外，来宾无法分配给您的目录中的管理角色。 携带**无**意味着具有对目录数据的正则用户在您的目录中具有相同的访问。
- **管理员和来宾邀请者角色中的用户可以邀请**:**是**意味着管理员和"来宾邀请者"角色中的用户将能够邀请到租户的来宾。 **无**意味着管理员和用户不能邀请到租户的来宾。
- **成员可以邀请**:**是**意味着您的目录的非管理员成员可以邀请来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。 到您的目录携带**无**意味着只有管理员可以邀请。
- **来宾可以邀请**:**是**意味着，您的目录中的来宾本身也可以邀请其他来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。 携带**无**方法不能邀请其他来宾与您的组织进行协作。
 


> [!NOTE]
> 您还可以管理哪些域可以作为来宾邀请到您的租户。 请参阅[Office 365 组允许/阻止来宾访问](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。 

## <a name="microsoft-teams"></a>Microsoft Teams
在 Microsoft Teams 中，你可以控制为组织启用还是禁用来宾体验。 该设置在默认情况下禁用，仅在租户级别应用于 Microsoft Teams。



你可以从 Office 365 管理中心管理 Microsoft Teams 来宾访问设置。 有关更多信息，请参阅[开启或关闭 Microsoft Teams 的来宾访问](set-up-guests.md)。 


## <a name="office-365-groups"></a>Office 365 组

从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 添加来宾用户和来宾访问。

1. 使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。
    
  
2. 在导航菜单中，依次选择 **“设置”** 和 **“服务&amp;和外接程序”**。
    
  
3. 选择 **“Office 365 组”**。
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. 在“Office 365 组”页面上，将切换设置为 **“开启”** 或 **“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。 单击或点击 **“允许组所有者将组织外部的人员添加到组”** 旁边的切换将其设置为 **“开启”**。 如果将此切换设置为“开启”，则会看到另一个选项，用于控制你是否让组和团队所有者将组织外的人员添加到 Office 365 组和 Microsoft Teams。 如果你想让组和团队所有者添加来宾用户，请将此切换设置为“开启”。 
 
   ![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




上述设置在租户级别应用，并控制 Office 365 组和 Microsoft Teams 中的来宾体验。


## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和 OneDrive for Business

Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。  
  
    
    
为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择 **“开启”**：
  
    
    

- 在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**
    
    有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://docs.microsoft.com/sharepoint/external-sharing-overview)。
    
  
- 在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**
    
    有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。
  

上述设置在租户级别应用，并控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。


你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。 有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。
