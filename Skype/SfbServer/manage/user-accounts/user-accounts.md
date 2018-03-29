---
title: 管理用户帐户的 Skype 业务服务器 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文各部分描述如何启用、 暂时禁用或删除 Active Directory 用户 Skype 业务服务器 2015年个。
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a>管理用户帐户的 Skype 业务服务器 2015
 
本文各部分描述如何启用、 暂时禁用或删除 Active Directory 用户 Skype 业务服务器 2015年个。
  
有关如何启用 Active Directory 用户的信息，请参阅[创建新用户帐户](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。 有关如何删除 Active Directory 用户的信息，请参阅[删除用户帐户](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。
  
维护期间，应执行这些过程，供业务使用 Skype 时最低。 这完成每日或每周的时间表取决于组织的需要。 
  
本文包含以下过程：
  
- [若要搜索一个或多个用户](user-accounts.md#Search)
    
- [添加并启用新的 Skype 业务服务器 2015年用户](user-accounts.md#Add)
    
- [禁用或重新启用以前为 Skype 业务服务器启用用户帐户](user-accounts.md#Disable)
    
- [禁用用户的企业语音](user-accounts.md#Disable_EV)
    
- [删除业务服务器管理外壳有 Skype 的用户帐户](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a>若要搜索一个或多个用户
<a name="Search"> </a>

搜索查询的结果可用于配置业务服务器 2015年的 Active Directory 用户 Skype。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。
  
可以搜索用户使用 Skype 业务服务器控件面板或 Active Directory 用户和计算机管理单元中。 下面的过程介绍如何使用 Skype 业务服务器的控制面板来搜索用户。
  
> [!NOTE]
> 在与中央林拓扑环境中，搜索结果可能不准确时由用户的电子邮件地址搜索用户。 相反，您可以通过指定 SIP 地址前缀，例如，sip： 名称来搜索用户、 添加搜索筛选器和选择 SIP 地址包含一个部分的电子邮件地址，或使用**Get CSUser** cmdlet。
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 SAM 帐户名的第一部分中，SIP 地址，或线形 URI 以搜索，然后单击**查找**所需的用户帐户。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击上面的**搜索结果**，在屏幕的右上角的展开箭头按钮，然后单击**添加筛选器**。
    
   b. 通过键入或单击下拉列表中选择一个用户属性中的箭头来输入用户属性。
    
   c. 在**等于**列表中单击**等于**或**不等于**。
    
   d. 在文本框中，键入要用来筛选搜索结果的搜索条件，然后单击**查找**。
    
6. 搜索结果将显示在**搜索结果**下。 可以选择任何或所有用户的列表中，并在您都选择的用户上执行配置任务。
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a>添加并启用新的 Skype 业务服务器 2015年用户
<a name="Add"> </a>

启用 Active Directory 用户和计算机中的用户帐户之后, 可以使用 Skype 业务服务器的控制面板来创建并启用新 Skype 业务服务器 2015年用户帐户通过 Active Directory 用户向 Skype 的业务服务器 2015年。
  
您还可以使用 cmdlet，专门[启用 CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左导航栏中，单击“**用户**”。
    
4. 单击**启用用户**。
    
5. 在**新的 Lync Server 用户**对话框中，单击**添加**。
    
6. 在**搜索用户**框中，键入全部或名称的第一部分，显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名称、 电子邮件地址、 用户主体名称 (UPN) 或 Active Directory 用户帐户所需的电话号码然后单击**寻找**。
    
7. 在表中，选择您想要添加到 Skype 的业务服务器 2015，的帐户，然后单击**确定**。
    
8. 将用户分配到池、 指定任何附加的详细信息，并将策略分配到用户所需，，然后单击**启用**。
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>禁用或重新启用以前为 Skype 业务服务器启用用户帐户
<a name="Disable"> </a>

可以使用下面的过程而不会丢失您为用户帐户配置的业务服务器设置为 Skype 业务服务器禁用 Skype 在以前已启用的用户帐户。 因为您不会丢失业务服务器用户帐户设置的 Skype，您可以重新启用以前已启用的用户帐户再次而无需重新配置用户帐户。 
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您想要禁用或重新启用，行的第一个部分中然后单击**查找**。
    
5. 在表中，单击您想要禁用或重新启用用户帐户。
    
6. 在**操作**菜单上，执行以下任一操作：
    
   - 要暂时禁用用户帐户 Skype 业务服务器，请单击**暂时禁用 Lync Server**。
    
   - 若要启用业务服务器的 Skype 的用户帐户，请单击**重新启用的 Lync Server**。
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows Powershell 禁用或重新启用用户帐户

用户帐户可以暂时禁用，然后稍后再重新启用，通过**一组 CsUser** cmdlet。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-disable-a-user-account"></a>要禁用用户帐户

- 若要暂时禁用用户帐户，请将已启用属性的值为 False ($False) 例如：
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>若要重新启用用户帐户

- 要重新启用已禁用的用户帐户，设置为 True ($True) 的已启用属性的值。 例如：
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

有关详细信息，请参阅[设置 CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="disable-a-user-for-enterprise-voice"></a>禁用用户的企业语音
<a name="Disable_EV"> </a>

使用以下过程禁用用户帐户启用的 Skype 业务服务器 2015年企业语音。
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a>针对企业语音禁用用户帐户

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。
    
5. 在表中，单击您想要启用的企业语音的用户帐户。
    
6. 在“编辑”****菜单上，单击“显示详细信息”****。
    
7. 在**编辑 Lync 服务器用户**页上，在**电话**中，单击除**企业语音**之外的任何选项。
    
    > [!NOTE]
    > 若要限制用户只能进行音频或视频呼叫使用 Lync 下**电话**，, 请单击**禁用音频/视频**。 
  
8. 单击“**提交**”。
    
现在，用户不能使用企业语音功能。 相关的信息： <br/>[企业语音和移动性](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [启用用户的 Skype 在企业语音的业务服务器 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype 的业务服务器 2015年管理外壳程序](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>删除业务服务器管理外壳有 Skype 的用户帐户
<a name="Remove"> </a>

可以使用以下过程可在 Skype 业务服务器 2015年移除以前添加的用户帐户。 
  
> [!NOTE]
> 删除用户将导致丢失您的用户帐户配置的任何设置。 如果您想要临时改为禁用的用户帐户，请参阅[禁用或重新启用以前为 Skype 业务服务器的已启用用户帐户](user-accounts.md#Disable)。 
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您想要禁用或重新启用，行的第一个部分中然后单击**查找**。
    
5. 在表中，单击要删除的用户帐户。
    
6. 在**操作**菜单，选择**从 Lync Server 中删除**，和一个对话框显示框。
    
7. 从对话框中，选择**确定**以删除用户。
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>删除用户帐户与 Windows Powershell cmdlet

通过禁用 CsUser cmdlet，您可以删除用户帐户。 从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行此 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-remove-a-user-account"></a>若要删除用户帐户
若要删除一个用户帐户，请使用禁用 CsUser cmdlet。 例如：
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
有关详细信息，请参阅[禁用 CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅
<a name="Remove"> </a>

#### 

[启用 CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[禁用-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

