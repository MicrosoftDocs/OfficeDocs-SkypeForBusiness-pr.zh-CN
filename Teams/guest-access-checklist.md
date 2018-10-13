---
title: Microsoft 团队来宾访问清单
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: 使用此清单可帮助 Microsoft 团队来宾 Access 中的来宾访问设置。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58dd3bb4e0f870cfcfff0f1297acdab7a82eb4a9
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546682"
---
<a name="teams-guest-access-checklist"></a>团队来宾访问清单
==========================================

使用此清单可帮助您启用和配置中的 Microsoft 团队的来宾访问功能，根据组织的首选项。




## <a name="--enable-guest-access-at-the-tenant-level"></a>在租户级别的 □ 启用来宾访问

转到团队和 Skype 的业务管理中心中，通过https://admin.teams.microsoft.com。 从此处，选择组织范围设置，和 selec 来宾访问权限选项卡最后，在此选项卡上，选择允许 Microsoft 团队中的来宾访问为启用。 

## <a name="need-a-new-screenshot-for-new-admin-center-enablement"></a>需要新管理中心启用新的屏幕截图。 

## <a name="-enable-specific-settings-for-channels"></a>□ 启用渠道的特定设置 
中的团队应用程序，在各个团队级别配置来宾权限，以便来宾可以创建、 更新和删除通道。 除了 admins 团队所有者可以配置此设置。

![屏幕快照显示了工作组/通道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)


有关详细信息，包括操作方法视频，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。



## <a name="--configure-sharing-in-office-365"></a>□ 配置 Office 365 中共享 

□ 确保用户可以添加来宾。 下面是如何：

1. 在 Office 365 管理中心，转到**设置** > **安全性和隐私**。
![屏幕快照显示了服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. 在**共享**，选择**编辑**。![屏幕快照显示了共享设置编辑按钮的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. 设置**让用户将添加到此组织的新来宾**为**上**，，然后单击**保存**。![屏幕快照显示了共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> 此设置等同于在用户设置中的**成员可以邀请**设置 > Azure AD 中的外部用户。  




## <a name="-configure-office-365-groups"></a>□ 配置 Office 365 组

在 Office 365 管理中心，转到**设置** > **服务和加载项** > **Office 365 组**。

请确保**让外部组织的访问组内容的组成员**设置为**上**。 如果此设置处于关闭，来宾将无法访问任何组内容。

请确保**让组添加到组组织外部的人员的所有者**设置为**上**。 如果此设置处于关闭，团队所有者将无法添加新的来宾。 至少，此设置必须为"开"以支持来宾访问。

有关配置这些设置的详细说明，请参阅部分[中的 Microsoft 团队的授权来宾访问](Teams-dependencies.md)和[允许/阻止来宾访问到 Office 365 组](https://go.microsoft.com/fwlink/?linkid=869658)中的"Office 365 组"。
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>□ Azure AD 业务对企业 (B2B) 中的配置设置
1. 登录到https://portal.azure.com。
2. 单击左侧窗格中的**Azure Active directory** 。
3. 在**管理**下单击**用户设置**。
4. 在**外部用户**，下单击**管理外部协作设置**
5. 在**外部协作设置**页中，确保**成员可以邀请**设置为**是**。![屏幕快照显示了 AAD 设置切换的示例。 ](media/guest-access-checklist-AADSettings1.png)

    

至少支持来宾 ►，**可以邀请成员**必须设置为**是**。

> > [!NOTE]
> > 如果设置为**否**的**成员可以邀请**并启用来宾访问 Office 365 组和 Microsoft 团队中的，管理员可以控制来宾邀请到您的目录。 来宾目录中后，他们可以由非管理员成员 （团队所有者） 添加到团队。


有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。







## <a name="-verify-sharing-setting-in-sharepoint"></a>在 SharePoint 中的 □ 验证共享设置
1. 登录 Office 365 管理中心。
2. 单击**管理中心**，然后选择**SharePoint**。
3. 在 SharePoint 管理中心中，选择**共享**。
4. 请确保选项*未*选中的**不允许共享您的组织外部**。![屏幕快照显示了 Sparepoint 在线设置切换的示例。 ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>□ 验证帐户许可证和类型

- **帐户许可团队**： 根中一些其他 Office 365 租户中的实际用户帐户是"来宾"帐户，真实的用户帐户必须团队获得许可"来宾"。 
- **帐户必须是 Office 365 学校或工作帐户或 MSA 帐户**： 目前，可以作为来宾用户添加具有与 Azure Active Directory、 Office 365 工作或学校帐户或 Microsoft 帐户 (MSA) 对应的电子邮件地址的用户。 
 
## <a name="-configure-environment"></a>□ 配置环境


如果宿主租户需要使用多因素身份验证 (MFA) 所需来宾。
有关详细信息，请参阅[标识模型和 Microsoft 团队中的身份验证](identify-models-authentication.md)。

## <a name="-understand-limitations-for-guests"></a>来宾 □ 了解限制

来宾体验设计具有限制。 请确保您了解来宾体验，以便不尝试修复内容不是问题。
例如，下面是功能的一些不可来宾中的 Microsoft 团队列表：

- OneDrive for Business
- 团队之外人员搜索
- 日历、 计划的会议或会议详细信息
- PSTN
- 组织结构图
- 创建或修改团队
- 浏览团队
- 将文件上载到个人到个人聊天

有关详细信息，请参阅[新增的来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。




## <a name="troubleshooting"></a>疑难解答

如果您遇到的 Microsoft 团队中添加来宾问题，请参阅[来宾访问疑难解答指南 》](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。


