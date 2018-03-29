---
title: 自定义业务服务器 2015年的 Skype 用户帐户属性
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 可以使用本节中的过程修改单个用户帐户属性。
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a>自定义业务服务器 2015年的 Skype 用户帐户属性
 
可以使用本节中的过程修改单个用户帐户属性。
  
有可以在单个用户级别完成的两个基本操作：
  
- [配置电话服务使用特定用户帐户的选项](customize-properties.md#Tel_Op)
    
- [将用户移动到其他池](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>配置电话服务使用特定用户帐户的选项
<a name="Tel_Op"> </a>

（前提是个人用户已启用的 Skype 业务服务器 2015年和组织支持电话服务），可以自定义特定用户的电话设置。
  
Skype 的业务用户电话选项如下所示：
  
- **音频/视频被禁用**用户不能调用带有音频和视频。
    
- **PC 到 PC 只**用户可仅 PC 到 PC 音频或视频通话。
    
- **企业语音**用户可以使用 Skype 业务服务器 2015年基础结构将所有传入和传出呼叫的路由。 用户还可以进行 PC 到 PC 的呼叫。
    
- **远程呼叫控制**用户可以使用 Skype 的业务服务器 2015年控制桌面电话，并且还可以进行 PC 到 PC 的调用。
    
有关配置电话服务组织的详细信息，请参阅部署文档中[启用企业语音中业务服务器 2015年的 Skype 的用户](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)和[业务服务器 2015年的 Skype 在部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**搜索用户**框中，键入全部或第一部分的显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您希望，并单击**查找行**.
    
5. 在表中，单击想要修改的用户帐户。
    
6. 在**编辑**菜单上，单击**修改**。
    
7. 在**电话服务**中，执行下列操作：
    
   - 若要禁用用户的音频和视频呼叫，请单击**禁用音频/视频**。
    
   - 若要启用 PC 到 PC 的音频通信的用户，但没有远程呼叫控制或企业语音，请单击**PC 到 PC 只**。 为用户对 PC 到 PC 的音频通信电话**线路**uri 中指定一个值。
    
   - 若要将用户的电话路由通过 Skype 业务基础结构的服务策略，包括 PC 到 PC 的音频通信类根据单击**企业语音**。 在**行的 URI**，指定企业语音的电话号码。 在**拨号计划策略**和**语音策略**，指定用户的相应策略。 若要指定用于转换为 E.164 格式的用户拨入的电话号码规范化规则，选择适当的位置配置文件**位置策略**中。
    
   - 若要启用远程调用控件，使用户能够控制从 Skype 的业务服务器 2015 进行 PC 到 PC 的呼叫和 PC 到电话的呼叫其桌面电话线路，请单击**远程呼叫控制**。 在**行的 URI**，指定远程呼叫控制的电话号码。 用户必须具有桌面电话和专用分组交换机 (PBX) 连接以将呼叫路由。
    
## <a name="move-users-to-another-pool"></a>将用户移动到其他池
<a name="Move_Users"> </a>

Skype 业务服务器控件面板用于将用户分配到特定的服务器或池。
  
> [!TIP]
> 将所有现有用户移动源库运行 Lync Server 2010 中或更早版本复杂的活动目录环境中的业务服务器 2015年目标池的 Skype 可能会导致速度慢的 Active Directory 复制。 若要避免此问题，可以使用搜索筛选器从池中正在运行 Lync Server 2010 中的移动用户或前面单独设置，也可以使用 Skype 业务服务器管理外壳为移动用户提供 cmdlet。 同时，筛选器功能与 Skype 业务服务器 2015年用户工作。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>若要将选定的用户移动到其他服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**搜索用户**框中，键入全部或第一部分的显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您希望，并单击**查找行**. 
    
5. 在表中，选择某一特定用户或用户列表中。 
    
6. 在**操作**菜单上，单击**移动到池的所选的用户**。
    
7. 在**移动用户**选择您想要将用户移动到**目标注册**池中的池。
    
8. （可选）如果目标服务器或池不可用，请选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择了**强制**，移动用户帐户，但删除任何关联的用户数据 （例如，用户已安排的会议）。 如果不选取它，移动帐户和相关联的数据。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移动到其他服务器或池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**操作**菜单上，单击**移动到池中的所有用户**。
    
5. 在**移动用户**选择包含您想要在**源池注册器**中移动用户帐户的池。
    
6. 在**目标注册池**，选择您想要将用户移动到的池。
    
7. （可选）如果目标服务器或池不可用，请选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择了**强制**，移动用户帐户，但删除任何关联的用户数据 （例如，用户已安排的会议）。 如果不选取它，移动帐户和相关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>若要使用筛选器将用户从一个池移动到其他池

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在**用户搜索**中，单击**搜索**，然后单击**添加筛选器**。
    
5. 在搜索条件中，选择**注册池**，选择**等于**，选择**当前池的 FQDN**，，然后单击**查找**。
    
6. 在**操作**菜单上，单击**移动到池中的所有用户**。
    
    > [!NOTE]
    > 当筛选器应用于一组现有用户中，**移动到池中的所有用户**将筛选出的那部分用户，没有**所有**可能的用户的上下文中的选项。
  
7. 在**移动用户**选择包含您想要在**源池注册器**中移动用户帐户的池。
    
8. 在**目标注册池**，选择您想要移动用户的池。
    
9. （可选）如果目标服务器或池不可用，请选择**强制**复选框。
    
    > [!CAUTION]
    > 如果选择了**强制**，移动用户帐户，但任何关联的用户数据则会删除 （例如，用户已计划的会议和联系人）。 如果不选取它，移动帐户和相关联的数据。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>若要将用户从一个池移动到另一个使用 Windows Powershell cmdlet

1. 这取决于如何运行 Windows PowerShell 命令时 （即本地或远程），您需要登录正确 Skype 业务服务器 2015年管理角色的成员，如下所示：
    
   a. 如果本地计算机 （例如，登录直接到前端服务器） 上运行这些命令： 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或具有所需的安装位置的计算机所述**代理安装程序权限**的用户权限。
    
   b. 如果您正在另一台计算机上远程运行命令 （例如，您登录到您的计算机上，在标准版前端服务器上远程运行命令）： 从用户帐户分配到 CsUserAdministrator 角色或 CsAdministrator角色，登录到内部部署中的任何计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 要移动一个用户，使用移动 CsUser cmdlet，如下所示：
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    其中用户可以移动赵华，用户和用户将会从移动他们当前已分配的主池到池 pool01.contoso.net
    
4. 若要移动大量的用户，对**Get CsUser** cmdlet 使用筛选器和传递到**移动 CsUser**得到的用户集：
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **获得 CsUser**和**移动 CsUser**的组合的命令可能会导致于：
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


