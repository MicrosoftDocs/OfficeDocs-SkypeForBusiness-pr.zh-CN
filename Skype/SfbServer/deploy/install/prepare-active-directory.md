---
title: 为 Skype for business 服务器准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '摘要: 了解如何为安装 Skype for Business 服务器准备 Active Directory 域。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 304887bdd6096b70c8d4d7b50f404f144f869859
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306596"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>为 Skype for business 服务器准备 Active Directory
 
**摘要:** 了解如何为 Skype for business 服务器的安装准备 Active Directory 域。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。
  
Skype for business 服务器与 Active Directory 密切协作。 必须准备 Active Directory 域才能使用 Skype for Business 服务器。 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 准备 Active Directory 是 8 个步骤中的第 4 步。 有关规划 Active Directory 的详细信息, 请参阅适用于 Skype for business Server 2019 的 Skype for business 服务器或[服务器要求](../../../SfBServer2019/plan/system-requirements.md)[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>准备 Active Directory

Skype for business 服务器与 Active Directory 域服务 (AD DS) 紧密集成。 第一次安装 Skype for Business 服务器之前, 必须准备 Active Directory。 名为 "**准备 Active directory** " 的部署向导部分准备了用于 Skype For business 服务器的 Active directory 环境。
  
> [!NOTE]
> Skype for Business 服务器使用 (AD DS) 跟踪拓扑中的所有服务器并与之通信。 每台服务器必须加入域, 以便 Skype for Business 服务器可以正常工作。 
  
> [!IMPORTANT]
> 应仅为部署中的每个域运行一次“准备 Active Directory”过程。 
  
观看“**准备 Active Directory**”视频了解相关步骤。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>通过部署向导准备 Active Directory

1. 以具备 Active Directory 域的 Schema Admins 凭证的用户身份登录。
    
2. 打开 Skype for Business 服务器部署向导。
    
    > [!TIP]
    > 如果你想要查看由 Skype for Business Server 部署向导创建的日志文件, 可以在运行该步骤的 AD DS 用户的用户目录中找到这些文件, 这些文件位于运行部署向导的计算机上。 例如, 如果用户在域中以域管理员的身份登录到本地登录, 则日志文件位于: C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 单击“**准备 Active Directory**”链接。
    
4. **第 1 步：准备架构**
    
    a. 检查第 1 步的先决条件信息，可单击第 1 步标题下的下拉菜单访问该信息。
    
    b. 单击第 1 步中的“**运行**”以启动“准备架构”向导。
    
    c. 请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。
    
    d. 准备好架构后，您可以单击“**查看日志**”以查看日志。 
    
    e.i. 单击“**完成**”以关闭“准备架构”向导，然后返回“准备 Active Directory”步骤。
    
5. **第 2 步：验证架构分区的复制**
    
    a. 登录到域的域控制器。
    
    b. 从“**服务器管理器**”中的“**工具**”下拉菜单打开“**ADSI Edit**”。
    
    c. 在“**操作**”菜单上，单击“**连接到**”。
    
    d. 在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。
    
    e.i. 在架构容器下，搜索“**CN=ms-RTC-SIP-SchemaVersion**”。 如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。 如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。
    
6. **第 3 步：准备当前林**
    
    a. 检查第 3 步的先决条件信息，可单击第 3 步标题下的下拉菜单访问该信息。
    
    b. 单击第 3 步中的“**运行**”以启动“准备当前林”向导。
    
    c. 请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。
    
    d. 指定将创建通用组的域。 如果服务器是组的一部分，您可以选择“**本地域**”，然后单击“**下一步**”。
    
    e.i. 准备好林后，您可以单击“**查看日志**”以查看日志。 
    
    f. 单击“**完成**”以关闭“准备当前林”向导，然后返回“准备 Active Directory”步骤。
    
    7. 单击 "**应用**" 页面上的 " **Skype For Business 服务器管理外壳**" 以启动 PowerShell。
    
    硬件. 键入命令 CsAdForest, 然后按**enter**。
    
    怎样. 如果结果为**LC_FORESTSETTINGS_STATE_READY**, 则林已成功做好准备, 如图所示。
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **第 4 步：验证全局目录的复制**
    
    a. 在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。
    
    b. 在“**Active Directory 用户和计算机**”中，展开林或子域的域名。
    
    c. 在左侧窗格中单击“**用户**”容器，在右侧窗格中查找通用组 **CsAdministrator**。 如果除其他以 Cs 开头的新通用组外还显示 CsAdministrator，则表明 Active Directory 的复制成功。
    
    d. 如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。 显示组后，表明复制完成。
    
8. **第 5 步：准备当前域**
    
    a. 查看第 5 步的先决条件信息
    
    b. 单击第 5 步中的“**运行**”以启动“准备当前域”向导。
    
    c. 请注意，应仅为部署中的每个域执行一次该过程，然后单击“**下一步**”。
    
    d. 准备好域后，您可以单击“**查看日志**”以查看日志。 
    
    e.i. 单击“**完成**”以关闭“准备当前域”向导，然后返回“准备 Active Directory”步骤。
    
    必须在每个找到 Skype for Business 服务器对象的域中完成这些步骤, 否则服务可能无法启动。 这包括任意类型的 Active Directory 对象，比如用户、联系人对象、管理组或其他任何类型的对象。 如果需要, 你可以使用 CsUserReplicatorConfiguration-ADDomainNamingContextList 仅添加具有 Skype for business 服务器对象的域。
    
9. **第 6 步：验证域中的复制**
    
    a. 从 "**应用**" 页面中单击 " **Skype For Business 服务器管理外壳**" 以启动 PowerShell。
    
    b. 使用命令 CsAdDomain 验证域内的复制。
    
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
  
    c. 如果结果为**LC_DOMAINSETTINGS_STATE_READY**, 则域已成功复制。
    
10. **第 7 步：添加用户以提供 Skype for Business Server 控制面板的管理访问权限**
    
    a. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
    b. 打开“**Active Directory 用户和计算机**”，展开域，单击“**用户**”容器，右键单击 CSAdministrator，然后选择“**属性**”。
    
    c. 在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。
    
    d. 在“**成员**”选项卡上，单击“**添加**”。 在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。 键入要添加到 CSAdministrators 组的用户名或组名。 单击“**确定**”。
    
    e.i. 在“**成员**”选项卡上，确认所选的用户或组存在。 单击“**确定**”。
    
    > [!CAUTION]
    > Skype for Business Server "控制面板" 是基于角色的访问控制工具。 CsAdministrator 组中的成员身份为所有可用的配置功能提供了使用 Skype for Business 服务器控制面板的 "完全控制"。 还有其他为特定功能设计的专门角色可用。 有关可用角色的详细信息, 请参阅 skype for business server 2019 的[环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 skype For business [Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 请注意, 用户不必启用 Skype for Business 服务器, 即可成为管理组的成员。 
  
    > [!CAUTION]
    > 若要帮助保留安全和基于角色的访问控制完整性, 请将用户添加到定义用户在管理 Skype for Business 服务器部署时所执行的角色的组。 
  
11. 注销, 然后重新登录到 Windows, 以便你的安全令牌通过新的 Skype for Business Server 安全组进行更新, 然后重新打开部署向导。
    
12. 验证“**准备 Active Directory**”旁边是否存在绿色对勾以确认过程取得成功，如图所示。
    
     ![Active Directory 准备工作已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另请参阅
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
