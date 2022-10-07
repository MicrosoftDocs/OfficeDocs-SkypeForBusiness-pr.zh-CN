---
title: 使用日历将Microsoft Teams 协作版 (AAD 标识) 连接到现有电子邮件系统
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解如何使用日历（如 Google Workspace）将Microsoft Teams 协作版 (AAD 标识) 连接到现有电子邮件系统
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acdd613044e5e7f0ac7db857ca734f276522c919
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377590"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>使用日历将Microsoft Teams 协作版 (AAD 标识) 连接到现有电子邮件系统

本指南提供用于将Microsoft Teams 协作版 (AAD 标识) 连接到具有日历的现有电子邮件系统的配置步骤。

Microsoft Teams 协作版 (AAD 标识) 通过会议、聊天、通话和协作将最好的 Teams 汇集在一起。 Teams Essentials (AAD 标识) 可以连接到现有电子邮件系统，以提供集成体验，例如在现有电子邮件收件箱中包含所有 Teams 通知、Teams 中的所有日历事件，以及使用现有电子邮件地址登录 Teams 的功能。

连接后，可以在邮箱和 Microsoft Teams 中查看对计划会议的响应和协作邀请。 还可以使用 Teams 和第三方会议软件（如 Google Workspace）查看日历中的传入会议并与之交互。

## <a name="prerequisites"></a>先决条件

本文中的配置步骤涉及从Exchange Online自动转发项的过程。 默认情况下，反垃圾邮件出站策略禁用自动转发。 必须启用此策略才能将 Teams Essentials 连接到现有邮箱和日历系统。

若要启用自动转发，请执行以下操作：

1. 转到Microsoft 365 Defender门户<https://security.microsoft.com/>
2. 在左侧导航菜单下，转到“策略”部分中的 **Email &协作** > 策略 **&规则** > **威胁策略** > **反垃圾邮件**
3. 在 **“反垃圾邮件策略**”页上，从列表 **中选择“反垃圾邮件出站策略 (默认)**
4. 在显示的策略详细信息浮出控件中，选择 **“编辑保护设置** ”以修改自动前移规则。
5. 在 **“转发规则**”下，将自动转发条件更改为 **“启用 - 转发”** 并保存更改。

:::image type="content" source="media/essentials-antispam.png" alt-text="显示Microsoft Defender门户反垃圾邮件出站策略浮出控件的图像，在转发规则下启用了转发条件。" :::

