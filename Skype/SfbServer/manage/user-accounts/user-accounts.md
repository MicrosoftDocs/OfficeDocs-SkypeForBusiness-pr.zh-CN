---
title: 管理用户帐户的 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各节介绍如何启用、 暂时禁用或删除业务服务器从 Skype Active Directory 用户。
ms.openlocfilehash: 918bdf556f040c115abf5869ad7a7dcd76a3271f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250792"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>管理用户帐户的 Skype 业务服务器

本文中的各节介绍如何启用、 暂时禁用或删除业务服务器从 Skype Active Directory 用户。

有关如何启用 Active Directory 用户的信息，请参阅[创建一个新的用户帐户](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。 有关如何删除 Active Directory 用户的信息，请参阅[删除用户帐户](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。

最低 Skype 业务使用时，应在维护窗口期间执行这些过程。 这完成每天或每周计划取决于您组织的需要。

本文包含以下过程：

- [搜索一个或多个用户](user-accounts.md#Search)

- [添加和启用新的 Skype Business Server 用户](user-accounts.md#Add)

- [禁用或重新启用以前启用的 Skype 业务服务器的用户帐户](user-accounts.md#Disable)

- [禁用企业语音的用户](user-accounts.md#Disable_EV)

- [业务 Server 命令行管理程序删除与 Skype 的用户帐户](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>搜索一个或多个用户
<a name="Search"> </a>

可以使用搜索查询的结果配置 Active Directory 用户的 Skype 业务服务器。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。

您可以通过使用 Skype 业务 Server Control Panel 或 Active Directory 用户来搜索用户和计算机管理单元。 以下过程介绍如何使用业务 Server Control Panel 的 Skype 搜索用户。

> [!NOTE]
> 在与中央林拓扑的环境中，搜索结果可能不准确时按用户的电子邮件地址搜索用户。 相反，您可以通过指定 SIP 地址前缀，例如，sip： 名称搜索用户、 添加搜索筛选器和选择 SIP 地址包含部分电子邮件地址，或使用**Get-csuser** cmdlet。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左导航栏中，单击“**用户**”。

4. 在**搜索用户**框中键入所有或显示名称、 名字、 姓氏、 SAM 帐户名的第一部分，SIP 地址或线路 URI 的要搜索，然后单击**查找**的用户帐户。

5. （可选）指定附加搜索条件以缩小结果的范围：

   a. 单击**搜索结果**上方屏幕右上角的展开箭头按钮，然后单击**添加筛选器**。

   b. 通过键入或单击下拉列表中选择一个用户属性中的箭头，输入用户属性。

   c. 在**等于**列表中，单击**等于**或**不等于**。

   d. 在文本框中，键入您想要用于筛选搜索结果的搜索条件，然后单击**查找**。

6. 在**搜索结果**下显示搜索结果。 您可以在列表中选择任一或所有用户，并对您都选择的用户执行配置任务。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>添加和启用新的 Skype Business Server 用户
<a name="Add"> </a>

启用后 Active Directory 用户和计算机中的用户帐户，可以使用业务 Server Control Panel 的 Skype 创建和启用业务 Server 用户帐户的新 Skype 业务服务器向 Skype 添加 Active Directory 用户。

您还可以使用 cmdlet，特别是[启用 CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左导航栏中，单击“**用户**”。

4. 单击**启用用户**。

5. 在**新建 Lync Server 用户**对话框中，单击**添加**。

6. 在**搜索用户**框中键入所有或名称的第一部分，显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名称、 电子邮件地址、 用户主体名称 (UPN) 或电话号码所需的 Active Directory 用户帐户，然后单击**查找**。

7. 在表中，选择您想要添加到 Skype 业务服务器的帐户，然后单击**确定**。

8. 将用户分配给池，指定其他任何详细信息，并将策略分配给您希望的用户，然后单击**启用**。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>禁用或重新启用以前启用的 Skype 业务服务器的用户帐户
<a name="Disable"> </a>

您可以使用以下过程而不会丢失的业务服务器设置配置的用户帐户的 Skype 业务服务器禁用 Skype 中的以前启用的用户帐户。 因为不会丢失 Business Server 用户帐户设置的 Skype，您可以重新启用以前启用的用户帐户再次而无需重新配置的用户帐户。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左导航栏中，单击“**用户**”。

4. 在**搜索用户**框中键入所有或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您想要禁用或重新启用的用户帐户的统一资源标识符 (URI) 的第一部分然后单击**查找**。

5. 在表中，单击您想要禁用或重新启用的用户帐户。

6. 在**操作**菜单中，执行以下任一操作：

   - 要暂时禁用的用户帐户的 Skype 业务服务器，请单击**Lync server 临时禁用**。

   - 要为业务服务器启用 Skype 的用户帐户，请单击**重新启用 Lync Server**。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows Powershell 禁用或重新启用用户帐户

可以暂时禁用，然后稍后重新启用，使用**Set-csuser** cmdlet 的用户帐户。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。

### <a name="to-disable-a-user-account"></a>若要禁用的用户帐户

- 要暂时禁用的用户帐户，设置为 False ($False) 的 Enabled 属性的值。 例如：

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>若要重新启用用户帐户

- 若要重新启用禁用的用户帐户，设置为 True ($True) 的 Enabled 属性的值。 例如：

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

有关详细信息，请参阅[Set-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。

## <a name="disable-a-user-for-enterprise-voice"></a>禁用企业语音的用户
<a name="Disable_EV"> </a>

使用以下过程为 Skype 业务 server 启用用户帐户禁用企业语音。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>若要禁用企业语音的用户帐户

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左导航栏中，单击“**用户**”。

4. 在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。

5. 在表中，单击您想要启用企业语音的用户帐户。

6. 在“编辑”**** 菜单上，单击“显示详细信息”****。

7. 在**编辑 Lync Server 用户**页上，在**电话**下单击**企业**语音的任何选项。

    > [!NOTE]
    > 若要限制用户发出音频或视频呼叫使用 Lync，在**电话**下的单击**禁用音频/视频**。

8. 单击“**提交**”。

现在，用户不能使用企业语音功能。 相关的信息： <br/>[企业语音和移动性](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Skype 中的企业语音的用户启用企业服务器](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理程序](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>业务 Server 命令行管理程序删除与 Skype 的用户帐户
<a name="Remove"> </a>

您可以使用以下过程中 Skype 业务服务器删除以前添加的用户帐户。

> [!NOTE]
> 删除用户将导致丢失的用户帐户配置的任何设置。 如果您想要暂时改为禁用的用户帐户，请参阅[禁用或重新启用以前启用了企业服务器的 Skype 的用户帐户](user-accounts.md#Disable)。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3. 在左导航栏中，单击“**用户**”。

4. 在**搜索用户**框中键入所有或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您想要禁用或重新启用的用户帐户的统一资源标识符 (URI) 的第一部分然后单击**查找**。

5. 在表中，单击您想要移除的用户帐户。

6. 在**操作**菜单、 选择**从 Lync Server 中删除**，和对话框显示框。

7. 从对话框框中，选择**确定**以删除该用户。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>删除与 Windows Powershell cmdlet 的用户帐户

您可以通过使用 Disable-csuser cmdlet 删除用户帐户。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。

### <a name="to-remove-a-user-account"></a>若要删除的用户帐户
若要删除的用户帐户，请使用 Disable-csuser cmdlet。 例如：

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

有关详细信息，请参阅[Disable-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅
<a name="Remove"> </a>

[启用 CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)