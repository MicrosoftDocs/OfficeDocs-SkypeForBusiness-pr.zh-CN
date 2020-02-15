---
title: 为 Skype for business Server 准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：了解如何准备 Active Directory 域以安装 Skype for business Server。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018173"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>为 Skype for business Server 准备 Active Directory
 
**摘要：** 了解如何准备 Active Directory 域以安装 Skype for business Server。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business Server 的免费试用版。
  
Skype for Business Server 与 Active Directory 紧密协作。 您必须准备 Active Directory 域才能与 Skype for Business Server 配合使用。 此过程在部署向导中完成，仅对域执行一次。 这是因为该过程会创建组并修改域，您只需执行一次此操作。 您可以按任意顺序执行步骤1至5。 但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 准备 Active Directory 是第4步（共8步）。 有关规划 Active Directory 的详细信息，请参阅 skype [for Business server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>准备 Active Directory

Skype for Business Server 与 Active Directory 域服务（AD DS）紧密集成。 在第一次可以安装 Skype for Business Server 之前，必须准备 Active Directory。 部署向导中名为 "**准备 Active directory** " 的部分准备 active directory 环境以用于 Skype For business Server。
  
> [!NOTE]
> Skype for Business Server 使用（AD DS）跟踪拓扑中的所有服务器并与之通信。 这些服务器中的大多数必须加入域，以便 Skype for Business Server 能够正常工作。 请注意，边缘和反向代理等服务器不应加入域。
  
> [!IMPORTANT]
> 对于部署中的每个域，应仅运行一次 "准备 Active Directory" 过程。 
  
观看**准备 Active Directory**的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>通过部署向导准备 Active Directory

1. 以具有 Active Directory 域的架构管理员凭据的用户身份登录。
    
2. 打开 Skype for Business Server 部署向导。
    
    > [!TIP]
    > 如果要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行此步骤的 AD DS 用户的用户目录中的 "部署向导" 所在的计算机上找到这些文件。 例如，如果用户以域管理员的身份登录到本地域，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 单击 "**准备 Active Directory** " 链接。
    
4. **步骤1：准备架构**
    
    a. 查看步骤1的先决条件信息，可通过单击 "步骤 1" 标题下的下拉箭头来访问。
    
    b. 单击步骤1中的 "**运行**" 以启动 "准备架构" 向导。
    
    c. 请注意，每个部署应仅运行一次该过程，然后单击 "**下一步**"。
    
    d. 准备好架构后，可以通过单击 "**查看日志**" 来查看日志。 
    
    e. 单击 "**完成**" 以关闭 "准备架构" 向导，然后返回到 "准备 Active Directory" 步骤。
    
5. **步骤2：验证架构分区的复制**
    
    a. 登录到域的域控制器。
    
    b. 从 "**服务器管理器**" 的 "**工具**" 下拉菜单中打开 " **ADSI 编辑**"。
    
    c. 在 **“操作”** 菜单上，单击 **“连接到”**。
    
    d. 在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。
    
    e. 在 "架构" 容器下，搜索 " **CN = ms-SIP-SchemaVersion**"。 如果该对象存在，并且**rangeUpper**属性的值为1150，并且**rangeLower**属性的值为3，则该架构已成功更新和复制。 如果此对象不存在，或者**rangeUpper**和**rangeLower**属性的值不是指定的，则不会修改架构或未对其进行复制。
    
6. **步骤3：准备当前林**
    
    a. 查看步骤3的先决条件信息，可通过单击步骤3标题下的下拉菜单访问该信息。
    
    b. 单击步骤3中的 "**运行**" 以启动 "准备当前林" 向导。
    
    c. 请注意，每个部署的过程应仅运行一次，然后单击 "**下一步**"。
    
    d. 指定将在其中创建通用组的域。 如果服务器是域的一部分，则可以选择 "**本地域**"，然后单击 "**下一步**"。
    
    e. 准备好林后，可以通过单击 "**查看日志**" 来查看日志。 
    
    f. 单击 "**完成**" 以关闭 "准备当前林" 向导，然后返回到 "准备 Active Directory" 步骤。
    
    g. 从 "**应用程序**" 页上单击 " **Skype For Business Server Management Shell** " 以启动 PowerShell。
    
    水平. 键入命令 CsAdForest，然后按**enter**。
    
    得到. 如果结果是**LC_FORESTSETTINGS_STATE_READY**的，则表示已成功准备林，如图所示。
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **步骤4：验证全局编录的复制**
    
    a. 在域控制器上（最好是在来自其他域控制器的远程站点中），在运行林准备的林中，打开 " **Active Directory 用户和计算机**"。
    
    b. 在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。
    
    c. 单击左侧窗格中的 "**用户**" 容器，然后在右侧窗格中查找通用组**CsAdministrator** 。 如果 CsAdministrator （与以 Cs 开头的其他新通用组）存在，则表明 Active Directory 已成功复制。
    
    d. 如果这些组尚不存在，则可以强制进行复制，或等待15分钟并刷新右侧窗格。 显示组后，表明复制完成。
    
8. **步骤5：准备当前域**
    
    a. 查看步骤5的先决条件信息。
    
    b. 单击步骤5中的 "**运行**" 以启动 "准备当前域" 向导。
    
    c. 请注意，应仅为部署中的每个域运行一次该过程，然后单击 "**下一步**"。
    
    d. 准备好域后，可以通过单击 "**查看日志**" 来查看日志。 
    
    e. 单击 "**完成**" 关闭 "准备当前域" 向导，然后返回 "准备 Active Directory" 步骤。
    
    必须在找到 Skype for Business Server 对象的每个域中完成这些步骤，否则服务可能无法启动。 这包括任何类型的 Active Directory 对象，例如用户、联系人对象、管理组或任何其他类型的对象。 如果需要，可以使用 CsUserReplicatorConfiguration-ADDomainNamingContextList 仅添加具有 Skype for business Server 对象的域。
    
9. **步骤6：验证域中的复制**
    
    a. 单击 "**应用程序**" 页上的 " **Skype For Business Server Management Shell** " 以启动 PowerShell。
    
    b. 使用命令 CsAdDomain 验证域中的复制。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > 如果不指定 Domain 参数，则将该值设置为本地域。 
  
    为 contoso. 本地域运行命令的示例：
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > 通过使用参数 GlobalSettingsDomainController，可以指示存储全局设置的位置。 如果您的设置存储在系统容器中（这对于不将全局设置迁移到配置容器的升级部署来说很典型），则需要在 AD DS 林的根目录中定义域控制器。 如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。 如果不指定此参数，则 cmdlet 假定设置存储在配置容器中，并引用 Active Directory 中的任何域控制器。 
  
    c. 如果结果是**LC_DOMAINSETTINGS_STATE_READY**的，则域已成功复制。
    
10. **步骤7：添加用户以提供对 Skype for business Server 控制面板的管理访问权限**
    
    a. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
    b. 打开 " **Active Directory 用户和计算机**"，展开您的域，单击 "**用户**" 容器，右键单击 "CSAdministrator"，然后选择 "**属性**"。
    
    c. 在“CSAdministrator 属性”**** 中，单击“成员”**** 选项卡。
    
    d. 在"成员"选项卡上，单击"添加"。 在“选择用户、联系人、计算机、服务帐户或组”**** 中，找到“输入要选择的对象名称”****。 键入要添加到 CSAdministrators 组的用户名或组名。 单击“确定”****。
    
    e. 在 "**成员**" 选项卡上，确认所选的用户或组存在。 单击“确定”。
    
    > [!CAUTION]
    > Skype for Business Server 控制面板是基于角色的访问控制工具。 CsAdministrator 组中的成员身份为所有可用的配置功能提供了使用 Skype for Business Server 控制面板的 "完全控制" 权限的用户。 为特定功能提供了其他专门的角色。 有关可用角色的详细信息，请参阅 skype for business [server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 请注意，无需为 Skype for business Server 启用用户即可成为管理组的成员。 
  
    > [!CAUTION]
    > 若要帮助保留安全性和基于角色的访问控制完整性，请将用户添加到定义了用户在管理 Skype for Business Server 部署时所执行的角色的组。 
  
11. 注销，然后重新登录到 Windows，以便使用新的 Skype for Business Server 安全组更新您的安全令牌，然后重新打开部署向导。
    
12. 验证您是否在**准备 Active Directory**以确认成功时看到一个绿色的标记，如图所示。
    
     ![准备 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另请参阅
 
[适用于 Skype for business Server 2015 的 Active Directory 域服务](../../plan-your-deployment/security/active-directory-domain-services.md)
