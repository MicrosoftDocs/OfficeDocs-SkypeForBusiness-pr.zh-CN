---
title: Skype for Business Server：准备 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：了解如何准备 Active Directory 域以安装Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：。
ms.openlocfilehash: a4a224da84d1e6b4b001e9c561529b1c64b0e995
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609809"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype for Business Server：准备 Active Directory
 
**摘要：** 了解如何准备 Active Directory 域以安装Skype for Business Server。 从 Microsoft 评估中心Skype for Business Server[免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype for Business Server Active Directory 紧密工作。 必须准备 Active Directory 域，以使用Skype for Business Server。 此过程在部署向导中完成，并且仅对域执行一次。 这是因为此过程会创建组并修改域，并且只需执行一次。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按照图中的概述顺序执行步骤 6、7 和 8 以及步骤 1 到步骤 5 之后。 准备 Active Directory 是步骤 4/8。 有关规划 Active Directory 的信息，请参阅 Environmental [requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>准备 Active Directory

Skype for Business Server与 Active Directory 域服务 (AD DS) 。 在Skype for Business Server安装 Active Directory 之前，必须准备 Active Directory。 部署向导中标题为 **"准备 Active Directory"** 的部分准备 Active Directory 环境以用于Skype for Business Server。
  
> [!NOTE]
> Skype for Business Server使用 (AD DS) 跟踪拓扑中所有服务器并进行通信。 这些服务器中的大多数必须加入域，以便Skype for Business Server正常工作。 请记住，边缘和反向代理等服务器不应加入域。
  
> [!IMPORTANT]
> 应仅为部署中的每个域运行一次"准备 Active Directory"过程。 
  
观看准备 Active **Directory 的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>从部署向导准备 Active Directory

1. 以具有 Active Directory 域的架构管理员凭据的用户身份登录。
    
2. 打开Skype for Business Server部署向导"。
    
    > [!TIP]
    > 如果要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位置为运行该步骤的 AD DS 用户的 Users 目录。 例如，如果用户以域 contoso.local 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 单击" **准备 Active Directory"** 链接。
    
4. **步骤 1：准备架构**
    
    a. 查看步骤 1 的先决条件信息，可通过单击"步骤 1"标题下的下拉列表来访问这些信息。
    
    b. 单击 **步骤** 1 中的"运行"以启动"准备架构"向导。
    
    c. 请注意，对于每个部署，该过程只应运行一次，然后单击"下一步 **"。**
    
    d. 准备好架构后，可以通过单击"查看日志"来 **查看日志**。 
    
    e. 单击 **"** 完成"关闭"准备架构"向导，并返回到"准备 Active Directory"步骤。
    
5. **步骤 2：验证架构分区的复制**
    
    a. 登录到域的域控制器。
    
    b. 从 **服务器管理器** 中的工具 **下拉菜单中** 打开 ADSI **编辑**。
    
    c. 在 **“操作”** 菜单上，单击 **“连接到”**。
    
    d. 在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。
    
    e. 在架构容器下，搜索 **CN=ms-RTC-SIP-SchemaVersion**。 如果此对象存在， **并且 rangeUpper** 属性的值为 1150， **并且 rangeLower** 属性的值为 3，则架构已成功更新和复制。 如果此对象不存在，或者 **rangeUpper** 和 **rangeLower** 属性的值未如指定值一样，则说明架构未修改或尚未复制。
    
6. **步骤 3：准备当前林**
    
    a. 查看步骤 3 的先决条件信息，可通过单击"步骤 3"标题下的下拉列表来访问这些信息。
    
    b. 单击 **步骤** 3 中的"运行"以启动"准备当前林"向导。
    
    c. 请注意，每个部署应仅运行一次该过程，然后单击"下一步 **"。**
    
    d. 指定将在其中创建通用组的域。 如果服务器是域的一部分，**可以选择"本地** 域"，然后单击"下一步 **"。**
    
    e. 准备好林后，可以通过单击"查看日志"来 **查看日志**。 
    
    f. 单击 **"完成** "关闭"准备当前林"向导，并返回到"准备 Active Directory"步骤。
    
    g. 从 **Skype for Business Server单击**"命令行管理程序 **"** 以启动 PowerShell。
    
    h. 键入命令 Get-CsAdForest，然后按 **Enter**。
    
    i. 如果结果为 **LC_FORESTSETTINGS_STATE_READY，** 则林已成功准备，如图所示。
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **步骤 4：验证全局编录的复制**
    
    a. 在域控制器 (最好位于其他域控制器) 的远程站点中，在运行林准备的林中，打开 **"Active Directory 用户和计算机"。**
    
    b. 在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。
    
    c. 单击 **左侧窗格** 上的"用户"容器，在右侧窗格中查找通用组 **CsAdministrator。** 如果 CsAdministrator (以 Cs 开头的其他新通用组) ，则 Active Directory 复制已成功完成。
    
    d. 如果组尚不存在，可以强制复制，或等待 15 分钟并刷新右侧窗格。 显示组后，表明复制完成。
    
8. **步骤 5：准备当前域**
    
    a. 查看步骤 5 的先决条件信息。
    
    b. 单击 **步骤** 5 中的"运行"以启动"准备当前域"向导。
    
    c. 请注意，该过程只应为部署中每个域运行一次，然后单击"下一步 **"。**
    
    d. 准备好域后，可以通过单击"查看日志"来 **查看日志**。 
    
    e. 单击 **"完成** "关闭"准备当前域"向导，并返回到"准备 Active Directory"步骤。
    
    必须在找到所有对象的所有域中Skype for Business Server这些步骤，否则服务可能无法启动。 这包括任何类型的 Active Directory 对象，如用户、联系对象、管理组或任何类型的对象。 如果需要，可以使用 Set-CsUserReplicatorConfiguration -ADDomainNamingContextList 仅添加包含 Skype for Business Server 对象的域。
    
9. **步骤 6：验证域中的复制**
    
    a. 单击 **"Skype for Business Server"** 页中的"命令行管理 **程序**"以启动 PowerShell。
    
    b. 使用命令Get-CsAdDomain验证域中的复制。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > 如果不指定 Domain 参数，则将该值设置为本地域。 
  
    为 contoso.local 域运行命令的示例：
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > 通过使用参数 GlobalSettingsDomainController，您可以指示存储全局设置的位置。 如果你的设置存储在系统容器 (这通常与尚未将全局设置迁移到配置容器) 的升级部署一样，则定义 AD DS 林根目录的域控制器。 如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。 如果不指定此参数，此 cmdlet 将假定设置存储在"配置"容器中，并引用 Active Directory 中任何域控制器。 
  
    c. 如果 **结果为** LC_DOMAINSETTINGS_STATE_READY ，则已成功复制域。
    
10. **步骤 7：添加用户以提供对 Skype for Business Server 控制面板的管理访问权限**
    
    a. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
    b. 打开 **"Active Directory 用户和计算机**"，展开您的域，单击"用户"容器，右键单击"CSAdministrator"，然后选择"属性 **"。**
    
    c. 在“CSAdministrator 属性”中，单击“成员”选项卡。
    
    d. 在"成员"选项卡上，单击"添加"。 在“选择用户、联系人、计算机、服务帐户或组”中，找到“输入要选择的对象名称”。 键入要添加到 CSAdministrators 组的用户名或组名。 单击“确定”。
    
    e. 在" **成员** "选项卡上，确认所选的用户或组存在。 单击“**确定**”。
    
    > [!CAUTION]
    > 该Skype for Business Server控制面板是基于角色的访问控制工具。 CsAdministrator 组的成员身份为使用"控制面板"Skype for Business Server所有可用配置功能的完全控制权限。 为特定功能提供了其他专门的角色。 有关可用角色的详细信息，请参阅[Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)。 请注意，用户不需要启用Skype for Business Server，就成为管理组的成员。 
  
    > [!CAUTION]
    > 为了帮助保留安全性和基于角色的访问控制完整性，将用户添加到组，这些组定义了用户在管理 Skype for Business Server 角色。 
  
11. 注销，然后重新登录Windows，以便使用新的安全组Skype for Business Server安全令牌，然后重新打开部署向导。
    
12. 确认在"准备 **Active Directory"** 旁边看到绿色选中标记以确认成功，如图所示。
    
     ![准备 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另请参阅
 
[Skype for Business Server 2015 的 Active Directory 域服务](../../plan-your-deployment/security/active-directory-domain-services.md)
