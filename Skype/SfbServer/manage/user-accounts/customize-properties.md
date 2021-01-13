---
title: 自定义 Skype for Business Server 的用户帐户属性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826262"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>自定义 Skype for Business Server 的用户帐户属性
 
您可以使用本节中的过程修改单个用户帐户属性。
  
可以在单个用户级别执行两个基本操作：
  
- [为特定用户帐户配置电话选项](customize-properties.md#Tel_Op)
    
- [将用户移动到另一个池](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>为特定用户帐户配置电话选项
<a name="Tel_Op"> </a>

你可以为特定用户自定义电话设置 (只要为单个用户启用了 Skype for Business Server，并且组织支持电话服务) 。
  
Skype for Business Server 用户电话选项包括：
  
- **禁用音频/视频** 用户无法使用音频和视频进行呼叫。
    
- **仅 PC 到 PC** 用户只能进行 PC 到 PC 音频或视频呼叫。
    
- **企业语音** 用户可以使用 Skype for Business Server 基础结构路由所有传入和传出呼叫。 用户还可以进行 PC 到 PC 呼叫。
    
- **远程呼叫控制** 用户可以使用 Skype for Business Server 控制桌面电话，还可以进行 PC 到 PC 呼叫。
    
有关为组织配置电话的详细信息，请参阅部署文档中的"在 Skype for Business Server 中为用户启用[企业语音，](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)在 Skype for Business Server 中部署[企业语音。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在 **“搜索用户”** 框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击 **“查找”**。
    
5. 在表中，单击要修改的用户帐户。
    
6. 在“编辑”菜单上，单击“修改”。
    
7. 在“电话”中，执行下列操作：
    
   - 要为用户禁用音频和视频呼叫，请单击“禁用音频/视频”。
    
   - 要为用户启用 PC 到 PC 音频通信，但不启用远程呼叫控制或企业语音，请单击“仅限 PC 到 PC”。为用户用于进行 PC 到 PC 音频通信的电话指定“线路 URI”值。
    
   - 若要根据服务策略类别（包括 PC 到 PC 音频通信）使用 Skype for Business 基础结构路由用户电话呼叫，请单击 **企业语音。** 在“线路 URI”中，指定用于企业语音的电话号码。 在“拨号计划策略”和“语音策略”中，为用户指定相应的策略。 要指定用于将用户拨打的电话号码转换为 E.164 格式的规范化规则，请在“位置策略”中选择相应的位置配置文件。
    
   - 若要启用远程呼叫控制，从而使用户能够控制其桌面电话线路从 Skype for Business Server 进行 PC 到 PC 呼叫和 PC 到电话呼叫，请单击 **"远程呼叫控制"。** 在“线路 URI”中，指定用于远程呼叫控制的电话号码。 要进行呼叫路由，用户必须具有桌面电话和专用交换机 (PBX) 连接。
    
## <a name="move-users-to-another-pool"></a>将用户移动到另一个池
<a name="Move_Users"> </a>

可以使用 Skype for Business Server 控制面板将用户分配到特定服务器或池。
  
> [!TIP]
> 将所有现有用户从运行 Lync Server 2010 或更早的源池移动到复杂 Active Directory 环境中 Skype for Business Server 目标池可能会导致 Active Directory 复制速度变慢。 为了避免这种情况，您可以使用搜索筛选器将用户从单独运行 Lync Server 2010 或更早版本池移动，或者可以使用 Skype for Business Server 命令行管理程序移动带 cmdlet 的用户。 此外，筛选器功能适用于 Skype for Business Server 用户。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>将所选用户移至其他服务器或池

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在“搜索用户”框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。 
    
5. 在表中，选择列表中的一个或多个特定用户。 
    
6. 在“操作”菜单中，单击“将所选用户移动到池”。
    
7. 在“移动用户”的“目标注册器池”中，选择要将用户移动到的池。
    
8. （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!CAUTION]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移至另一个服务器或池

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在“操作”菜单上，单击“将所有用户移动到池”。
    
5. 在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。
    
6. 在“目标注册器池”中，选择要将用户移动到的池。
    
7. （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!CAUTION]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用筛选器将用户从一个池移至另一个池

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击“用户”。
    
4. 在 **"用户搜索**"中，**单击"搜索**"，然后单击"**添加筛选器"。**
    
5. 在搜索条件中，依次选择“注册器池”、“等于”和“当前池 FQDN”，然后单击“查找”。
    
6. 在“操作”菜单上，单击“将所有用户移动到池”。
    
    > [!NOTE]
    > 将筛选器应用于现有用户组时，选项“将所有用户移动到池”出现在经过筛选的用户子集上下文中，而不是出现在 **所有** 可能的用户上下文中。
  
7. 在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。
    
8. 在“目标注册器池”中，选择要将用户移动到的池。
    
9. （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!CAUTION]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议和联系人）。如果不选中，将同时移动帐户和关联数据。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows Powershell cmdlet 将用户从一个池移动到另一个池

1. 根据运行 Windows PowerShell 命令 (（本地或远程) ）的不同，你需要以正确的 Skype for Business Server 管理角色成员登录，如下所示：
    
   a. 例如，如果在本地计算机上运行命令 (，请直接登录到前端服务器) ：以 RTCUniversalServerAdmins 组的成员或具有委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序的计算机。 
    
   b. 例如，如果在另一台计算机 (远程运行命令，请登录到计算机，在 Standard Edition 前端服务器) 上远程运行命令：从分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任意计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 若要移动单个用户，请按如下方式使用 Move-CsUser cmdlet：
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    其中，要移动的用户是用户 Pilar Ackerman，该用户将从当前分配的主池移至 pool01.contoso.net 池
    
4. 若要移动大量用户，请将筛选器与 **Get-CsUser** cmdlet 配合使用，并将生成的用户组传递给 **Move-CsUser**：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get-CsUser** 和 **Move-CsUser** 命令结合使用时可能如下所示：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


