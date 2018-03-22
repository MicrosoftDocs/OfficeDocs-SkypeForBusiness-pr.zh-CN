---
title: Microsoft 的团队来宾访问清单
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: 使用此检查表来帮助设置在 Microsoft 小组来宾访问来宾访问权限。
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a>团队来宾访问清单
==========================================

使用此检查表可帮助您启用和配置 Microsoft 小组在来宾访问功能，根据您的组织的首选项。




## <a name="--enable-guest-access-at-the-tenant-level"></a>在组织级别 □ 启用来宾访问

至少，您必须打开所有用户的许可证类型**来宾**Microsoft 小组。 有关详细说明，请参阅[启用或禁用来宾访问 Microsoft 小组](set-up-guests.md)。

![屏幕抓图显示了示例团队设置切换](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a>□ 启用特定频道设置 
在团队的应用程序，各个团队级别配置来宾权限以便客人可以创建、 更新和删除频道。 除了管理员、 团队所有者可以配置该设置。

![屏幕抓图显示了示例团队/通道设置切换](media/guest-access-checklist-TeamsSettings2.png)


有关详细信息，包括操作方法视频，请参阅[Microsoft 小组中的来宾访问](guest-access.md)。



## <a name="--configure-sharing-in-office-365"></a>□ 配置 Office 365 中共享 

□ 请确保用户可以添加的客人。 下面是如何：

1. 在 Office 365 管理中心，转到**设置** > **安全和保密**。
![屏幕抓图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. 在**共享**，选择**编辑**。![屏幕抓图显示共享设置编辑按钮的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. 设置**允许用户添加为该组织新的来宾**为**上**，，然后单击**保存**。![屏幕抓图显示了一种共享设置切换](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> 此设置相当于在用户设置中的**成员可以邀请**设置 > Azure AD 中的外部用户。  




## <a name="-configure-office-365-groups"></a>□ 配置 Office 365 组

在 Office 365 管理中心，转到**设置** > **服务和加载** > **Office 365 组**。

请确保**让组织访问组内容之外的组成员**被设置为**On**。 如果此设置处于禁用状态，来宾不能访问组中的任何内容。

请确保**让组添加到组组织外人员的所有者**设置为**上**。 如果关闭了此设置，则团队所有者将无法添加新的客人。 （但是，如果管理员已经到 Azure AD 添加来宾用户，然后团队所有者能够将该用户添加到团队。）至少，此设置必须为"on"支持来宾访问。

有关配置这些设置的详细说明，请参阅[Microsoft 小组授权来宾访问](Teams-dependencies.md)和[允许/阻止来宾访问 Office 365 组](https://go.microsoft.com/fwlink/?linkid=869658)中的"Office 365 组"一节。
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>□ 在 Azure 广告企业到企业 (B2B) 中的配置设置
1. 登录到 https://portal.azure.com。
2. 在左窗格中单击**Azure 活动目录**。
3. 在**管理**下单击**用户设置**。
4. 在**外部用户**，请确保**可以邀请成员**设置为**是**。![屏幕抓图显示了 AAD 设置切换的示例。 ](media/guest-access-checklist-AADSettings1.png)

    

► 最少支持的客人，**可以邀请成员**必须设置为**是**。

> > [!NOTE]
> 如果设置为**否**的**成员可以邀请**并启用 guest 访问 Office 365 组和 Microsoft 小组中的，管理员可以控制来宾邀请到您的目录。 客人在目录中后，它们可以由非管理员成员 （团队所有者） 添加到团队。


有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。







## <a name="-verify-sharing-setting-in-sharepoint"></a>□ 在 SharePoint 中验证共享设置
1. 登录 Office 365 管理中心。
2. 单击**管理中心**，然后选择**SharePoint**。
3. 在 SharePoint 管理中心中，选择**共享**。
4. 请确保选择*未*选中的**不允许在您的组织之外共享**。![的屏幕快照演示的 Sparepoint 在线设置切换示例。 ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>□ 验证帐户许可证和类型

- **帐户工作组授权**： 植根于真实的用户帐户在某些其他 Office 365 租户"Guest"帐户，真实的用户帐户必须授权工作组有关"来宾"。 
- **帐户必须是 Office 365 学校或者工作帐户或 MSA 帐户**： 目前，可以作为访客用户添加具有对应于 Azure Active Directory、 Office 365 的工作或学校的帐户，或者 Microsoft 帐户 (MSA) 的电子邮件地址的用户。 
 
## <a name="-configure-environment"></a>□ 配置环境


客人需要使用多因素身份验证 (MFA) 承载租户的要求。
有关详细信息，请参阅[标识模型和 Microsoft 小组中的身份验证](identify-models-authentication.md)。

## <a name="-understand-limitations-for-guests"></a>□ 客人了解限制

访客体验设计上有一定局限性。 确保您了解访客的经验，所以不要尝试修复不是问题。
例如，下面是功能的一些来宾在 Microsoft 小组中没有的列表：

- OneDrive 为公司的
- 在团队之外的人搜索
- 日历、 计划的会议或会议的详细信息
- PSTN
- 组织结构图
- 创建或修改团队
- 浏览一个团队
- 将文件上载到人际交谈

有关详细信息，请参阅[何谓来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。




## <a name="troubleshooting"></a>疑难解答

如果必须添加在 Microsoft 团队客人的问题，请参阅[来宾访问故障排除指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。


