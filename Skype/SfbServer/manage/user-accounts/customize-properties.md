---
title: 自定义业务服务器 Skype 的用户帐户属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: 1f2039180a2bfa44b3379f7cf6bf095e2d0a7c14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911831"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>自定义业务服务器 Skype 的用户帐户属性
 
您可以使用本节中的过程修改单个用户帐户属性。
  
有两个可在单个用户级别的基本操作：
  
- [配置特定的用户帐户的电话选项](customize-properties.md#Tel_Op)
    
- [将用户移动到另一个池](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>配置特定的用户帐户的电话选项
<a name="Tel_Op"> </a>

（前提是单个用户已启用的 Skype 业务服务器和组织支持电话），您可以自定义特定用户的电话设置。
  
Skype 的企业服务器用户电话选项包括：
  
- **禁用音频/视频**用户不能与呼叫音频和视频。
    
- **PC 到 PC 仅**用户可以发出仅限 PC 到 PC 音频或视频呼叫。
    
- **企业语音**用户可以使用 Business Server 基础结构 Skype 将所有传入和传出呼叫路由。 用户还可以发出 PC 到 PC 呼叫。
    
- **远程呼叫控制**用户可以使用 Skype 业务服务器来控制桌面电话，并还可以发出 PC 到 PC 呼叫。
    
有关配置为组织的电话的详细信息，请参阅部署文档中的[为 Skype 业务服务器中的企业语音用户启用](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)和[Skype 业务服务器中部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左导航栏中，单击“用户”****。
    
4. 在**搜索用户**框中键入所有或显示名称、 名字、 最后一个名称、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您希望，并单击**查找的用户帐户的统一资源标识符 (URI) 的第一部分**.
    
5. 在表中，单击要修改的用户帐户。
    
6. 在**编辑**菜单上，单击**修改**。
    
7. 在**电话**中，执行以下操作：
    
   - 若要禁用的用户的音频和视频呼叫，请单击**禁用音频/视频**。
    
   - 若要启用 PC 到 PC 音频通信的用户，但没有远程呼叫控制或企业语音，请单击**PC 到 PC 仅**。 指定的用户进行 PC 到 PC 音频通信使用的电话**线路 URI**值。
    
   - 若要将用户的电话呼叫路由使用的服务策略，包括 PC 到 PC 音频通信类按照业务基础结构 Skype 单击**企业语音**。 在**线路 URI**中，指定企业语音的电话号码。 在**拨号计划策略**和**语音策略**中，指定用户的相应策略。 若要指定转换为 E.164 格式的用户所拨打的电话号码的规范化规则，选择适当的位置配置文件**的位置策略**中。
    
   - 要启用远程呼叫控件，它使用户可以控制业务服务器进行 PC 到 PC 呼叫以及 PC 到电话的呼叫的 Skype 从其桌面电话线，单击**远程呼叫控制**。 在**线路 URI**中，指定远程呼叫控制的电话号码。 用户必须拥有桌面电话和专用交换机 (pbx) 连接的呼叫路由。
    
## <a name="move-users-to-another-pool"></a>将用户移动到另一个池
<a name="Move_Users"> </a>

您可以使用业务 Server Control Panel 的 Skype 将用户分配给特定服务器或池。
  
> [!TIP]
> 从正在运行 Lync Server 2010 的源池或更早版本的复杂的 Active Directory 环境中的业务服务器目标池 Skype 移动所有现有用户可能会导致速度较慢的 Active Directory 复制。 若要避免此问题，可以使用搜索筛选器从正在运行 Lync Server 2010 的池中移动用户或更早版本分别，或者您可以使用 Skype 的业务 Server 命令行管理程序移动用户通过 cmdlet。 此外，筛选器功能与 Skype 适用于企业服务器用户。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>将所选的用户移动到其他服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 在**搜索用户**框中键入所有或显示名称、 名字、 最后一个名称、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或行您希望，并单击**查找的用户帐户的统一资源标识符 (URI) 的第一部分**. 
    
5. 在表中，选择一个特定用户或列表中的用户。 
    
6. 在**操作**菜单中，单击**移动所选的用户移动到池**。
    
7. 在**移动用户**中，选择您想要将用户移动到的**目标注册器池**的池。
    
8. （可选）如果目标服务器或池不可用，则选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择**强制**，移动的用户帐户时，但任何关联的用户数据 （例如，用户已安排的会议） 中删除。 如果未选择它，移动帐户和关联的数据。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移至其他服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 在**操作**菜单中，单击**移动所有用户移动到池**。
    
5. 在**移动用户**中，选择包含您要在**源注册器池**移动的用户帐户的池。
    
6. 在**目标注册器池**，选择您想要将用户移动到池。
    
7. （可选）如果目标服务器或池不可用，则选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择**强制**，移动的用户帐户时，但任何关联的用户数据 （例如，用户已安排的会议） 中删除。 如果未选择它，移动帐户和关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>若要将用户从一个池移动到另一个池，使用筛选器

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左导航栏中，单击“用户”****。
    
4. 在**用户搜索**，单击**搜索**，然后单击**添加筛选器**。
    
5. 在搜索条件中，选择**注册器池**，选择**等于**、 选择**当前池 FQDN**，，然后单击**查找**。
    
6. 在**操作**菜单中，单击**移动所有用户移动到池**。
    
    > [!NOTE]
    > 当筛选器应用于现有一组用户，**移动到池的所有用户**是筛选子集的用户，不**所有**可能的用户的上下文中的选项。
  
7. 在**移动用户**中，选择包含您要在**源注册器池**移动的用户帐户的池。
    
8. 在**目标注册器池**，选择您想要移动的用户的池。
    
9. （可选）如果目标服务器或池不可用，则选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择**强制**，移动的用户帐户时，但任何关联的用户数据删除 （例如，用户已安排的会议和联系人）。 如果未选择它，移动帐户和关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>将用户从一个池移至另一个使用 Windows Powershell cmdlet

1. 根据如何运行 Windows PowerShell 命令的 （即 （本地还是远程），您需要以登录正确的 Skype 业务服务器管理角色的成员，如下所示：
    
   a. 如果要在本地计算机 （例如，您直接登录前端服务器） 上运行命令： 登录到计算机的业务 Server Management Shell 的 Skype 成员身份的 RTCUniversalServerAdmins 组或具有所需的安装**Delegate Setup Permissions**中所述的用户权限。
    
   b. 如果您要在另一台计算机上远程运行命令 （例如，您登录到您的计算机上，在 Standard Edition 前端服务器上远程运行命令）： 使用分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户角色，登录到内部部署中的任何计算机。
    
2. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。
    
3. 若要移动单个用户，请按以下方式使用 Move-csuser cmdlet:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    其中移动用户是用户 Pilar Ackerman，该用户将是从其当前分配主池移至 pool01.contoso.net
    
4. 若要移动大量用户，将筛选器与**Get-csuser** cmdlet，并将生成的用户组传递给**Move-csuser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get-csuser**和**Move-csuser**命令结合可能会导致此：
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


