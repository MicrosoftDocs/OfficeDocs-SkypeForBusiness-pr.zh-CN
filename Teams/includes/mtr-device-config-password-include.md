
与任何 Microsoft 365 帐户一样，新创建的资源帐户密码将在一段时间后自动过期。 但是，如果资源帐户密码过期，则登录到的Teams 会议室设备将无法在到期日期再次登录。 

为了避免不得不重置资源帐户的密码，然后再次登录到每个Teams 会议室设备，可以关闭帐户的密码过期。
  
> [!NOTE]
> 对于共享的 Microsoft Teams 设备，设置 **密码永远不会过期** 。 如果域规则禁止密码过期，则需要为每个 Teams 设备资源帐户创建异常。

按照以下选项卡之一中的步骤关闭密码过期：

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

首先，连接到 Active Directory PowerShell：

```PowerShell
   Connect-AzureAD
```

然后，请参阅 [“将密码设置为永不过期](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire)”。

本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 连接到 MSOnline PowerShell：

       ```PowerShell
       Connect-MsolService
       ```

       有关 Active Directory 的详细信息，请 [参阅 Azure Active Directory (MSOnline) ](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (本地)**](#tab/active-directory1-password/)

1. 连接到 Active Directory PowerShell：

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    有关 Active Directory PowerShell 的详细信息，请参阅 [ActiveDirectory](/powershell/module/activedirectory)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---