---
title: 自定义 Skype for Business 服务器的用户帐户属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 你可以使用本部分中的过程修改单个用户帐户属性。
ms.openlocfilehash: eca88717d0b81ddd7c27fc140df9bdbf7590c5c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991427"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>自定义 Skype for Business 服务器的用户帐户属性
 
你可以使用本部分中的过程修改单个用户帐户属性。
  
可以在单个用户级别执行两项基本操作：
  
- [为特定用户帐户配置电话选项](customize-properties.md#Tel_Op)
    
- [将用户移动到另一个池](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>为特定用户帐户配置电话选项
<a name="Tel_Op"> </a>

你可以自定义特定用户的电话设置（只要个人用户已启用 Skype for business 服务器且组织支持电话服务）。
  
Skype for business 服务器用户电话选项包括以下内容：
  
- **音频/视频已禁用**用户无法使用音频和视频进行呼叫。
    
- **仅适用于 pc 到 pc**用户只能进行 PC 到 PC 的音频或视频通话。
    
- **企业语音**用户可以使用 Skype for Business 服务器基础结构路由所有传入和传出呼叫。 用户还可以进行 PC 到 PC 呼叫。
    
- **远程呼叫控制**用户可以使用 Skype for Business 服务器控制桌面电话，也可以进行 PC 到 PC 的通话。
    
有关为组织配置电话的详细信息，请参阅在 "skype for business"[服务器中启用企业语音的用户](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)，并在部署文档中[部署 Skype for business 服务器中的企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左导航栏中，单击“用户”****。
    
4. 在 "**搜索用户**" 框中，键入所需用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。
    
5. 在表中，单击要修改的用户帐户。
    
6. 在 "**编辑**" 菜单上，单击 "**修改**"。
    
7. 在**电话服务**中，执行以下操作：
    
   - 若要为用户禁用音频和视频呼叫，请单击 "**音频/视频已禁用**"。
    
   - 若要为用户启用 PC 至 PC 音频通信，但不支持远程呼叫控制或企业语音，请单击 "**仅 pc 到 pc**"。 为用户用于 PC 到 PC 音频通信的电话指定**行 URI**的值。
    
   - 若要根据服务策略类别（包括 PC 到 PC 音频通信）使用 Skype for Business 基础结构路由用户的电话呼叫，请单击 "**企业语音**"。 在 "**行 URI**" 中，指定企业语音的电话号码。 在 "**拨号计划策略**" 和 "**语音策略**" 中，为用户指定适当的策略。 若要指定将用户拨打的电话号码转换为电子164格式的规范化规则，请在 "**位置策略**" 中选择相应的位置配置文件。
    
   - 要启用 "远程呼叫控制"，使用户能够从 Skype for Business 服务器控制其桌面电话线路，以进行 PC 到 PC 呼叫和 PC 至电话呼叫，请单击 "**远程呼叫控制**"。 在 "**行 URI**" 中，指定远程呼叫控制的电话号码。 用户必须具有桌面电话和专用分支 exchange （PBX）连接才能使用呼叫路由。
    
## <a name="move-users-to-another-pool"></a>将用户移动到另一个池
<a name="Move_Users"> </a>

可以使用 Skype for Business 服务器控制面板将用户分配到特定的服务器或池。
  
> [!TIP]
> 将所有现有用户从运行 Lync Server 2010 或更早版本的源池中移动到复杂的 Active Directory 环境中的 Skype for business 服务器目标池可能会导致 Active Directory 复制速度较慢。 为避免这种情况，您可以使用搜索筛选器从运行 Lync Server 2010 或更早版本的池中移动用户，也可以使用 Skype for Business Server Management Shell 将用户与 cmdlet 一起移动。 此外，筛选器功能可与 Skype for Business 服务器用户配合使用。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>将所选用户移动到其他服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 在 "**搜索用户**" 框中，键入所需用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。 
    
5. 在表中，选择列表中的特定用户或用户。 
    
6. 在 "**操作**" 菜单上，单击 "**将所选用户移至池**"。
    
7. 在 "**移动用户**" 中，选择要将用户移动到 "**目标注册机构" 池中**的池。
    
8. 可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    > [!CAUTION]
    > 如果您选择 "**强制**"，则用户帐户将被移动，但任何相关联的用户数据（例如，用户已安排的会议）都将被删除。 如果不选择该帐户，将同时移动帐户和关联的数据。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移动到另一个服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 在 "**操作**" 菜单上，单击 "**将所有用户移至池**"。
    
5. 在 "**移动用户**" 中，选择包含要在**源注册机构池中**移动的用户帐户的池。
    
6. 在 "**目标注册机构" 池中**，选择要将用户移动到的池。
    
7. 可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    > [!CAUTION]
    > 如果您选择 "**强制**"，则用户帐户将被移动，但任何相关联的用户数据（例如，用户已安排的会议）都将被删除。 如果不选择该帐户，将同时移动帐户和关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用筛选器将用户从一个池移动到另一个池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左导航栏中，单击“用户”****。
    
4. 在 "**用户搜索**" 中，单击 "**搜索**"，然后单击 "**添加筛选器**"。
    
5. 在搜索条件中，选择 "**注册机构池**"，选择 "**等于**"，选择 "**当前池 FQDN**"，然后单击 "**查找**"。
    
6. 在 "**操作**" 菜单上，单击 "**将所有用户移至池**"。
    
    > [!NOTE]
    > 将筛选器应用于现有用户集时，选项 "**将所有用户移至池中**" 将位于已筛选的用户子集的上下文中，而不是**所有**可能的用户。
  
7. 在 "**移动用户**" 中，选择包含要在**源注册机构池中**移动的用户帐户的池。
    
8. 在 "**目标注册机构" 池中**，选择要将用户移动到的池。
    
9. 可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    > [!CAUTION]
    > 如果您选择 "**强制**"，则用户帐户将被移动，但任何相关联的用户数据（例如，用户已安排和联系人的会议）都将被删除。 如果不选择该帐户，将同时移动帐户和关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows Powershell cmdlet 将用户从一个池移动到另一个池

1. 根据你运行的 Windows PowerShell 命令（本地或远程）的运行方式，你需要以正确的 Skype for Business 服务器管理角色的成员身份登录，如下所示：
    
   a. 如果你在本地计算机上运行命令（例如，直接登录前端服务器）：登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或使用**委派设置权限**中所述的必要用户权限。
    
   b. 如果您在另一台计算机上远程运行命令（例如，登录到计算机并在标准版前端服务器上远程运行命令）：从分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户。角色，请登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business 服务器命令行管理程序：单击 "**开始**"，单击 "**所有程序**"，单击 " **skype**for Business"，然后单击 " **skype for business 服务器管理外壳**"。
    
3. 若要移动单个用户，请使用 Move-csuser cmdlet，如下所示：
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    要移动的用户是用户 Pilar Ackerman，用户将从其当前分配的主池移动到该池 pool01.contoso.net
    
4. 若要移动大量用户，请将筛选器与**move-csuser** cmdlet 配合使用，并将生成的用户集传递到**move-csuser**：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Move-csuser**和**move-csuser**的合并命令可能会导致以下情况：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


