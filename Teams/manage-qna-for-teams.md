---
title: 在 Teams 会议中管理 Q&A
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: 了解 IT 管理员如何在 Teams Q&A 中设置、使用和管理 Q&A，以采用结构化方法收集问题、组织讨论、删除单个消息、使用可用语言以及了解数据生命周期以及数据保留和删除策略。
ms.openlocfilehash: 17de45280809ae6c5fffdce64067fe97020965ec
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494830"
---
# <a name="manage-qa-in-teams-meetings"></a>在 Teams 会议中管理 Q&A

Q&A 是一种集成会议体验，让参与者有机会正式提问和回答问题，并参与结构化讨论。 此体验是与超过 10 名参与者的会议的最佳做法。

本文介绍如何管理 Q&A 和用户级策略，这些策略决定了组织者是否可以在会议中启用 Teams Q&A。

> [!NOTE]
> 此功能目前为专用预览版，不可公开访问。 如果要参与专用预览计划，请在此处注册 [。](https://m365crmedu.powerappsportals.com/LMSSignup/)


## <a name="prerequisites"></a>先决条件

- 验证你是否尚未阻止对 [Yammer IP 和 URL 的访问。](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- 若要允许组织中的用户向 Teams 会议添加 Q&A，需要确认已在 Azure Active Directory 中启用了 Office 365 Yammer 服务的登录。 按照以下步骤确认已启用登录：
  - 转到 **Azure AD 管理中心** > **“所有服务** > **企业应用程序** > **Office 365 Yammer** > **属性**。
  - 对于 **“为用户启用登录？** ”选项，请根据需要选择 **“是** ”。

## <a name="who-can-use-qa"></a>谁可以使用 Q&A

Q&A 可由以下用户类型使用：

- 常规用户 - 租户中具有 Microsoft 365 凭据的用户。
- 联合用户 - 具有 Microsoft 365 凭据的用户到其他租户。
- 来宾用户 - 添加到 Microsoft Teams、SharePoint 或 Azure Active Directory 的任何来宾。

> [!NOTE]
> Q&A 目前不支持匿名用户。

当管理员启用 Q&A 时，具有组织者角色的用户可以在创建或更新会议时打开 Q&A。 通过 Teams 和 Outlook 会议选项，组织者还可以从之前添加的会议中删除 Q&A，以阻止与会者使用该功能。

## <a name="use-the-teams-admin-center-to-manage-qa"></a>使用 Teams 管理中心管理 Q&A

> [!NOTE]
> 在管理中心管理 Q&A 在公共预览版中不可用。 使用 PowerShell 为用户设置和管理 Q&A。

组织可能要求限制哪些组织者可以打开 Q&A。 可以使用 Teams 管理中心来管理哪些组织者可以在大型会议中打开 Q&A。
按照以下步骤控制哪些组织者可以使用 Q&A：

1. 在 Teams 管理中心，转到 **会议** > [**会议策略**](/meeting-policies-participants-and-guests)
2. 选择现有策略或创建一个新策略，并为其命名，例如“这些组织者没有 Q&A”
3. 滚动到名为 **“参与者&来宾”** 的部分，选择禁用 **“问题&回答体验”** 设置，并保存策略
4. 将策略分配给要阻止设置 Q&A 的特定 M365 组、最终用户或订阅

## <a name="use-powershell-to-manage-qa"></a>使用 PowerShell 管理 Q&A

组织可能要求限制哪些组织者可以打开 Q&A。 可以使用 PowerShell 管理哪些组织者可以在大型会议中打开 Q&A。

启用 Q&A 的示例 PowerShell 命令：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>在 Teams 中从 Q&A 中删除单个消息

若要删除 Q&A 应用程序中发布的问题或答案，请执行以下步骤：

1. 以全局管理员身份登录 Exchange 管理员中心。
2. 转到 **收件人** > **邮箱** 并按姓名搜索组织会议的用户。
3. 选择会议组织者，然后单击 **“管理邮箱委派**”。 在 **“读取和管理** ”部分中，选择 **“编辑** > **添加权限**”。
4. 将自己添加为会议组织者的代理人，然后选择“保存”。
5. 在Outlook Web App (而不是桌面) 中打开Outlook 日历，然后选择 **“添加日历**”，然后 **从目录中添加**。
6. 搜索会议组织者并将其日历添加到 **“我的日历**”。 所选用户的会议现在将显示在日历上。
7. 在日历中，找到要为其删除内容的会议，打开会议记录，然后选择 **与参与者聊天**。 选择与参与者聊天将在 Teams 中打开会议聊天。
8. 导航到 Teams 应用栏中的 Q&A 应用程序。
9. 查找要删除的任何问题或答案，然后选择“删除”。
10. 删除完内容后，返回 Exchange 管理员中心，并删除自己作为会议组织者的代理人。

> [!NOTE]
> 如果在删除答案之前删除问题，则该问题的第一个答案将成为问题。
>
> 若要避免这种情况，请按以下顺序执行以下步骤：
>
> 1. 确定要删除的问题
> 2. 删除问题的答案
> 3. 删除问题

## <a name="available-languages-for-yammer-versus-teams"></a>Yammer 与 Teams 的可用语言

Q&A 将默认为 Teams 的用户语言。 当 Teams 与 Yammer 可用的语言存在差异时，将发生以下语言默认值：

- 最近的主语言 - Yammer 将默认为最近的主语言（如果可用）。 例如，Yammer 不提供法语加拿大 (fr-CA) 版本，因此它将以法语 (fr-FR) 显示内容。
- 不受支持的语言 - 如果 Yammer 根本不提供该语言，则 Yammer 将默认为美国英语 (en-US) 。

## <a name="ediscovery"></a>电子数据展示

适用于 Q&A 的电子数据展示将与任何其他 Yammer 内容的电子数据展示相同。

- 如果在租户的 Teams 应用程序中使用 Teams Q&A，则无论 Yammer 网络的配置或存在，此内容都将在电子数据展示中提供。 若要将电子数据展示用于标准 Yammer 内容，Yammer 网络需要处于 [本机模式](/yammer/configure-your-yammer-network/overview-native-mode)。
- 执行电子数据展示时，可以确定消息是在 Yammer 中生成的还是通过 Teams 中的 Q&A 生成的。 在“文件元数据”部分中，可以在“项目类”字段中找到该信息。
- 如果你的组织使用由 Yammer 支持的 Teams Q&A，则 Q&A 生成的内容被视为 Yammer 内容，并且可以发现。 有关 Microsoft 365 应用中的电子数据展示的详细信息，请参阅 [Microsoft 365 中的电子数据展示解决方案。](/microsoft-365/compliance/ediscovery)

## <a name="data-storage"></a>数据存储

问&作为会议一部分创建的消息存储为 Yammer 消息。 这些消息存储在 Yammer 中，并引入电子数据展示。
文件始终存储在 SharePoint 中，它处理所有数据静态策略和位置。

以下指南介绍了如何存储消息传送数据：

- 问&可通过电子数据展示搜索内容，并在用户级别Advanced eDiscovery。
- 包含消息内容) 的消息数据 (默认情况下将存储在北美或欧盟 (，具体取决于客户的 Yammer 网络位置) 。
- 对于没有现有 Yammer 网络的租户，将在 美国 Yammer 区域中创建 Q&A Yammer 网络。 组织针对 Q&A 的消息将始终存储在美国。
- 与 OneNote 选项卡类似，从会议中删除 Q&A 不会删除会议数据。 从会议中删除 Q&A 只会删除对会议中数据的访问权限。 如果重新添加 Q&A 选项卡，则会再次看到所有会议对话。

## <a name="gdpr-for-qa-in-teams"></a>Teams 中 Q&A 的 GDPR

通过Microsoft 365 管理中心完成数据主体请求后，它会自动从 Q&A 中的所有内容中删除用户的联系信息。

## <a name="data-lifecycle-for-qa-in-teams"></a>Teams 中 Q&A 的数据生命周期

Teams 中 Q&A 生成的数据的生命周期取决于合规中心中的 Yammer 数据保留设置。 如果硬删除会议中通过 Azure Active Directory 收到其基板分片中 Q&A 消息副本的所有用户，Yammer 将在用户删除后 30 天内删除其 Q&A 内容的副本。

## <a name="retention-and-deletion"></a>保留和删除

保留内容遵循为 Yammer 设置的保留策略 - 无论是否为 Yammer 和 Teams 设置了不同的策略。

> [!NOTE]
> 如果 Yammer 网络不在本机模式下，则此处创建的策略将仅适用于 Teams Q&A 数据。 在本机模式下，所有 Yammer 用户都在 Azure Active Directory (Azure AD) 中，所有组都是 Microsoft 365 组，所有文件都存储在 SharePoint Online 中。

## <a name="faq"></a>常见问题

**问：如何实现导出 Q&A 内容？**

**答：** Q&A 内容存储在Microsoft 365 合规中心中并通过电子数据展示访问。 将来的迭代将包括会议重点报告和会议组织者的导出功能。

**问：Q&A 是否支持 Microsoft 365 多地理位置功能？**

**答：** Q&A 当前不支持 Microsoft 365 多地理位置功能。 问&默认情况下，数据将存储在北美或欧盟 (取决于客户的 Yammer 网络位置) 。

**问：在哪里可以详细了解结构化会议？**

**答：** 遵循以下 [最佳做法](/MicrosoftTeams/quick-start-meetings-live-events) ，在 Microsoft Teams 中成功托管大型会议。

**问：通过 Teams 应用商店设置 Q&A 与使用会议选项有何区别？**

**答：** 尽管与会者和审阅者用户体验没有区别，但今后 Q&A 必须仅使用会议选项进行设置。 Teams 应用商店中的 Q&A 应用将在 2022 年底之前弃用，因此最好使用会议选项在会议中设置 Q&A。
