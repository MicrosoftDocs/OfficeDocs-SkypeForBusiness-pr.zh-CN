---
title: 连接 Microsoft Teams Essentials (AAD Identity) 日历发送到现有电子邮件系统
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解如何将 Microsoft Teams Essentials (AAD Identity) Google Workspace 等日历连接到现有电子邮件系统
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 682f7bcd4e90e96534e954cd0e22c6f5952db08b
ms.sourcegitcommit: 563567ab140d5802756170c846dade3645d0b9e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284790"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>连接 Microsoft Teams Essentials (AAD Identity) 日历发送到现有电子邮件系统

本指南提供了使用日历将 Microsoft Teams Essentials (AAD Identity) 连接到现有电子邮件系统的配置步骤。

Microsoft Teams Essentials (AAD 标识) 将会议、聊天、呼叫Teams协作的最佳功能汇集在一起。 Teams Essentials (AAD Identity) 可以连接到现有电子邮件系统，以提供集成体验，例如，将所有 Teams 通知都放入现有电子邮件收件箱、Teams 中所有日历事件，以及使用现有电子邮件地址登录 Teams。

连接后，可在邮箱和邮箱中查看对计划会议和协作邀请Microsoft Teams。 您还可以使用 Google Workspace 等第三方Teams查看来自日历的传入会议并与之交互。

## <a name="prerequisites"></a>先决条件

本文中的配置步骤涉及自动转发来自Exchange Online。 默认情况下，反垃圾邮件出站策略禁用自动转发。 必须启用此策略，Teams Essentials 连接到现有邮箱和日历系统。

启用自动转发：

1. 转到 Microsoft 365 Defender 门户<https://security.microsoft.com/>
2. 在左侧导航菜单下，转到"**电子邮件**"&协作策略  >  **&"** 策略"部分中的威胁  >    >  策略反垃圾邮件
3. 在" **反垃圾邮件策略"** 页上，从列表中选择" (垃圾邮件) **策略** "
4. 在出现的策略详细信息飞出中，选择" **编辑保护设置** "以修改自动前向规则。
5. 在 **"转发规则**"下，将自动转发条件更改为"启用 - 转发 **"已启用** 并保存更改。

:::image type="content" source="media/essentials-antispam.png" alt-text="显示 Microsoft Defender 门户反垃圾邮件出站策略飞出的图像，其中显示"启用，转发"规则下已启用转发条件。" :::

