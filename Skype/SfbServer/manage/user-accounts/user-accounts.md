---
title: 管理用户的用户帐户Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各节介绍如何启用、临时禁用 Active Directory 用户或删除 Skype for Business Server。
---

# <a name="manage-user-accounts-for-skype-for-business-server"></a>管理用户的用户帐户Skype for Business Server

本文中的各节介绍如何启用、临时禁用 Active Directory 用户或删除 Skype for Business Server。

若要了解如何启用 Active Directory 用户，请参阅创建新的 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))。 若要了解如何删除 Active Directory 用户，请参阅删除 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。

这些过程应在维护时段内执行，Skype for Business使用率最低时。 这是按每天还是按周计划完成，取决于组织的需要。

本文包含以下过程：

- [搜索一个或多个用户](#search-for-one-or-more-users)

- [添加和启用新的Skype for Business Server用户](#add-and-enable-a-new-skype-for-business-server-user)

- [禁用或重新启用用户帐户进行Skype for Business Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [为用户禁用企业语音](#disable-a-user-for-enterprise-voice)

- [使用命令行管理程序Skype for Business Server用户帐户](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>搜索一个或多个用户

您可以使用搜索查询的结果为 Active Directory 用户配置Skype for Business Server。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。

可以使用"Active Directory 用户和计算机"Skype for Business Server控制面板或"Active Directory 用户和计算机"管理单元来搜索用户。 以下过程介绍如何使用Skype for Business Server控制面板搜索用户。

> [!NOTE]
> 在具有中央林拓扑的环境中，当您按用户的电子邮件地址搜索用户时，搜索结果可能不准确。 可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 **Get-CSUser** cmdlet。

### <a name="search-for-users-using-the-new-control-panel"></a>使用新的控制面板搜索用户 

1. 打开浏览器窗口并输入管理 URL 以打开Skype for Business Server控制面板。
 
2. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录。

3. 在左窗格中，选择" **用户"**。

4. 在"**用户**"页上的"搜索"框中，键入要搜索的所有显示名称第一部分，然后按 **Enter**。

5. （可选）指定附加搜索条件以缩小结果的范围：

    1. 单击"搜索"框旁边的 **筛选器** 按钮。

    2. 在出现的 **"** 筛选器"面板中，单击下拉列表中的箭头，选择所需的用户属性。

    3. 单击下拉运算符列表中的箭头，选择所需的运算符。

    4. 在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击"确定 **"**。

6. 搜索结果显示在"用户 **"** 页上。 可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。

> [!NOTE]
> 新控制面板不适用于 2015 Skype for Business Server控制面板。

### <a name="search-for-users-using-the-legacy-control-panel"></a>使用旧版控制面板搜索用户 

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左窗格中，选择" **用户"**。

4. 在“搜索用户”框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的全部或第一部分，然后单击“查找”。

5. （可选）指定附加搜索条件以缩小结果的范围：

    1. 单击“搜索结果”上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”。

    2. 通过键入用户属性或单击下拉列表中的箭头选择用户属性来输入用户属性。

    3. 在" **等于"列表中** ，选择 **"等于** " **或"不等于"**。

    4. 在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击“查找”。

6. 搜索结果将显示在“搜索结果”下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>添加和启用新的Skype for Business Server用户

在 Active Directory 用户和计算机中启用用户帐户后，可以使用 Skype for Business Server 控制面板创建和启用新的 Skype for Business Server 用户帐户，通过将 Active Directory 用户添加到 Skype for Business Server。

您还可以使用 cmdlet，特别是 [Enable-CsUser](/powershell/module/skype/enable-csuser)。

### <a name="add-a-user-using-the-new-control-panel"></a>使用新的控制面板添加用户 

1. 打开浏览器窗口并输入管理 URL 以打开Skype for Business Server控制面板。
 
2. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录。

3. 导航到 **"UsersEnable** >  **Users"**，然后单击"添加 **"**。

4. 在" **搜索** "框中，键入搜索的所有部分或第一显示名称然后单击"查找 **"**。

5.  (可选) 若要指定其他用户条件，请单击" **+ 添加** 筛选器"，选择所需的用户属性，选择运算符，然后输入值。 单击“查找”。

6. 在表中，选择要添加到帐户Skype for Business Server然后单击"确定 **"**。

7. 将用户分配到池，指定任何其他详细信息，然后将所需策略分配给用户，然后单击"启用 **"**。

> [!NOTE]
> 新控制面板不适用于 2015 Skype for Business Server控制面板。

### <a name="add-a-user-using-the-legacy-control-panel"></a>使用旧版控制面板添加用户 

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 导航到 **UsersEnable** >  **usersNew** >  Lync Server User，然后单击添加 **。**

6. 在“搜索用户”框中，键入所需 Active Directory 用户帐户的完整的名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、电子邮件地址、用户主体名称 (UPN) 或电话号码，或这些内容的第一部分，然后单击“查找”。

7. 在表中，选择要添加到帐户Skype for Business Server然后单击"确定 **"**。

8. 将该用户分配给某个池，指定其他任何详细信息，并向所需用户分配策略，然后单击“启用”。

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>禁用或重新启用用户帐户进行Skype for Business Server

可以使用以下过程在 Skype for Business Server禁用以前启用的用户帐户Skype for Business Server为用户帐户配置的所有设置。 由于不会丢失Skype for Business Server用户帐户设置，因此可以重新启用以前启用的用户帐户，而无需重新配置用户帐户。

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>使用新的控制面板禁用或重新启用用户帐户

1. 打开浏览器窗口并输入管理 URL 以打开Skype for Business Server控制面板。
 
2. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录。

3. 在左窗格中，选择" **用户"**。

4. 在" **用户"** 页上的"搜索 **"框中，** 键入搜索的所有部分或第一显示名称按 **Enter**。

5. 在表中，双击要禁用或重新启用的用户帐户。
    1. 在出现的面板中，若要暂时禁用用户帐户Skype for Business Server，请选择"禁用 **用户"**。 在出现的面板中，单击"保存 **"**。
    2. 若要重新为用户帐户启用Skype for Business Server，请在面板中选择"重新 **启用用户"**。 在出现的下一个面板中，单击"保存 **"**。

> [!NOTE]
> 新控制面板不适用于 2015 Skype for Business Server控制面板。

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>使用旧版控制面板禁用或重新启用用户帐户

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左窗格中，选择" **用户"**。

4. 在“搜索用户”框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5. 在表中，单击要禁用或重新启用的用户帐户。

6. 在“操作”菜单上，执行下列操作之一：
   1. 若要暂时禁用用户的用户帐户Skype for Business Server，请选择"**暂时禁用 Lync Server"**。
   2. 若要为用户帐户启用Skype for Business Server，请选择 **"重新启用 Lync Server"**。
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>使用管理程序禁用或重新启用Windows PowerShell

可以使用 **Set-CsUser** cmdlet 暂时禁用用户帐户，稍后再重新启用。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在 Skype for Business Server 中Skype for Business Server。

### <a name="to-disable-a-user-account-using-windows-powershell"></a>若要禁用用户帐户，请Windows PowerShell

- 若要暂时禁用用户帐户，将 enabled 属性的值设置为 False ($False) 。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>使用"设置"功能重新启用Windows PowerShell

- 若要重新启用已禁用的用户帐户，将 enabled 属性的值设置为 True ($True) 。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

有关详细信息，请参阅 [Set-CsUser](/powershell/module/skype/set-csuser) cmdlet 的帮助主题。

## <a name="disable-a-user-for-enterprise-voice"></a>为用户禁用企业语音

使用以下过程禁用企业语音启用的用户帐户Skype for Business Server。

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>使用新的控制面板企业语音禁用用户登录

1. 打开浏览器窗口并输入管理 URL 以打开Skype for Business Server控制面板。
 
2. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录。

3. 在左窗格中，单击"用户 **"**。

4. 在" **搜索** "框中，键入搜索的所有部分或第一显示名称然后单击"查找 **"**。

5. 在表中，双击要禁用该帐户的用户帐户企业语音。

6. 在出现的面板中，单击"分配的策略"旁边的 **铅笔图标**。

7. 在"**分配的策略"** 面板 **中的"电话**"下，单击下拉列表 **企业语音选项之外** 的任何选项。

8. 单击“**保存**”。

    > [!NOTE]
    > 若要限制用户进行音频或视频呼叫，请在"电话"下单击"**禁用音频/视频"**。

用户现在无法使用企业语音功能。 

> [!NOTE]
> 新控制面板不适用于 2015 Skype for Business Server控制面板。

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>使用旧版控制面板企业语音用户帐户进行登录

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左窗格中，单击"用户 **"**。

4. 在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5. 在表中，单击要为此帐户启用的企业语音。

6. 在“编辑”菜单上，单击“显示详细信息”。

7. 在“编辑 Lync Server 用户”页的“电话”下，单击“企业语音”。

    > [!NOTE]
    > 若要限制用户使用 Lync 进行音频或视频呼叫，请在"电话"下单击"禁用 **音频/视频"**。

8. 单击“提交”。

用户现在无法使用企业语音功能。

相关信息： <br/>[企业语音移动性](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [在用户企业语音Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 命令行管理程序](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server用户帐户

可以使用以下过程删除以前在 Skype for Business Server 中添加的用户帐户。

> [!NOTE]
> 移除用户将导致您丢失为用户帐户配置的所有设置。 如果要临时禁用用户帐户，请参阅禁用或重新启用以前为用户帐户启用[Skype for Business Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)。

### <a name="remove-a-user-using-the-new-control-panel"></a>使用新的控制面板删除用户

1. 打开浏览器窗口并输入管理 URL 以打开Skype for Business Server控制面板。
 
2. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录。

3. 在左窗格中，选择" **用户"**。

4. 在" **搜索** "框中，键入搜索的所有部分或第一显示名称然后单击"查找 **"**。

5. 在表中，双击要删除的用户帐户。

6. 在出现的面板中，单击"删除 **用户"**。 在出现的下一个面板中，单击"确定 **"**。

> [!NOTE]
> 新控制面板不适用于 2015 Skype for Business Server控制面板。

### <a name="remove-a-user-using-the-legacy-control-panel"></a>使用旧版控制面板删除用户

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左窗格中，选择" **用户"**。

4. 在"搜索用户"框中，键入要删除的用户帐户的 显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的所有或第一部分，然后单击 **"查找"**。

5. 在表中，单击要移除的用户帐户。

6. 在“操作”菜单上，选择“从 Lync Server 中删除”，然后将出现一个对话框。

7. 从该对话框中，选择“确定”来移除该用户。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>使用 cmdlet 删除Windows PowerShell用户帐户

您可以使用 Disable-CsUser cmdlet 删除用户帐户。 可以从命令行管理程序或远程Skype for Business Server命令行管理程序运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在 Skype for Business Server 中Skype for Business Server。

若要移除用户帐户，请使用 Disable-CsUser cmdlet。例如：

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

在此命令运行后，没有办法重新启用该帐户及其以前的设置。您将需要使用 Enable-CsUser cmdlet 为 Ken Myer 创建全新的帐户。

有关详细信息，请参阅 [Disable-CsUser](/powershell/module/skype/disable-csuser) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
