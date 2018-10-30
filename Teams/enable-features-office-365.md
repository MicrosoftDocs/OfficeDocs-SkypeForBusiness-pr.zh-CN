---
title: 管理 Office 365 组织中的 Microsoft 团队功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何启用或禁用 Office 365 组织，包括选项卡、 连接器、 自动程序或这三个任意组合中的 Microsoft 团队应用程序。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f78876064ae50221562bd42b334545f627a02fb
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842073"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>管理 Office 365 组织中的 Microsoft 团队功能

所有团队设置很快将都迁移到新的 Microsoft 团队和 Skype 的业务 Admin Center。 在 Office 365 管理中心中托管的唯一团队功能是应用程序。 

除非另行说明，否则选项的默认值是**在上**。

## <a name="office-365-tenant-wide-settings"></a>Office 365 租户范围的设置 

在**租户范围的设置**，可以打开或关闭应用程序。

编辑团队**租户范围的设置**，请转到 Microsoft 团队和 Skype 的业务管理中心中，并选择**旧门户**。 选择 **“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。 如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作： 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>应用

应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。 可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。 这些策略允许您指定的应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。 

在 **“应用”** 下，可以为贵组织配置以下设置： 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **在 Microsoft Teams 中允许外部应用：** 如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **默认启用新的外部应用：** 打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。 如果你希望控制新应用，请关闭此开关。 当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。 

- **允许 sideloading 的外部应用程序**： 启用此开关后，用户可以安装和启用自定义自动程序和选项卡。 

要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。 

## <a name="teams-org-wide-settings"></a>团队组织范围的设置

您可以控制组织范围内用户设置中的 Microsoft 团队业务管理中心的 Skype。 若要编辑组织范围的设置，请转到的业务管理中心中，Microsoft Skype，然后选择**组织范围的设置**。 您可以配置以下设置。

### <a name="external-access"></a>外部访问

**外部访问**允许您的团队和 Skype 业务用户与组织外部的用户进行通信。 若要配置外部访问，请转到[让您的团队用户聊天并与其他团队组织中的用户进行通信](let-your-teams-users-communicate-with-other-people.md)。

### <a name="guest-access"></a>来宾访问

**来宾访问**中的 Microsoft 团队允许在与组织外部的人员协作通过授予其访问权限的团队和频道贵组织中的团队。 具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以参与作为来宾团队中具有到团队聊天、 会议和文件的完全访问权限。 有关详细信息，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。

### <a name="teams-settings"></a>团队设置

在**工作组设置**，您可以设置电子邮件集成，云存储选项 Skype 业务互操作性和设备。

#### <a name="email-integration"></a>电子邮件集成

开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。 用户可以对属于其所属团队的任何频道执行此操作。 用户还可以向任何已添加为工作组成员开启连接器团队中的通道发送电子邮件。 若要启用电子邮件集成，请确保**允许用户发送到通道电子邮件地址的电子邮件****上**。 

#### <a name="files"></a>文件

此处可以在打开或关闭文件共享和云文件存储选项。 

用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。 当前，团队中的云存储选项包括 ShareFile、 收存箱、 框中，和 Google 驱动器。 可打开贵组织要使用的云存储提供商对应的开关。

#### <a name="organization"></a>组织

此处可以打开**组织**选项卡，其中显示用户的组织详细组织结构图。 有关详细信息，请参阅[使用团队中的组织选项卡](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)。

#### <a name="skype-for-business-interop"></a>业务互操作的的 Skype

使用此设置可允许与 Skype 的业务用户的工作组用户聊天。 有关团队之间 for Business 的 Skype 的互操作性的详细信息，请转到[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

#### <a name="devices"></a>设备

这些设置控制参加会议的 Microsoft 团队的图面集线器设备资源帐户行为。 使用这些设置来配置身份验证要求、 需要内容的 PIN，然后打开面集线器资源帐户发送邮件。

- **需要第二窗体的身份验证才能访问会议内容**– 选择用户可以输入内容时的访问级别的 PIN。
- **设置内容 PIN** – 要求用户输入此 PIN，以防止未经授权的访问文档。 这样可以防止未经授权的用户加入即将召开的会议和浏览附件。
- **资源帐户可以发送邮件**– 启用**此设置**以允许从面集线器资源帐户发送邮件。

#### <a name="search"></a>搜索

Microsoft 团队作用域的目录搜索使用 Exchange 通讯簿策略 (APB) 以允许组织创建虚拟边界的控件如何查找用户并与其他组织中的用户进行通信。 您可能需要在以下情况下使用作用域的目录搜索：

- 您的组织具有多个公司内您希望用于保存单独其租户。 
- 您的学校希望限制教职员工学生之间的聊天。 

切换**上**打开作用域的目录搜索此设置。

### <a name="teams-upgrade"></a>团队升级

您可以使用这些设置配置如何您的用户将从升级 for Business 的 Skype 到 Microsoft 团队。 

#### <a name="coexistence-mode"></a>共存模式
您可以指定共存模式：**仅团队**、**群岛**（团队和共存的业务将 Skype） 或**仅业务的 Skype**。 您选择的共存模式确定传入呼叫和聊天和启动聊天和呼叫或安排会议的用户使用的应用程序的路由。 有关共存模式的详细信息，请转到[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

#### <a name="app-preferences"></a>应用程序首选项

您可以在此处选择应用程序的用户将用来加入 for Business 的 Skype 会议 (适用于商务或[Skype 会议应用程序](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)的 Skype)。 此设置不依赖于在共存模式设置。