若要详细了解如何配置出站垃圾邮件策略，请访问[配置出站垃圾邮件筛选 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>连接 Teams Essentials Exchange Online本地Exchange部署

可以使用混合Teams (AAD) 配置 Microsoft Teams 与 Exchange Online 本地Exchange连接，享受 Teams Essentials Exchange 提供的所有功能。

若要使本地邮箱的日历访问正常工作，请遵循为 Exchange 本地邮箱配置[Teams](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)日历访问 - Microsoft Tech Community

若要Microsoft Teams 会议室本地 Exchange混合环境中部署 Microsoft Teams 会议室，Exchange本地[部署 Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>连接 Teams日历将 Essentials 更新到第三方电子邮件系统

如果不想将组织的邮箱切换到 Microsoft 365，可以将 Teams 连接到现有的第三方电子邮件和日历系统。 通过此连接，Teams现有电子邮件系统中接收通知，同时查看现有会议邀请和日历Microsoft Teams。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>连接 Teams Google Workspace 示例中使用虚域向第三方电子邮件 (协作) 

以下部分演示如何使用日历（Microsoft Teams Google Workspace）将电子邮件连接到现有电子邮件系统。 若要完成此连接，请保持当前电子邮件系统不变，将所有电子邮件转发Exchange Online，筛选日历类型的电子邮件之外的所有内容。 这样做时，日历电子邮件会自动显示在Teams接受为暂定和非日历类型的电子邮件的日历中。

在 Microsoft 365 中生成的所有电子邮件都转发到 Google Workspace，以便用户Teams提醒和通知。 用户标识（如用户的主要电子邮件）可以重复。 也可以进行单一登录，但这不是必需的。 用户应该能够从第三Teams日历或日历中加入Teams会议。 其他Teams功能将正常工作。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="描述 EXO 和 Gmail 之间的邮件流的图表的图像":::

这些示例依赖于 连接 PowerShell V2 模块中的[Exchange Online-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) [PowerShell commandlet。](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) 如果在运行 连接-ExchangeOnline 时收到错误，请确保遵循了使用安装[EXO V2 模块安装模块的建议说明](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true)。 当Connect-ExchangeOnline提示输入凭据时，请务必使用租户管理员帐户。

**步骤 1：设置新的Microsoft 365租户域**

1. 转到 的管理中心 <https://admin.microsoft.com> 。

2. 转到"**设置域**  >  **"，** 然后选择 **"添加域**"以添加现有域。 如果不添加域，您的组织中的人员将使用 onmicrosoft.com 域作为电子邮件地址，直到您添加。 请务必在添加用户之前添加域，因此不必设置两次。

3. 按照使用 TXT 记录进行验证中的步骤，使用 [TXT 记录验证域](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)。

4. 系统提示时，**选择"不允许Microsoft 365配置 DNS。**

5. 当系统提示时，保留现有 MX 记录，而不更改它们。

6. 更新现有 SPF TXT 记录以包含Microsoft 365。

7. 按照以下步骤手动设置 DKIM， (DKIM) DKIM Microsoft 365，为用户[配置 DomainKey 标识的邮件](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)。

8. 在 上重新Microsoft 365 管理中心 <https://admin.microsoft.com/AdminPortal/> 以启用 DKIM

9. 在左侧导航面板中，选择"设置 **域**  >  **"**

10. 使用复选框，选择现有非 Microsoft 域 (例如：JohannaL@contosolandscapting2.m365master.com) 域列表。

11. 选择具有三 **个垂直圆点的按钮** 以打开菜单。

12. 在菜单中，选择" **设为默认值"**

13. **确认在显示以** 将现有域设置为默认域的窗口中将 设置为默认值。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="用于将域设置为默认值的确认对话框的图像":::

    有关向域添加域Microsoft 365，请遵循将域添加到 Microsoft 365 中所述[的步骤](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)。

**步骤 2：添加用户并Teams Essentials 许可证**

1. 转到管理中心， <https://admin.microsoft.com> 添加单个用户

2. 转到"**用户**  >  **""活动用户**"，然后选择 **"添加用户"**

3. 在 **"设置基本信息"窗格中**，填写基本用户信息，然后选择"下一步 **"。**
    - **名称：** 填写名字和姓氏、显示名称和用户名。
    - **域：** 选择用户帐户的域。 例如，如果用户的用户名为 Jakob，并且域 contoso.com，则他们将使用 jakob@contoso.com。
    - **密码设置：** 选择使用自动生成的密码或为用户创建自己的强密码。  确定是否要在添加用户时在电子邮件中发送密码。

4. 在 **"分配产品许可证** "窗格中，为用户选择位置和相应的许可证。 如果没有可用的许可证，仍可添加用户并购买更多许可证。 选择"下一步"。

5. 在"**可选设置"****窗格中，如果要** 使此用户成为管理员，请展开"角色"。展开 **"个人资料** 信息"，添加有关用户的其他信息。

6. 选择 **"下** 一步"，查看新用户的设置，如有必要进行任何其他更改，然后选择" **完成添加**"，然后关闭。

若要同时添加多个用户，请按照添加用户和分配许可证 - Microsoft 365[管理员|Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**步骤 3：配置 Google 工作区**

***配置电子邮件双重传送到Microsoft 365和条带附件：***

1. 按照 Google 设置双重交付的步骤操作： <https://support.google.com/a/answer/9228551?hl=en>

2. 添加路由Office 365

    - 转到 Google 管理控制台 <https://admin.google.com> ，) 
    - 转到"Google Workspace >应用> Gmail >主机"。
    - 输入路由名称。  (例如，Microsoft 365) 
    - 选择"单主机"，并输入为域指定的 MX 记录Microsoft 365 (例如：ContosoLandscaping2-m365master-com.mail.protection.outlook.com) 

    **将邮件发送到本地/Exchange时解析 ATTR35 响应代码的智能主机Exchange Online：**
    - 选择"单一主机"，并输入作为智能主机的租户初始域的 MX 记录。 初始域的格式为 GUID.onmicrosoft.com。 GUID 是一个唯一值，作为组织在服务中的注册的一部分提供给每个组织。 GUID 是 128 位整数 (16) ，可在需要唯一标识符的所有计算机和网络之间使用。
    - 可以使用命令行：nslookup -type MX GUID.onmicrosoft.com 解析 MX 记录 (例如：contosolandscaping2.mail.protection.outlook.com) 
    - 选择 **"端口：25"**
    - 继续执行建议的选项

3. 配置路由到Office 365

    - 打开 **Google 管理控制台** ， <https://admin.google.com>

    - 转到"**应用**  >  **""Google 工作区**  >  **Gmail**  >  **路由"**

    - 在"路由 **"选项卡** 上，选择" **配置"**

    - 输入 **规则** 的名称。  (例如，Gmail 到 Office 365) 

    - 若要 **影响电子邮件**，请选择"入站 **"** 和"  **内部接收"**

    - 在 **"对于上述类型的消息"下**，选择" **修改消息"**

    - 在 **"也发送到"** 下 **，选择"添加更多收件人** "，然后选择"添加" **以添加辅助邮件路由。**

    - 在 **"收件人"** 下，选择向下箭头""，然后选择"高级 **"。**

    - 选择" **更改路由"。**

    - 从列表中选择前面创建的辅助邮件路由

    - 在 **"附件"** 下， **选择"从邮件中删除附件"**

    - 向下滚动并选择"保存 **"。**

***在 Google 工作区中添加子域，以接收来自 Microsoft 365。***

  接下来，您将在将邮箱Microsoft 365子域创建转发规则。 选择要在 Google Workspace 中用于接收电子邮件的Microsoft 365 (例如，g.contosolandscaping2.m365master.com) 

1. 从 **Google 管理控制台 (，admin.google.com)**

2. 转到"**帐户**  >  **域**  >  **""管理域"**

3. 选择 **"添加域"**

4. 输入所选域名

5. 选择 **用户别名域**

6. 选择 **"添加域&开始验证**

7. 等待验证完成并刷新页面

8. 选择" **激活 Gmail"**

9. 选择 **"跳过 MX 记录设置"，** 然后选择"下一 **步"**

10. 在 **"将邮件路由** 到其他服务器"对话框中，记下将邮件路由到 (例如，aspmx.l.google.com) 并选择"我使用另一个 **邮件服务器"**

***允许来自Microsoft 365的电子邮件绕过垃圾邮件筛选器***

1. 通过向 Google 工作区上的Microsoft 365，从租户中查找相应的标头。

2. 打开邮件，然后选择" **显示原始内容"**

3. 选择唯一标识来自租户的邮件的电子邮件Microsoft 365邮件。  (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

4. 转到 **Google 管理控制台，** 位于 <https://admin.google.com>

5. 转到"**应用**  >  **""Google 工作区**  >  **Gmail**  >  **符合性"**

6. 导航到" **内容符合性"，** 然后选择"配置 **"**

7. 为设置命名。 例如，Allowlist Microsoft 365电子邮件。

8. 在 **"要影响的电子邮件"下，** 检查"入站"

9. 在 **"添加描述每** 封邮件中要搜索的内容的表达式"下，选择以下任一项是否 **与邮件匹配**

10. 在 **"表达式"** 下，选择 **"添加** xi"。 在 **"添加设置"** 下，选择 **"高级内容匹配"**

11. 在 **"位置"****下，选择"完整标头"**

12. 在 **"匹配类型"****下，选择"全文"**

13. 在"内容"下，输入唯一标识来自 Microsoft 365 租户的电子邮件的电子邮件标头 (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

14. 选择" **保存"**

15. 在"**如果上述表达式匹配**"中，执行以下字段>**修改邮件**"，在"垃圾邮件"下选中"绕过垃圾邮件筛选器 **"。**

16. 选择" **保存"**

**步骤 4：Microsoft 365配置集成设置**

*配置连接器以将邮件从 Microsoft 365 Gmail：*

1. 转到 **Microsoft 管理中心**<https://admin.microsoft.com/AdminPortal>

2. 在 **左侧导航** 菜单中选择"全部显示"。

3. 在 **"管理中心****"Exchange，** 在新选项卡Exchange打开管理中心

4. 在 **Exchange管理** 中心的左侧导航菜单中，选择"邮件流连接器"，打开"溢出"菜单  >   (...) 选择"添加连接器"

5. 在新 **连接器窗口中** 的"从连接"下，**选择**"Office 365

6. 在 **"连接"** 下选择组织的电子邮件服务器，然后选择"下一 **步"**

7. 输入新 **连接器** 的名称，例如： (Gmail) "下一 **步"**

8. 在"**使用连接器"** 部分中，选择"仅在我具有将消息重定向到此连接器 **规则集** 传输连接时，选择"下一 **步"。**

9. 在"路由"部分中，输入相应的智能邮件 (例如，选择 **+** aspmx.l.google.com) ，然后继续"下一 **步"。**

10. 在" **安全限制"** 部分中，通过选择"下一步"接受 **默认设置**

11. 在" **验证电子邮件**"部分中，输入 Gmail 系统的有效电子邮件地址 (例如，johannal@g.contosolandscaping2.m365master.com) ，选择加号 **(+)**，然后选择"验证 **"**

12. 等待验证完成，如果成功，请按"下一步"

13. 在 **"查看连接器**"下，验证配置是否正确，然后按"创建连接器"

14. 看到连接器创建通知时，按" **完成"**

*将邮件从Microsoft 365邮箱转发到 Gmail*

1. 使用 **Microsoft 365 管理 中心** 更新每个邮箱，或者可以使用 **PowerShell** 脚本，如下所示：

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*配置Exchange Online日历传输规则*

1. 配置此设置将自动接受日历邀请，以便它们显示在Teams日历中，而无需用户在日历中与邀请Outlook Web App。

2. 以下脚本可用于创建传输规则：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*禁用Outlook 网页版邮箱的"*

1. 按照为邮箱[启用或禁用Outlook 网页版中的](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)Exchange Online中的说明Outlook 网页版邮箱。

2. 可以使用 Outlook 网页版 管理Exchange PowerShell **禁用****该设置**。 可以使用以下 PowerShell 示例来禁用Outlook 网页版邮箱的邮箱：

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**步骤 5：Exchange Online内部中继的域**

此步骤可确保将电子邮件发送到第三方系统进行最终解决。

1. 转到 **Microsoft 管理中心**<https://admin.microsoft.com/AdminPortal>

2. 在左侧导航栏中，选择" **全部显示"**

3. 在 **"管理中心****"Exchange，Exchange** 选项卡中打开管理中心

4. 在 **Exchange管理中心** 中，从左侧导航菜单中选择"邮件流"，然后选择"接受 **的域"**

5. 点击第三方系统配置域名 (例如，contosoLandscaping2.m365master.com) 

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="显示邮件Exchange管理中心设置的图像。":::

6. 选择 **"内部中继**"，并单击" **保存"**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="显示保存内部中继设置的行为的图像。":::

**步骤 6：创建一个规则，用于删除除日历Exchange Online所有入站邮件**

1. 可以在管理中心或 **PowerShell** Exchange配置此 **规则**。 可以使用以下 **PowerShell 示例** 创建规则：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>连接 Teams Essentials 发送到第三方电子邮件，而不是使用虚域或 Gmail (示例) 

可以通过将消费者 Gmail Teams连接到 Teams Essentials，直接从 Google Workspace 安排和加入 Teams 会议，主要依赖于[Teams G Suite 加载项](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60)。 这为你提供了使用屏幕共享、会议聊天、数字白板等安排视频和音频会议的机会。

将 Gmail 配置为从 Exchange Online 提取电子邮件，以确保在 Microsoft 365 中Teams邮件成功到达 Gmail。 可能需要禁用安全默认值才能完成此连接，因此，使用强唯一密码至关重要。 此方案不需要自定义域，但如果需要使用自定义域Microsoft 365可在 Gmail 中配置自定义域。

:::image type="content" source="media/essentials-gmail.png" alt-text="在 Essentials 和 Gmail 之间Teams邮件流的图像":::

**确保已设置 Gmail 帐户。**

如果已有帐户，可以继续执行下一步。 如果没有，请访问 [创建新的 Google 帐户](https://accounts.google.com/SignUp?hl=en) 以设置新的 Gmail 帐户。

**2. 设置Microsoft 365租户**

*配置Teams AAD用户*

1. 按照添加用户[和分配许可证中的指导](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 添加多个用户

*配置标识保护*

1. 如果处于活动状态，则禁用"安全默认值"。

2. 为用户配置多重身份验证

3. 如果使用条件访问，请确保对邮箱进行 POP 访问时例外

*将域添加到Microsoft 365 管理中心 (可选)*

1. 在导航下，选择设置 >域"，然后选择"添加域"

2. 在相应的字段中输入域名

3. 按照屏幕上的说明使用 TXT 记录验证域

4. 系统提示时，允许 Microsoft 配置 DNS

5. 完成说明以验证 MX 记录路由到Microsoft 365

6. 配置 SPF TXT 记录以包含Microsoft 365

7. 完成为用户配置 DKIM TXT 记录Microsoft 365

8. 注销并重新登录到管理中心，验证是否已启用 DKIM

**3. 配置 Gmail**

1. 将 Gmail 配置为将Exchange Online邮件拉取到其系统中

2. 配置Teams日历加载项

3. 使 Gmail 能够使用业务域 (可选) 