若要详细了解如何配置出站垃圾邮件策略，请访问[配置出站垃圾邮件筛选 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>使用本地 Exchange 将 Teams Essentials 连接到Exchange Online

可以使用混合方法配置 Microsoft Teams 与本地 Exchange 的连接，从而享受 AAD (AAD Exchange Online) 必须提供的所有 Teams 概要。

若要使日历访问适用于本地邮箱，请遵循为[Exchange 本地邮箱配置 Teams 日历访问权限](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)时提供的指南 - Microsoft Tech Community

若要使用本地 Exchange 在混合环境中部署Microsoft Teams 会议室，请访问[使用 Exchange 本地部署Microsoft Teams 会议室 - Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>使用日历将 Teams Essentials 连接到第三方电子邮件系统

如果不打算将组织的邮箱切换到 Microsoft 365，则可以将 Teams Essentials 连接到现有的第三方电子邮件和日历系统。 通过此连接，可以在查看 Microsoft Teams 中的现有会议邀请和日历事件时，在现有电子邮件系统中接收 Teams 通知。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>使用虚荣域将 Teams Essentials 连接到第三方电子邮件 (Google 工作区示例) 

以下部分介绍如何使用日历（如 Google Workspace）将 Microsoft Teams 连接到现有电子邮件系统。 你将通过保持当前电子邮件系统完好无损、将所有电子邮件转发到Exchange Online、筛选除日历类型电子邮件以外的所有内容来完成此连接。 在执行此操作时，日历电子邮件会自动显示在已接受为暂定和非日历类型电子邮件的 Teams 日历中。

Microsoft 365 中生成的所有电子邮件都转发到 Google 工作区，以便用户获取 Teams 提醒和通知。 用户标识（如用户的主要电子邮件）可以重复。 也可以单一登录，但不是必需的。 用户应该能够从第三方日历或 Teams 日历加入 Teams 会议。 其他 Teams 功能将按预期工作。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="描述 EXO 和 Gmail 之间的邮件流关系图的图像":::

这些示例依赖于作为 [Exchange Online PowerShell V2 模块](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps)一部分的 [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) PowerShell 命令。 如果在运行 Connect-ExchangeOnline 时遇到错误，请确保已按照建议的说明使用 [安装 EXO V2 模块安装模块](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module)。 当Connect-ExchangeOnline提示输入凭据时，请务必使用租户管理员帐户。

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>步骤一：设置新的 Microsoft 365 租户域

1. 转到管理中心 <https://admin.microsoft.com>。

2. 转到 **“设置域”** > ，然后选择 **“添加域**”以添加现有域。 如果不添加域，组织中的人员将使用其电子邮件地址的 onmicrosoft.com 域，直到你这样做。 在添加用户之前，请务必添加域，因此无需设置两次。

3. 按照 [使用 TXT 记录的 Verify 中的步骤验证具有 TXT 记录的](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)域。

4. 出现提示时，选择 **“不允许 Microsoft 365 配置 DNS**”。

5. 出现提示时，请在不更改现有 MX 记录的情况下保留这些记录。

6. 更新现有 SPF TXT 记录以包括 Microsoft 365。

7. 按照以下步骤手动 [设置 DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)，为 Microsoft 365 配置 DomainKeys 标识的邮件 (DKIM) 。

8. 登录到Microsoft 365 管理中心处<https://admin.microsoft.com/AdminPortal/>以启用 DKIM

9. 在左侧导航面板中，选择 **“设置** > **域**”

10. 使用复选框，从当前域列表中选择现有的非 Microsoft 域 (ex：TomislavK@thephone-company.com) 。

11. 选择具有三个 **垂直点的** 按钮以打开菜单。

12. 在菜单中，选择 **“设置为默认值”**

13. 确认在窗口中将现有域设置为 **默认值的默认设置**。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="将域设置为默认值的确认对话框的图像":::

    有关将域添加到 Microsoft 365 的更多指导，请按照“将 [域添加到 Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)”中所述的步骤进行操作。

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>步骤 2：添加用户并分配 Teams Essentials 许可证

1. 转到管理中心 <https://admin.microsoft.com> 添加单个用户

2. 转到 **用户** > **活动用户**，然后选择 **“添加用户**”

3. 在 **“设置基本信息** ”窗格中，填写基本用户信息，然后选择 **“下一步**”。
    - **名字：** 填写名字和姓氏、显示名称和用户名。
    - **域：** 选择用户帐户的域。 例如，如果用户的用户名是 Jakob，并且域 contoso.com，则使用 jakob@contoso.com 登录。
    - **密码设置：** 选择使用自动生成的密码或为用户创建自己的强密码。  确定在添加用户时是否要在电子邮件中发送密码。

4. 在 **“分配产品许可证** ”窗格中，选择用户的位置和相应的许可证。 如果没有可用的许可证，仍可添加用户并购买更多许可证。 选择“下一步”。

5. 在 **“可选设置”** 窗格中，如果要将此用户设为管理员，请展开 **“角色** ”。展开 **配置文件信息** 以添加有关用户的其他信息。

6. 选择 **“下一步**”，查看新用户的设置，如有必要进行任何其他更改，然后选择 **“完成添加**”，然后关闭。

若要同时添加多个用户，请按照[“添加用户”中的推荐步骤操作，并分配许可证 - Microsoft 365 管理员|Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>步骤 3：配置 Google Workspace

***配置发送到 Microsoft 365 和条带附件的电子邮件双重传递：***

1. 按照 Google 的步骤设置双重交付： <https://support.google.com/a/answer/9228551?hl=en>

2. 为Office 365添加路由

    - 在) 转到 Google 管理员 控制台<https://admin.google.com>
    - 转到应用> Google 工作区> Gmail >主机。
    - 输入路由名称。  (例如，Microsoft 365) 
    - 选择“单一主机”，输入为 Microsoft 365 (中域指定的 MX 记录，例如：ContosoLandscaping2-m365master-com.mail.protection.outlook.com) 

    **将邮件发送到 Exchange 本地/Exchange Online时解析 ATTR35 响应代码的智能主机方法：**
    - 选择“单一主机”，并输入作为智能主机的租户初始域的 MX 记录。 初始域采用 GUID.onmicrosoft.com 格式。 GUID 是提供给每个组织的唯一值，作为其在服务中注册的一部分。 GUID 是一个 128 位整数 (16 字节) ，可以在需要唯一标识符的所有计算机和网络中使用。
    - 可以使用命令行：nslookup -type MX GUID.onmicrosoft.com 解析 MX 记录 (例如：contosolandscaping2.mail.protection.outlook.com) 
    - 选择 **端口：25**
    - 继续使用建议的选项

3. 配置路由以Office 365

    - 打开 **Google 管理员控制台**<https://admin.google.com>

    - 转到 **应用** > **Google 工作区** > **Gmail** > **路由**

    - 在“ **路由”** 选项卡上，选择 **“配置”**

    - 输入规则 **的名称** 。  (例如，Gmail to Office 365) 

    - 若 **要影响电子邮件**，请同时选择 **入站** 和  **内部接收**

    - 对于 **上述类型的消息**，请选择 **“修改”消息**

    - 在 **“还传递到**”下，选择 **“添加更多收件人** ”，然后选择 **“添加”以添加辅助邮件路由。**

    - 在 **“收件人**”下，选择向下箭头“”，然后选择 **“高级”。**

    - 选择 **“更改路由”。**

    - 从列表中，选择之前创建的辅助邮件路由

    - 在 **“附件**”下，从 **邮件中选择“删除附件**”

    - 向下滚动并选择 **“保存**”。

***在 Google 工作区中添加子域以接收来自 Microsoft 365 的电子邮件。***

  接下来，你将创建 Microsoft 365 邮箱上的转发规则到子域。 选择要在 Google Workspace 中使用的子域以接收来自 Microsoft 365 的电子邮件 (例如，g.contosolandscaping2.m365master.com) 

1. 从 **google 管理员 控制台** 开始， (admin.google.com) 

2. 转到 **帐户** > **域** > **管理域**

3. 选择 **“添加域”**

4. 输入所选域名

5. 选择 **用户别名域**

6. 选择 **“添加域&开始验证**

7. 等待验证完成并刷新页面

8. 选择 **“激活 Gmail”**

9. 选择 **“跳过 MX 记录设置**”，然后选择 **“下一步**”

10. 在“**将邮件路由到另一台服务器**”对话框中，记下将邮件路由到 (例如，aspmx.l.google.com) 并选择 **“我使用另一个邮件服务器**”

***允许来自 Microsoft 365 的电子邮件绕过 SPAM 筛选器***

1. 通过向 Google 工作区上的用户发送电子邮件，从 Microsoft 365 租户中查找合适的标头。

2. 打开邮件并选择 **“显示原始**”

3. 选择唯一标识来自 Microsoft 365 租户的邮件的电子邮件标头。  (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

4. 转到 **Google 管理员控制台**<https://admin.google.com>

5. 转到 **应用** > **Google 工作区** > **Gmail** > **合规性**

6. 导航到 **内容符合性** 并选择 **“配置”**

7. 为设置指定一个名称。 例如，Allowlist Microsoft 365 电子邮件。

8. 在 **电子邮件下影响** 签入

9. 在 **“添加表达式”下，描述要在每个邮件中搜索的内容**，**如果以下任何一条与消息匹配，** 请选择

10. 在 **“表达式”** 下，选择 **“添加** xi”。 在 **“添加设置**”下，选择 **“高级内容”匹配项**

11. 在 **“位置”** 下选择 **“完整标头”**

12. 在 **“匹配类型** ”下选择 **全文**

13. 在内容下，输入唯一标识来自 Microsoft 365 租户的电子邮件的电子邮件标头 (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

14. 选择 **“保存”**

15. 在 **“如果上述表达式匹配”中，请执行以下** 字段>**修改邮件**，并在 **“垃圾** 邮件”下检查 **“绕过垃圾邮件”筛选器**。

16. 选择 **“保存”**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>步骤四：为集成配置 Microsoft 365 设置

*配置连接器以将邮件从 Microsoft 365 路由到 Gmail：*

1. 转到 **Microsoft 管理员中心**<https://admin.microsoft.com/AdminPortal>

2. 在左侧导航菜单中选择 **“全部显示** ”。

3. 在 **管理员中心** 下，选择 **“Exchange**”以在新选项卡中打开 Exchange 管理中心

4. 在 **Exchange 管理中心的** 左侧导航菜单中，选择 **“邮件流** > **连接器**”，打开溢出菜单 (...) ，然后选择“添加连接器”

5. 在新连接器窗口的“**连接**”下，选择 **Office 365**

6. 在 **“连接**”下选择组织的电子邮件服务器，然后选择 **“下一步**”

7. 输入新连接器的 **名称** (Ex：到 Gmail) ，然后继续 **下一步**

8. 在 **“使用连接器”** 部分中， **选择“仅当我设置了传输规则，将消息重定向到此连接器** ，然后选择 **下一步**”。

9. 在“路由”部分中，输入相应的智能邮件主机 (例如，aspmx.l.google.com) 、选择 **+**，然后继续 **下一步**。

10. 在 **“安全限制**”部分中，通过选择 **“下一步**”接受默认设置

11. 在 **“验证电子邮件”部分** 中，输入 Gmail 系统的有效电子邮件地址 (例如，johannal@g.contosolandscaping2.m365master.com) ，选择 **加号 (+)**，然后选择 **“验证**”

12. 等待验证完成，如果成功按下一步

13. 在 **“审阅”连接器** 下，验证配置是否正确，然后按“创建连接器”

14. 看到连接器创建的通知时，按 **“完成”**

*将邮件从 Microsoft 365 邮箱转发到 Gmail：*

1. 使用 **Microsoft 365 管理中心** 更新每个邮箱，也可以使用 **PowerShell** 脚本，如以下内容：

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Connect-ExchangeOnline 疑难解答：**

    运行 Connect-ExchangeOnline 时是否遇到错误？ 这可能是组织自动电子邮件转发规则的结果。 默认情况下，自动转发处于禁用状态。 若要将 Teams Essentials 连接到 Google 工作区，必须启用该规则。

    输入以下脚本：

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    之后，运行以下命令：

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*配置Exchange Online直接到日历传输规则：*

1. 配置此设置将自动接受日历邀请，以便它们显示在 Teams 日历中，而无需用户在Outlook Web App中与邀请交互。

2. 以下脚本可用于创建传输规则：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*禁用邮箱Outlook 网页版：*

1. 按照在Exchange Online中[启用或禁用邮箱Outlook 网页版](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)的说明禁用邮箱Outlook 网页版。

2. 可以使用 **Exchange 管理员中心** 或 **PowerShell** 禁用Outlook 网页版。 可以使用以下 PowerShell 示例为所有邮箱禁用Outlook 网页版：

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>步骤 5：为内部中继配置Exchange Online域

此步骤可确保将电子邮件发送到第三方系统以进行最终解决。

1. 转到 **Microsoft 管理员中心**<https://admin.microsoft.com/AdminPortal>

2. 在左侧导航中，选择 **“全部显示”**

3. 在 **“管理员中心**”下，选择 **“Exchange**”以在新选项卡中打开 Exchange 管理中心

4. 在 **Exchange 管理中心**，从左侧导航菜单中选择 **“邮件流** ”，然后选择 **“接受的域”**

5. 点击在第三方系统中配置的域名 (例如，contosoLandscaping2.m365master.com) 

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="显示邮件流的 Exchange 管理中心设置的图像。 ":::

6. 选择 **“内部中继**”，然后单击 **“保存”**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="显示保存内部中继设置的操作的图像。":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>步骤 6：创建一个规则，用于删除除日历之外Exchange Online的所有入站邮件

1. 可以在 **Exchange 管理员中心** 或 **PowerShell** 中配置此规则。 可以使用以下 **PowerShell** 示例创建规则：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>将 Teams Essentials 连接到不使用虚荣域的第三方电子邮件 (Gmail 示例) 

通过将使用者 Gmail 帐户连接到主要依赖 [Teams G Suite Add On](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) 的 Teams Essentials，可以直接从 Google Workspace 安排和加入 Teams 会议。 这使你有机会通过屏幕共享、会议聊天、数字白板等来安排视频和音频会议。

你将将 Gmail 配置为从 Exchange Online 拉取电子邮件，以确保在 Microsoft 365 中生成的邮件和 Teams 成功到达 Gmail。 可能需要禁用安全默认值才能完成此连接，这使使用强唯一密码变得至关重要。 此方案不需要自定义域，但如果要使用自定义域，可在 Microsoft 365 中将其配置为在 Gmail 中使用。

:::image type="content" source="media/essentials-gmail.png" alt-text="描述 Teams Essentials 和 Gmail 之间的邮件流的图像":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. 确保已设置 Gmail 帐户

如果已有帐户，可以继续执行下一步。 如果没有，请访问 [“创建新的 Google 帐户](https://accounts.google.com/SignUp?hl=en) ”以设置新的 Gmail 帐户。

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2.设置 Microsoft 365 租户

*配置 Teams AAD 用户：*

1. 遵循[“添加用户”指南并分配许可证](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 以添加多个用户

*配置标识保护：*

1. 如果处于活动状态，则禁用安全默认值。

2. 为用户配置多重身份验证

3. 如果使用条件访问，请务必为 POP 访问邮箱设置异常

*将域添加到Microsoft 365 管理中心 (可选) ：*

1. 在导航下，选择“设置>域”，然后选择“添加域”

2. 在相应的字段中输入域名

3. 按照屏幕上的说明使用 TXT 记录验证域

4. 出现提示时，允许 Microsoft 配置 DNS

5. 完成说明以验证到 Microsoft 365 的 MX 记录路由

6. 将 SPF TXT 记录配置为包含 Microsoft 365

7. 完成有关为 Microsoft 365 配置 DKIM TXT 记录的说明

8. 通过注销并重新登录到管理员中心来验证 DKIM 是否已启用

#### <a name="3-configure-gmail"></a>3. 配置 Gmail

1. 配置 Gmail 以将Exchange Online邮件拉入其系统

2. 配置 Teams 日历加载项

3. 使 Gmail 能够使用业务域 (可选) 
