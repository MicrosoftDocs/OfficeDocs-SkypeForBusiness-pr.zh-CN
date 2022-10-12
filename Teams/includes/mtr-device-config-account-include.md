
每个Microsoft Teams 会议室设备都需要自己的资源帐户。 资源帐户是Teams 会议室设备登录的帐户，也是组织中的用户邀请预订 Teams 会议室的帐户。

创建资源邮箱时，可以指定是否允许定期会议、让会议室自动接受邀请、将来接受邀请的天数等。

> [!TIP]
> 命名资源帐户时，建议使用电子邮件地址开头的标准命名约定。 这将有助于创建动态组，以简化 Azure Active Directory 中的管理。 例如，可以对与Microsoft Teams 会议室关联的所有资源帐户使用“mtr-”。

> [!TIP]
> 建议使用 Exchange Online 和 Azure Active Directory 创建所有资源帐户。

使用以下选项卡之一的方法创建资源帐户：

#### <a name="in-microsoft-365-admin-center"></a>[**在Microsoft 365 管理中心**](#tab/m365-admin-center)

1. 登录到 Microsoft 365 管理中心。

2. 为 Microsoft 365 租户提供管理员凭据。

3. 转到左侧面板中的 **“资源** ”，然后选择 **“会议室”&设备**。 如果这些选项在左侧面板中不可用，则可能需要先选择 **“全部显示** ”。

4. 选择 **“添加资源** ”以创建新的资源帐户。 输入帐户的显示名称和电子邮件地址，然后选择 **“保存**”。

5. 默认情况下，资源帐户配置有以下设置：

    - 允许重复会议
    - 自动拒绝超出以下限制的会议
      - 预订窗口 (天) ：180
      - 最长持续时间 (小时) ：24
    - 自动接受会议请求

    如果要更改这些选项，请在选择 **“关闭**”之前选择 **“编辑预订”选项**。 如果以后要更改它们，请转到 **资源** > **室&设备**，选择资源帐户。 然后在 **“预订”选项** 下，选择 **“编辑**”。

6. 转到 **用户** > **活动用户**，然后选择创建的房间以打开属性面板。

7. 接下来，将密码分配给资源帐户。 在面板中，选择 **“重置密码**”。

8. 要求用户更改共享设备上的密码会导致登录问题。 取消选中 **要求此用户在首次登录时更改其密码**，然后选择 **“重置密码**”。

你可能需要将带宽策略或会议策略应用到此帐户。 可以在后续步骤中设置邮箱策略。

#### <a name="with-exchange-online"></a>[**使用Exchange Online**](#tab/exchange-online)

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 默认情况下，会议室邮箱没有关联的帐户。 创建会议室邮箱时添加帐户，以便可以使用 Microsoft Teams 进行身份验证。

    如果要创建新的资源邮箱：

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    此示例使用以下设置创建新会议室邮箱：

    - 帐户：ConferenceRoom01@contoso.com

    - 名称：ConferenceRoom01

    - 别名：ConferenceRoom01

    - 帐户密码：P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

如果使用的是 Exchange 混合配置，则需要为本地域帐户添加电子邮件地址。 有关详细信息，请参阅[本地同步和Office 365用户帐户目录](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

#### <a name="with-exchange-server"></a>[**使用Exchange Server**](#tab/exchange-server)

  1. 连接到 Exchange Management Shell。 [打开 Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 或 [使用远程 PowerShell 连接到 Exchange 服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

  2. 若要创建新会议室邮箱，请执行以下操作：

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      此示例使用以下设置创建新会议室邮箱：

      - 帐户：ConferenceRoom01@contoso.com

      - 名称：ConferenceRoom01

      - 别名：ConferenceRoom01

      - 帐户密码：P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**修改现有的 Exchange 会议室邮箱**](#tab/existing-account)

若要修改现有会议室邮箱以成为资源帐户，请使用以下语法：

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

本示例为具有别名值 ConferenceRoom02 的现有会议室邮箱启用帐户，并将密码设置为 9898P@$$W 0rd。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

如果使用的是 Exchange 混合配置，则还需要为本地域帐户添加电子邮件地址。 有关详细信息，请参阅[本地同步和Office 365用户帐户目录](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

有关详细的语法和参数信息，请参阅 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果要为 Surface Hub 上的 Teams 会议室创建此帐户，还应在此帐户上启用 ActiveSync。 这将允许你直接从 Surface Hub 发送电子邮件，可用于 Whiteboard 等功能。 有关详细信息，请参阅 [将 ActiveSync 策略应用到 Surface Hub (设备帐户) ](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) 。

---

> [!IMPORTANT]
> 如果仅使用此资源帐户来预订空间并自动接受或拒绝邀请，则已完成设置。 如果使用此资源帐户进行 PSTN 调用，请参阅 [Microsoft Teams 加载项许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 以确定它所需的许可证。
