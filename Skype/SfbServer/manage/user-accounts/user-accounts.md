---
title: 管理 Skype for Business Server 的用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各节介绍如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009635"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>管理 Skype for Business Server 的用户帐户

本文中的各节介绍如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。

有关如何启用 Active Directory 用户的信息，请参阅[创建新用户帐户](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)。 有关如何删除 Active Directory 用户的信息，请参阅[删除用户帐户](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)。

当 Skype for Business 使用率最低时，应在维护时段内执行这些过程。 您的组织的需求是否取决于每日或每周计划是否完成此操作。

本文包含以下过程：

- [搜索一个或多个用户](user-accounts.md#Search)

- [添加和启用新的 Skype for Business Server 用户](user-accounts.md#Add)

- [禁用或重新启用之前为 Skype for business Server 启用的用户帐户](user-accounts.md#Disable)

- [为用户禁用企业语音](user-accounts.md#Disable_EV)

- [使用 Skype for Business Server 命令行管理程序删除用户帐户](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>搜索一个或多个用户
<a name="Search"> </a>

您可以使用搜索查询的结果为 Skype for business Server 配置 Active Directory 用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。

您可以使用 Skype for Business Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。 以下过程介绍如何使用 Skype for Business Server 控制面板搜索用户。

> [!NOTE]
> 在具有中央林拓扑的环境中，当您按用户的电子邮件地址搜索用户时，搜索结果可能不准确。 可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 **Get-CSUser** cmdlet。

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“用户”****。

4. 在“搜索用户”**** 框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的全部或第一部分，然后单击“查找”****。

5. （可选）指定附加搜索条件以缩小结果的范围：

   a. 单击“搜索结果”**** 上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”****。

   b. 通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。

   c. 在“等于”**** 列表中，单击“等于”**** 或“不等于”****。

   d. 在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击“查找”****。

6. 搜索结果将显示在“搜索结果”**** 下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>添加和启用新的 Skype for Business Server 用户
<a name="Add"> </a>

在 Active Directory 用户和计算机中启用用户帐户后，可以使用 Skype for Business Server 控制面板通过将 Active Directory 用户添加到 Skype for business Server 来创建和启用新的 Skype for Business Server 用户帐户。

您还可以使用 cmdlet，特别是[Enable-get-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“用户”****。

4. 单击“启用用户”****。

5. 在“新建 Lync Server 用户”**** 对话框中，单击“添加”****。

6. 在“搜索用户”**** 框中，键入所需 Active Directory 用户帐户的完整的名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、电子邮件地址、用户主体名称 (UPN) 或电话号码，或这些内容的第一部分，然后单击“查找”****。

7. 在表中，选择要添加到 Skype for business Server 的帐户，然后单击 **"确定"**。

8. 将该用户分配给某个池，指定其他任何详细信息，并向所需用户分配策略，然后单击“启用”****。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>禁用或重新启用之前为 Skype for business Server 启用的用户帐户
<a name="Disable"> </a>

您可以使用以下过程在 Skype for Business Server 中禁用以前启用的用户帐户，而不会丢失为该用户帐户配置的 Skype for Business 服务器设置。 由于您不会丢失 Skype for Business Server 用户帐户设置，因此您可以重新启用以前启用的用户帐户，而无需重新配置用户帐户。

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“用户”****。

4. 在“搜索用户”**** 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5. 在表中，单击要禁用或重新启用的用户帐户。

6. 在“操作”**** 菜单上，执行下列操作之一：

   - 若要暂时禁用 Skype for business Server 的用户帐户，请单击 "为**Lync Server 暂时禁用**"。

   - 若要为 Skype for business Server 启用用户帐户，请单击 "**为 Lync Server 重新启用**"。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows Powershell 禁用或重新启用用户帐户

可以暂时禁用用户帐户，然后再使用**get-csuser** cmdlet 重新启用用户帐户。 您可以从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for business Server 的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 Skype for Business Server 中的过程相同。

### <a name="to-disable-a-user-account"></a>禁用用户帐户

- 若要暂时禁用某一用户帐户，请将 Enabled 属性的值设置为 False ($False)。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>重新启用用户帐户

- 若要重新启用已禁用的用户帐户，请将 Enabled 属性的值设置为 True ($True)。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

有关详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。

## <a name="disable-a-user-for-enterprise-voice"></a>为用户禁用企业语音
<a name="Disable_EV"> </a>

使用以下过程可为对 Skype for business Server 启用的用户帐户禁用企业语音。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>为企业语音禁用用户帐户

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“用户”****。

4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5. 在表中，单击要为企业语音启用的用户帐户。

6. 在“编辑”**** 菜单上，单击“显示详细信息”****。

7. 在“编辑 Lync Server 用户”**** 页的“电话”**** 下，单击“企业语音”****。

    > [!NOTE]
    > 若要使用 Lync 限制用户进行音频或视频呼叫，请在 "**电话服务**" 下单击 "**音频/视频已禁用**"。

8. 单击“提交”****。

用户现在无法使用企业语音功能。 相关信息： <br/>[企业语音和移动性](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [在 Skype for Business Server 中为用户启用企业语音](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 命令行管理程序](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除用户帐户
<a name="Remove"> </a>

您可以使用以下过程在 Skype for Business Server 中删除之前添加的用户帐户。

> [!NOTE]
> 移除用户将导致您丢失为用户帐户配置的所有设置。 如果要暂时禁用用户帐户，请参阅[disable or 重新启用之前为 Skype for Business Server 启用的用户帐户](user-accounts.md#Disable)。

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3. 在左侧导航栏中，单击“用户”****。

4. 在“搜索用户”**** 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5. 在表中，单击要移除的用户帐户。

6. 在“操作”**** 菜单上，选择“从 Lync Server 中删除”****，然后将出现一个对话框。

7. 从该对话框中，选择“确定”**** 来移除该用户。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>使用 Windows Powershell cmdlet 删除用户帐户

您可以使用 Get-csuser cmdlet 删除用户帐户。 此 cmdlet 可从 Skype for Business Server 命令行管理程序或远程会话 Windows PowerShell 中运行。 有关使用远程 Windows PowerShell 连接到 Skype for business Server 的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 Skype for Business Server 中的过程相同。

### <a name="to-remove-a-user-account"></a>删除用户帐户
若要移除用户帐户，请使用 Disable-CsUser cmdlet。 例如：

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

有关详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅
<a name="Remove"> </a>

[Enable-Get-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-Get-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
