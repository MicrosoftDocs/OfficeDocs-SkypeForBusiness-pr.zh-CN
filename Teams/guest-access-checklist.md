---
title: Microsoft Teams 来宾访问清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单可帮助设置 Microsoft 团队中的来宾访问。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 833d79d16365a1b90e8cd35e88e43468f0e25fa8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280922"
---
<a name="teams-guest-access-checklist"></a>团队来宾访问清单
==========================================

使用此清单可帮助你根据你的组织的首选项, 在 Microsoft 团队中启用和配置来宾访问功能。

## <a name="understand-the-limitations-for-guests"></a>了解对来宾的限制

来宾体验由设计限制。 请确保你了解来宾体验, 这样就不会尝试修复不存在问题的内容。 例如, 下面列出了 Microsoft 团队中的来宾无法使用的一些功能:

- OneDrive for Business
- 在团队外搜索的人员
- 日历、计划的会议或会议详细信息
- PSTN
- 组织结构图
- 创建或修订团队
- 浏览团队
- 将文件上传到人员间聊天
- 如果用户知道他们的完整电子邮件 ID, 则来宾仍可搜索和查找其团队外的用户。 为避免这种情况, IT 管理员可以使用具有[范围的目录搜索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)的模式, 这些模式能够将来宾限制在自己的虚拟 GAL 中。

有关更多详细信息, 请参阅[来宾体验](guest-experience.md)和[Office 365 组中的来宾访问](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。

### <a name="guest-access-vs-external-access-federation"></a>来宾访问与外部访问（联合身份验证）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您的客人看到许可证错误

Microsoft 团队中的来宾访问使用 Azure Active Directory 商业版 (B2B) 和其许可模型。 如果您看到授权错误, 请确保阅读 B2B 授权指南以了解您的组织拥有的授权要求, 以便用户能够邀请来宾加入您的组织。

需要注意的一些事项:

- 对于分配给用户的每个付费 Azure AD 许可证, 你的用户可以在外部用户津贴下邀请最多五个来宾用户。
- 来宾是您的组织外部的用户。 您的员工、现场承包商、现场工程师等不能添加为来宾。 这同样适用于您的会员。
- 来宾许可证按邀请的组织计入。 当你计算所需的许可证数量时, 请考虑此情况。
- 根据您的组织统计许可证, 无论受邀的来宾来自其他 Office 365 租户还是使用其个人电子邮件地址。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□步骤 1: 在 Azure AD 企业到企业中配置设置

1. 登录到https://portal.azure.com
2. 在左窗格中单击 " **Azure Active directory** "。
3. 在 "**管理**" 下, 单击 "**用户设置**"。
4. 在 "**外部用户**" 下, 单击 "**管理外部协作设置**"。
5. 在 "**外部协作设置**" 页面上, 确保 "**成员可邀请**" 设置为 **"是"**。

      ![屏幕截图显示 AAD 设置切换的示例。 ](media/guest-access-checklist-AADSettings1.png)

    若要支持来宾, "**成员可以邀请**" 必须设置为 **"是"**。 
   
> [!NOTE] 
> 如果您设置的**成员可以邀请**"**否**", 然后在 Office 365 组和 Microsoft 团队中启用来宾访问, 则管理员可以控制您的目录的来宾邀请。 来宾位于目录中后, 可通过非管理员成员的团队所有者将其添加到团队。

有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。


## <a name="-step-2-configure-office-365-groups"></a>□步骤 2: 配置 Office 365 组

1. 在 Microsoft 365 管理中心, 转到 "**设置** > **服务 &" 加载项** > **Office 365 组**。
2. 确保将 **"组织" 访问组内容外的组成员**设置为 **"开"**。 如果此设置处于关闭状态, 则来宾将无法访问任何组内容。
3. 确保**组所有者将组织外部的人员添加到 "组**" 设置为 **"开**"。 如果此设置处于关闭状态, 则团队所有者将无法添加新来宾。 此设置至少必须启用才能支持来宾访问。

     ![屏幕截图显示 Office 365 组的切换](media/guest-access-checklist-office365.png)

有关配置这些设置的详细说明, 请参阅在[Office 365 组中管理来宾访问](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和在[Microsoft 团队中授权来宾访问](Teams-dependencies.md)部分中的 "Office 365 组" 部分。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□步骤 3: 在租户级别启用来宾访问

至少, 你必须在**Microsoft 团队管理中心**下为 microsoft 团队启用来宾访问。 

1. 在 "团队管理中心" 中, 选择 "**组织范围设置** > "**来宾访问**。
2. 将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. 在此同一页面上, 配置所需的任何其他来宾设置。
4. 单击“**保存**”。

有关详细说明, 请参阅[打开或关闭对 Microsoft 团队的来宾访问](set-up-guests.md)。


## <a name="--step-4-configure-sharing-in-office-365"></a>□步骤 4: 在 Office 365 中配置共享 

请确保用户可以添加来宾。 操作方法如下:

1. 在 Microsoft 365 管理中心中, 转到 "**设置** > **安全 & 隐私**"。

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. 在 "**共享**" 中, 选择 "**编辑**"。

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. 设置 "**允许用户向此组织添加新来宾**", 然后单击 "**保存**"。 ****

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> 此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□步骤 5: 验证 SharePoint 中的共享设置

1. 登录到 Microsoft 365 管理中心。
2. 单击 "**管理中心**", 然后选择 " **SharePoint**"。
3. 在 SharePoint 管理中心中, 选择 "**共享**"。
4. 请确保*未*选中 "**不允许在组织外部共享**" 选项。
 
     ![屏幕截图显示 SparePoint 联机设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□步骤 6: 启用频道的特定设置 

在 "团队" 应用程序中, 在单个团队级别配置来宾权限, 以便来宾可以创建、更新和删除频道。 除了管理员, 团队所有者还可以配置此设置。

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

有关详细信息, 包括操作方法视频, 请参阅[Microsoft 团队中的来宾访问](guest-access.md)。


## <a name="troubleshooting"></a>疑难解答

如果您在 Microsoft 团队中添加来宾时遇到问题, 请参阅[来宾 Access 疑难解答指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。


