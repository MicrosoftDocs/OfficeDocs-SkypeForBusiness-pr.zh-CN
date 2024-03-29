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
audience: Admin
appliesto:
- Microsoft Teams
description: 了解 IT 管理员如何在 Teams Q&A 中设置、使用和管理 Q&A，以便采用结构化方法收集问题、组织讨论、删除单个消息、使用可用语言以及了解数据生命周期以及数据保留和删除策略。
ms.openlocfilehash: 3d85dbe4c9035a9de0ccb47557735bb797bdf244
ms.sourcegitcommit: 94e3f5e8dcfe8b3098ed8de2e4397e2338038f03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2022
ms.locfileid: "69177718"
---
# <a name="manage-qa-in-teams-meetings"></a>在 Teams 会议中管理 Q&A

Q&A 允许演示者回答与会者的问题并实时回答。 此功能最适合大型结构化会议，例如市政厅、网络研讨会、全手和培训。

本文介绍如何管理 Q&A 和用户级策略，这些策略指示组织者是否可以在其会议中启用 Teams Q&A。

## <a name="prerequisites"></a>先决条件

- 验证是否未阻止访问 [Yammer 的 IP 和 URL。](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- 若要允许组织中的用户向 Teams 会议添加 Q&A，需要在 Azure Active Directory 中确认已启用 Office 365 Yammer 服务的登录。 按照以下步骤确认已启用登录：
  - 转到 **Azure AD 管理中心** > **“所有服务** > **企业应用程序** > **Office 365 Yammer** > **属性**”。
  - 对于 **“允许用户登录？”** 选项，选择“ **是** ”（如有必要）。
- 验证是否未在 Teams 应用中阻止 Q&A (Native) [应用](/MicrosoftTeams/manage-apps)

## <a name="who-can-use-qa"></a>谁可以使用 Q&A

Q&A 可由以下用户类型使用：

- 普通用户 - 租户中具有Microsoft 365 凭据的用户。
- 联合用户 - 具有不同租户Microsoft 365 凭据的用户。
- 来宾用户 - 添加到 Microsoft Teams、SharePoint 或 Azure Active Directory 的任何来宾。

> [!NOTE]
> Q&A 在 GCC 中不可用。

当管理员启用 Q&A 时，具有 [组织者角色](https://aka.ms/GetQnA) 的用户可以在创建或更新会议时打开 Q&A。 通过 Teams 和 Outlook 会议选项，组织者还可以从之前添加的会议中删除 Q&A，以阻止与会者使用该功能。
> [!NOTE]
> Q&A 将不适用于仅查看已超过会议容量加入的与会者。

## <a name="use-the-teams-admin-center-to-manage-qa"></a>使用 Teams 管理中心管理 Q&A

组织可能要求限制哪些组织者可以启用 Q&A。 可以使用 Teams 管理中心来管理哪些组织者可以在大型会议中打开 Q&A。
按照以下步骤控制哪些组织者可以使用 Q&A：

1. 在 Teams 管理中心，转到 **“会议策略** > [**”**](/meeting-policies-participants-and-guests)
2. 选择现有策略或创建新策略，并为其命名，例如“对于这些组织者，没有 Q&A”
3. 滚动到名为 **“参与者&来宾”** 部分，为 **“问题&答案体验”** 设置选择禁用，然后保存策略
4. 将策略分配给要阻止设置 Q&A 的特定 M365 组、最终用户或订阅

## <a name="use-powershell-to-manage-qa"></a>使用 PowerShell 管理 Q&A

组织可能要求限制哪些组织者可以启用 Q&A。 可以使用 PowerShell 来管理哪些组织者可以在大型会议中打开 Q&A。

启用 Q&A 的示例 PowerShell 命令：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>在 Teams 中从 Q&A 中删除单个邮件

若要删除 Q&A 应用程序中发布的问题或答案，请执行以下步骤：

1. 以全局管理员身份登录到 Exchange 管理员中心。
2. 转到 **“收件人** > **邮箱”** ，并按名称搜索组织会议的用户。
3. 选择会议组织者，然后单击“ **管理邮箱委派**”。 在 **“读取和管理** ”部分中，选择 **“编辑** > **添加权限**”。
4. 将自己添加为会议组织者的代理人，然后选择“保存”。
5. 在非桌面) Outlook Web App (打开Outlook 日历，然后选择“**添加日历**”，然后选择“**从目录添加**”。
6. 搜索会议组织者并将其日历添加到 **“我的日历**”。 所选用户的会议现在将显示在日历上。
7. 在日历中，找到要删除其内容的会议，打开会议记录，然后选择“ **与参与者聊天**”。 选择“与参与者聊天”将在 Teams 中打开会议聊天。
8. 导航到 Teams 应用栏中的 Q&A 应用程序。
9. 找到要删除的任何问题或解答，然后选择“删除”。
10. 删除完内容后，返回到 Exchange 管理员中心，并删除自己作为会议组织者的代理人。

> [!NOTE]
> 如果在删除答案之前删除问题，则问题的第一个答案将成为问题。
>
> 若要避免这种情况，请按顺序执行以下步骤：
>
> 1. 确定要删除的问题
> 2. 删除问题的答案
> 3. 删除问题

## <a name="available-languages-for-yammer-versus-teams"></a>Yammer 与 Teams 的可用语言

Q&A 默认为 Teams 用户的语言。 当 Teams 与 Yammer 可用的语言存在差异时，将出现以下语言默认值：

- 最近的主要语言 - Yammer 将默认为最近的主要语言（如果可用）。 例如，Yammer 不提供法语加拿大 (fr-CA) 版本，因此它将改为使用法语 (fr-FR) 显示内容。
- 不支持的语言 - 如果 Yammer 根本不提供语言，Yammer 将默认为美国英语 (en-US) 。

## <a name="ediscovery"></a>电子数据展示

Q&A 的电子数据展示与任何其他 Yammer 内容的电子数据展示相同。

- 如果在租户的 Teams 应用程序中使用 Teams Q&A，则无论 Yammer 网络的配置或存在如何，此内容都将在电子数据展示中提供。 若要对标准 Yammer 内容使用电子数据展示，Yammer 网络需要处于 [本机模式](/yammer/configure-your-yammer-network/overview-native-mode)。
- 执行电子数据展示时，可以确定消息是在 Yammer 中生成的，还是通过 Teams 中的 Q&A 生成的。 在“文件元数据”部分中，可以在“项类”字段中找到该信息。
- 如果你的组织使用由 Yammer 提供支持的 Teams Q&A，则 Q&A 生成的内容将被视为 Yammer 内容，并且是可发现的。 有关 Microsoft 365 应用中的电子数据展示的详细信息，请参阅 [Microsoft 365 中的电子数据展示解决方案。](/microsoft-365/compliance/ediscovery)
- 如果会议组织者启用匿名发布，与会者发布的问题将引入组织者的邮箱进行电子数据展示。

## <a name="data-storage"></a>数据存储

问&作为会议一部分创建的消息存储为 Yammer 消息。 这些消息存储在 Yammer 中，并引入用于电子数据展示。
文件始终存储在 SharePoint 中，后者处理所有数据 rest 策略和位置。

以下指南介绍了如何存储消息传递数据：

- Q&内容可通过电子数据展示进行搜索，并在用户级别Advanced eDiscovery。
- 默认情况下，包含消息内容) 的消息数据 (将存储在北美或欧盟， (具体取决于客户的 Yammer 网络位置) 。
- 对于没有现有 Yammer 网络的租户，将在 美国 Yammer 区域中创建 Q&A Yammer 网络。 组织的 Q&A 消息将始终存储在美国。
- 与 OneNote 选项卡类似，从会议中删除 Q&A 不会删除会议数据。 从会议中删除 Q&A 只会从会议中删除对数据的访问权限。 如果添加 Q&A 选项卡，将再次看到所有会议对话。

## <a name="gdpr-for-qa-in-teams"></a>Teams 中 Q&A 的 GDPR

通过Microsoft 365 管理中心完成数据主体请求时，它会自动从 Q&A 中的所有内容中删除用户的联系信息。

## <a name="data-lifecycle-for-qa-in-teams"></a>Teams 中 Q&A 的数据生命周期

Teams 中 Q&A 生成的数据的生命周期取决于合规中心中的 Yammer 数据保留设置。 如果通过 Azure Active Directory 硬删除会议中收到 Q&A 消息副本的所有用户，Yammer 将在用户删除后的 30 天内删除该会议 Q&A 内容的副本。

## <a name="retention-and-deletion"></a>保留和删除

内容保留遵循为 Yammer 设置的保留策略 - 无论你是否为 Yammer 和 Teams 设置了不同的策略。

> [!NOTE]
> 如果 Yammer 网络不处于本机模式，此处创建的策略将仅适用于 Teams Q&A 数据。 在本机模式下，所有 Yammer 用户都位于 Azure Active Directory (Azure AD) 中，所有组Microsoft 365 个组，所有文件都存储在 SharePoint Online 中。

## <a name="faq"></a>常见问题

**问：如何实现导出 Q&A 内容？**

**答：** Q&内容存储在Microsoft 365 合规中心中，并通过电子数据展示访问。 未来的迭代将包括会议重点报告和会议组织者的导出功能。

**问：Q&A 是否支持 Microsoft 365 多地理位置功能？**

**答：** Q&A 目前不支持 Microsoft 365 多地理位置功能。 Q&默认情况下，根据客户的 Yammer 网络位置) ， (，A 数据存储在北美或欧盟。

**问：在哪里可以了解有关结构化会议的详细信息？**

**答：** 遵循以下 [最佳做法](/MicrosoftTeams/quick-start-meetings-live-events)，在 Microsoft Teams 中成功举办大型会议。

**问：通过 Teams 应用商店设置 Q&A 与使用会议选项有何区别？**

**答：** 我们已简化通过会议选项启用 Q&A。从 2022 年 8 月开始，将不再支持 Teams 应用商店中的 Q&A 应用，因此只能通过会议选项启用 Q&A。 如果你是通过 Teams 应用商店启用 Q&A 的会议的组织者，请删除 Q&A 应用，而仅通过会议选项启用。

**问：为什么我在会议中看到两个 Q&A 图标？**

**答：** 会议中会显示两个 Q&A 图标，因为 Q&A 也通过会议选项启用。 请按照以下说明删除通过 Teams App Store添加的 Q&A 应用。 请针对之前通过 Teams 应用商店添加 Q&A 的所有会议执行此操作。

**如何删除从 Teams 应用商店添加的 Q&A 应用。**

1. 在 Teams 桌面上，加入之前添加 Q&A 的会议。

2. 在顶部面板中，选择“Teams 会议”窗口中第二个“Q&A”图标，这是通过 Teams App Store添加的 Q&A 体验。

3. 打开所选的 Q&A 选项卡后，单击省略号并单击“删除”。 这将删除通过 Teams 应用商店添加的 Q&A 体验。

4. 单击“删除”可永久删除通过 Teams 应用商店添加的 Q&A 体验。

> [!NOTE]
> 只有通过 Teams 应用商店添加的 Q&A 应用才会有一个省略号来删除 Q&A 应用。 通过会议选项启用的 Q&A 体验不会有省略号，并且无法从此处删除。

就是这样！ 现在只有一个 Q&A 体验 - 由会议选项提供支持。 已删除通过 Teams 应用商店添加的 Q&A 应用。
