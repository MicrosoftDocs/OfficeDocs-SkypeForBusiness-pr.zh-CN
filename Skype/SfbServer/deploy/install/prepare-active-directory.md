---
title: 为 Skype for Business Server 2015 准备 Active Directory
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 准备 Active Directory
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 准备 Active Directory 是 8 个步骤中的第 4 步。 For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>准备 Active Directory

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> 应仅为部署中的每个域运行一次“准备 Active Directory”过程。 
  
观看“**准备 Active Directory**”视频了解相关步骤。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>通过部署向导准备 Active Directory

1. 以具备 Active Directory 域的 Schema Admins 凭证的用户身份登录。
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. 单击“**准备 Active Directory**”链接。
    
4. **Step 1: Prepare schema**
    
    a. 检查第 1 步的先决条件信息，可单击第 1 步标题下的下拉菜单访问该信息。
    
    b. 单击第 1 步中的“**运行**”以启动“准备架构”向导。
    
    c. 请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。
    
    d. 准备好架构后，您可以单击“**查看日志**”以查看日志。 
    
    e. 单击“**完成**”以关闭“准备架构”向导，然后返回“准备 Active Directory”步骤。
    
5. **Step 2: Verify replication of schema partition**
    
    a. 登录到域的域控制器。
    
    b. 从“**服务器管理器**”中的“**工具**”下拉菜单打开“**ADSI Edit**”。
    
    c. 在“**操作**”菜单上，单击“**连接到**”。
    
    d. 在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。
    
    e. 在架构容器下，搜索“**CN=ms-RTC-SIP-SchemaVersion**”。 如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。 如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。
    
6. **Step 3: Prepare current forest**
    
    a. 检查第 3 步的先决条件信息，可单击第 3 步标题下的下拉菜单访问该信息。
    
    b. 单击第 3 步中的“**运行**”以启动“准备当前林”向导。
    
    c. 请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。
    
    d. 指定将创建通用组的域。 如果服务器是组的一部分，您可以选择“**本地域**”，然后单击“**下一步**”。
    
    e. 准备好林后，您可以单击“**查看日志**”以查看日志。 
    
    f. 单击“**完成**”以关闭“准备当前林”向导，然后返回“准备 Active Directory”步骤。
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    a. 在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。
    
    b. 在“**Active Directory 用户和计算机**”中，展开林或子域的域名。
    
    c. 在左侧窗格中单击“**用户**”容器，在右侧窗格中查找通用组 **CsAdministrator**。 如果除其他以 Cs 开头的新通用组外还显示 CsAdministrator，则表明 Active Directory 的复制成功。
    
    d. 如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。 显示组后，表明复制完成。
    
8. **Step 5: Prepare the current domain**
    
    a. 查看第 5 步的先决条件信息
    
    b. 单击第 5 步中的“**运行**”以启动“准备当前域”向导。
    
    c. 请注意，应仅为部署中的每个域执行一次该过程，然后单击“**下一步**”。
    
    d. 准备好域后，您可以单击“**查看日志**”以查看日志。 
    
    e. 单击“**完成**”以关闭“准备当前域”向导，然后返回“准备 Active Directory”步骤。
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. 这包括任意类型的 Active Directory 对象，比如用户、联系人对象、管理组或其他任何类型的对象。 You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    a. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    b. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > 如果不指定 Domain 参数，则将该值设置为本地域。 
  
    为 contoso.local 域运行命令的示例：
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > 通过使用参数 GlobalSettingsDomainController，您可以指出存储全局设置的位置。如果设置存储在“系统”容器中（在全局设置尚未迁移到“配置”容器的升级部署中时通常是这种情况），则定义 AD DS 林的根中的某个域控制器。如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。 
  
    c. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    a. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
    b. 打开“**Active Directory 用户和计算机**”，展开域，单击“**用户**”容器，右键单击 CSAdministrator，然后选择“**属性**”。
    
    c. 在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。
    
    d. 在“**成员**”选项卡上，单击“**添加**”。 在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。 键入要添加到 CSAdministrators 组的用户名或组名。 单击“**确定**”。
    
    e. 在“**成员**”选项卡上，确认所选的用户或组存在。 单击“**确定**”。
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. 为特定功能提供了其他专门的角色。 For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. 验证“**准备 Active Directory**”旁边是否存在绿色对勾以确认过程取得成功，如图所示。
    
     ![Active Directory 准备工作已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

