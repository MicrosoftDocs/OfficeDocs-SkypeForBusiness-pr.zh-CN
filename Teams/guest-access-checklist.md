---
title: Microsoft Teams 来宾访问清单
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单可帮助 Microsoft 团队来宾 Access 中的来宾访问设置。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 404754c373d46b9b6e5578107415d61bbb87f97e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463465"
---
<a name="teams-guest-access-checklist"></a>团队来宾访问清单
==========================================

使用此清单可帮助您启用和配置中的 Microsoft 团队的来宾访问功能，根据组织的首选项。

## <a name="understand-the-limitations-for-guests"></a>了解来宾的限制

来宾体验设计具有限制。 请确保您了解来宾体验，以便不尝试修复内容不是问题。 例如，下面是功能的一些不可来宾中的 Microsoft 团队列表：

- OneDrive for Business
- 团队之外人员搜索
- 日历、 计划的会议或会议详细信息
- PSTN
- 组织结构图
- 创建或修改团队
- 浏览团队
- 将文件上载到个人到个人聊天

有关详细信息，请参阅[新增的来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。

### <a name="guest-access-vs-external-access-federation"></a>来宾访问与外部访问 （联合身份验证）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您来宾看到许可证错误

来宾访问中的 Microsoft 团队使用 Azure Active Directory 业务到企业 (B2B) 和其许可模型。 如果您看到许可错误，请务必阅读 B2B 许可指南以了解您的组织有以便用户能够邀请来宾到您的组织的许可要求。

要记住的几个事项：

- 为每个付费 Azure AD 许可证分配给用户，用户可以邀请外部用户宽限下的最多五个来宾用户。
- 来宾是组织外部的用户。 无法为来宾添加您的员工、 现场承包商、 现场代理，等等。 这同样适用于您子公司。
- 来宾许可证在内针对邀请的组织。 当计算所需的许可证数量，请考虑以下事项。
- 针对许可证计数针对您的组织是否受邀的来宾来自其他 Office 365 租户，或使用其个人电子邮件地址。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ 步骤 1： 在 Azure AD 企业到企业中配置设置

1. 登录到https://portal.azure.com。
2. 单击左侧窗格中的**Azure Active directory** 。
3. 在**管理**下单击**用户设置**。
4. 在**外部用户**，下单击**管理外部协作设置**。
5. 在**外部协作设置**页中，确保**成员可以邀请**设置为**是**。

      ![屏幕快照显示了 AAD 设置切换的示例。 ](media/guest-access-checklist-AADSettings1.png)

    若要支持来宾，**可以邀请成员**必须设置为**是**。 
   
> [!NOTE] 
> 如果设置为**否**的**成员可以邀请**，然后启用来宾访问 Office 365 组和 Microsoft 团队中的，管理员可以控制来宾邀请到您的目录。 来宾目录中后，他们可以通过属于团队所有者非管理员成员添加到团队。

有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。


## <a name="-step-2-configure-office-365-groups"></a>□ 步骤 2： 配置 Office 365 组

1. 在 Microsoft 365 管理中心，转到**设置** > **服务 & 加载** > **Office 365 组**。
2. 请确保**让外部组织的访问组内容的组成员**设置为**上**。 如果此设置处于关闭，来宾将无法访问任何组内容。
3. 请确保**让组添加到组组织外部的人员的所有者**设置为**上**。 如果此设置处于关闭，团队所有者将无法添加新的来宾。 至少，此设置必须登录到支持来宾访问权限。

     ![屏幕快照显示了 Office 365 组切换](media/guest-access-checklist-office365.png)

有关配置这些设置的详细说明，请参阅[管理 Office 365 组中的来宾访问](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和部分[中的 Microsoft 团队的授权来宾访问](Teams-dependencies.md)中的"Office 365 组"。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ 步骤 3： 启用租户级别的来宾访问

至少，您必须启用来宾访问的**Microsoft 团队管理中心**下的 Microsoft 团队。 

1. 在团队管理中心中选择**组织范围设置** > **来宾访问**。
2. 设置为**上**的**Microsoft 团队中的允许来宾访问**开关。

    ![屏幕快照显示了工作组设置切换的示例](media/set-up-guests-image1.png)

3. 在此同一页上，配置所需的任何其他来宾设置。
4. 单击“**保存**”。

有关详细说明，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。


## <a name="--step-4-configure-sharing-in-office-365"></a>□ 步骤 4： 配置 Office 365 中共享 

确保用户可以添加来宾。 下面是如何：

1. 在 Microsoft 365 管理中心，转到**设置** > **安全 & 隐私**。

     ![屏幕快照显示了服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. 在**共享**，选择**编辑**。

     ![屏幕快照显示了共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. 设置**让用户将添加到此组织的新来宾**为**上**，，然后单击**保存**。

     ![屏幕快照显示了共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> 此设置等同于在**用户设置**中的**成员可以邀请**设置 > Azure AD 中的**外部用户**。  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ 步骤 5： 验证在 SharePoint 中的共享设置

1. 登录 Office 365 管理中心。
2. 单击**管理中心**，然后选择**SharePoint**。
3. 在 SharePoint 管理中心中，选择**共享**。
4. 请确保选项*未*选中的**不允许共享您的组织外部**。
 
     ![屏幕快照显示了 Sparepoint 在线设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ 步骤 6： 启用渠道的特定设置 

中的团队应用程序，在各个团队级别配置来宾权限，以便来宾可以创建、 更新和删除通道。 除了 admins 团队所有者可以配置此设置。

![屏幕快照显示了工作组/通道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

有关详细信息，包括操作方法视频，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。


## <a name="troubleshooting"></a>故障排除

如果您遇到的 Microsoft 团队中添加来宾问题，请参阅[来宾访问疑难解答指南 》](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。


