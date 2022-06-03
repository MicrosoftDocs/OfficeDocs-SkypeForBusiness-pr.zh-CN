---
title: 在拓扑中的服务器上安装Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 摘要：了解如何在拓扑中的每台服务器上安装Skype for Business Server系统组件。
ms.openlocfilehash: 7aea6d25edcd28ba611b81d33eceed4172019bee
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860613"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>在拓扑中的服务器上安装Skype for Business Server
 
**总结：** 了解如何在拓扑中的每台服务器上安装Skype for Business Server系统组件。
  
将拓扑加载到中央管理Microsoft Store并且 Active Directory 知道哪些服务器将执行哪些角色后，需要在拓扑中的每个服务器上安装Skype for Business Server系统。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8 以及步骤 1 到 5，如下图所述。 安装Skype for Business Server系统是第 8 步的第 7 步。
  
![概述图。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>安装Skype for Business Server系统

发布拓扑后，可以在拓扑中的每台服务器上安装Skype for Business Server组件。 本部分介绍如何安装Skype for Business Server并设置前端池的服务器角色以及与前端服务器并置的任何服务器角色。 若要安装和设置服务器角色，请在安装服务器角色的每台计算机上运行Skype for Business Server部署向导。 使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。
  
> [!IMPORTANT]
> 必须使用拓扑生成器来完成拓扑并发布拓扑，然后才能在服务器上安装Skype for Business Server。 
  
> [!NOTE]
> 必须为拓扑中的所有服务器完成此过程。 
  
> [!CAUTION]
> 首次启动服务时，在前端服务器上安装Skype for Business Server后，必须确保Windows防火墙服务在服务器上运行。 
  
> [!CAUTION]
> 在执行这些步骤之前，请确保使用域用户帐户登录到服务器，该帐户既是本地管理员，又是 RTCUniversalServerAdmins 组的成员。 
  
> [!NOTE]
> 如果之前尚未在此服务器上运行Skype for Business Server安装程序，系统会提示你输入安装的驱动器和路径。 这提供了安装到系统驱动器以外的驱动器的功能，如果你的组织需要它，或者如果你有空间问题。 可以将 **“设置**”对话框中Skype for Business Server文件的安装位置路径更改为新的可用驱动器。 如果将安装程序文件安装到此路径，包括OCSCore.msi，则Skype for Business Server文件的其余部分也将部署到此路径。
  
> [!IMPORTANT]
> 在开始安装之前，请确保Windows服务器使用Windows 更新是最新的。 
  
![Windows服务器最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>安装Skype for Business Server系统

1. 插入Skype for Business Server安装介质。 如果安装程序未自动开始，请双击 **“设置**”。
    
2. 安装介质需要Microsoft Visual C++才能运行。 将弹出一个对话框，询问是否要安装它。 单击 **“是”。**
    
3. 仔细查看许可协议，如果同意，请选择 **我接受许可协议中的条款**，然后单击 **“确定**”。 
    
4. 智能安装是Skype for Business Server中的一项功能，可在安装过程中连接到 Internet 以检查 Microsoft 更新 (MU) 中的更新，如图所示。 这通过确保你拥有产品的最新更新提供了更好的体验。 单击 **“安装”**，开始安装。
    
    > [!NOTE]
    > 许多组织在其公司环境中部署了Windows Server Update Services (WSUS) 。 WSUS 允许管理员完全管理通过 Microsoft 更新发布到其网络中的计算机的更新的分发。 作为累积更新 1 版本的一部分，Skype for Business Server引入了对智能安装程序的支持，以便与 WSUS 配合使用。 首次部署Skype for Business Server或使用 In-Place 升级功能从 Lync Server 2013 环境升级的 WSUS 客户将具有智能安装程序，用于从 WSUS 获取 Skype Windows更新，而不是从 MU 提取更新。 想要使用智能安装程序的客户需要在运行Setup.exe之前在所有计算机上运行 SmartSetupWithWSUS.psq。 
  
     ![智能安装屏幕截图。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. 在“部署向导”页上，单击“**安装”或“更新”Skype for Business Server系统**。
    
6. 在以下过程中执行这些过程，完成这些过程后，单击 **“退出** ”关闭部署向导。 重复池中每个前端服务器的过程。
    
### <a name="step-1-install-local-configuration-store"></a>步骤 1：安装本地配置Microsoft Store

1. 查看先决条件，然后单击步骤 1 旁边的 **“运行****：安装本地配置Microsoft Store**”。
    
    > [!NOTE]
    > 本地配置Microsoft Store是中央管理Microsoft Store的只读副本。 在Standard Edition部署中，使用前端服务器上SQL Server Express版本的本地副本创建中央管理Microsoft Store。 运行“准备第一Standard Edition服务器”过程时会发生这种情况。 在Enterprise Edition部署中，发布包含Enterprise Edition前端池的拓扑时，将创建中央管理存储。 
  
2. 在 **“安装本地配置Microsoft Store**”页上，确保 **选择“直接从中央管理存储区检索**”选项，然后单击 **“下一步**”。
    
    SQL Server Express版本安装在本地服务器上。 本地配置存储需要SQL Server Express版本。
    
3. 完成本地服务器配置安装后，单击 **“完成”**。
    
### <a name="step-2-set-up-or-remove-skype-for-business-server-components"></a>步骤 2：设置或删除Skype for Business Server组件

1. 查看先决条件，然后单击步骤 2 旁边的 **“运行****：设置”或“删除Skype for Business Server组件**”。
    
2. 在 **“设置Skype for Business Server组件**”页上，单击 **“下一步**”设置已发布的拓扑中定义的组件。
    
3. **“执行命令**”页显示设置时命令和安装信息的摘要。 完成后，可以使用列表选择要查看的日志，然后单击 **“查看日志**”。
    
4. 完成Skype for Business Server组件设置并根据需要查看日志后，单击 **“完成**”以完成安装中的此步骤。
    
    > [!NOTE]
    > 如果系统提示 (如果需要安装) Windows桌面体验，则重启服务器。 当计算机备起并运行时，需要再次运行此 (步骤 2：安装或删除Skype for Business Server组件) 过程。 
  
    > [!NOTE]
    > 如果安装程序发现任何未满足的先决条件，系统会收到“先决条件不满意”消息，如图所示。 满足所需的先决条件，然后再次启动此 (步骤 2：设置或删除Skype for Business Server组件) 过程。 
  
     ![需要先决条件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. 验证前两个步骤是否按预期完成。 确认有一个绿色复选标记，其中包含“ **完成**”一词，如图所示。
    
     ![安装组件后完成的前两个步骤。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. 再次 **运行Windows 更新**，检查安装Skype for Business Server组件后是否有任何更新。
    
### <a name="step-3-request-install-or-assign-certificates"></a>步骤 3：请求、安装或分配证书

1. 查看先决条件，然后单击 **“步骤 3：请求、安装或分配证书**”旁边的 **“运行**”。
    
    > [!NOTE]
    > Skype for Business Server包括对 SHA-2 套件的支持 (SHA-2 使用摘要长度为 224、256、384 或 512 位，) 摘要哈希和签名算法，用于运行 Windows 10、Windows 8、Windows 7、Windows Server 2012 R2 的客户端的连接，Windows Server 2012或Windows服务器 2008 R2 操作系统。 为了支持使用 SHA-2 套件的外部访问，外部证书由公共 CA 颁发，该公用 CA 还可以颁发具有相同位长度摘要的证书。 
  
    > [!IMPORTANT]
    > 选择哪个哈希摘要和签名算法取决于将使用证书的客户端和服务器，以及客户端和服务器将与谁通信的其他计算机和设备，这些计算机和设备还必须知道如何使用证书中使用的算法。 有关操作系统和某些客户端应用程序支持哪些摘要长度的信息，请[参阅 Windows PKI 博客 - SHA2 和 Windows](/archive/blogs/pki/sha2-and-windows)。 
  
    每个Standard Edition或前端服务器最多需要四个证书：oAuthTokenIssuer 证书、默认证书、Web 内部证书和 Web 外部证书。 但是，可以请求并分配具有相应使用者替代名称条目以及 oAuthTokenIssuer 证书的单个默认证书。 有关证书要求的详细信息，请参阅 [2019](../../../SfBServer2019/plan/system-requirements.md) Skype for Business Server Skype for Business Server或服务器要求[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
    
    > [!IMPORTANT]
    > 以下过程介绍如何从基于 Active Directory 证书服务的内部证书颁发机构配置证书。 
  
2. 在 **“证书向导”** 页上，单击 **“请求”**。
    
3. 在 **“证书请求** ”页上填写相关数据，包括选择 SIP 域，然后单击 **“下一步**”。
    
4. 在 **“延迟”或“即时请求**”页上，可以通过单击“**下** 一步”接受默认的“**立即将请求发送到联机证书颁发机构**”选项。 如果选择此选项，则必须提供具有自动联机注册的内部 CA。 如果选择延迟请求的选项，系统会提示你输入一个名称和位置来保存证书请求文件。 证书请求必须由组织内部的 CA 或公共 CA 提出和处理。 然后，需要导入证书响应并将其分配给适当的证书角色。
    
5. 在 **“选择证书颁发机构 (CA)**”页 **上，从环境选项中检测到的列表中选择 CA**，然后从列表中选择Active Directory 域服务) CA 中的已知 (。 或者，选择“ **指定另一个证书颁发机构** ”选项，在框中输入另一个 CA 的名称，然后单击 **“下一步**”。
    
6. 在 **“证书颁发机构帐户** ”页上，系统会提示输入凭据，以便在 CA 请求和处理证书请求。 应确定是否需要用户名和密码来提前请求证书。 你的 CA 管理员将拥有所需的信息，并且可能必须协助你完成此步骤。 如果需要提供备用凭据，请选中复选框，在文本框中提供用户名和密码，然后单击 **“下一步**”。
    
7. 在 **“指定备用证书模板”** 页上，若要使用默认 Web 服务器模板，请单击 **“下一步**”。
    
    > [!NOTE]
    > 如果组织已创建模板以用作默认 Web 服务器 CA 模板的替代方法，请选中复选框，然后输入备用模板的名称。 需要 CA 管理员定义的模板名称。 
  
8. 在 **“名称和安全设置** 页上，指定 **友好名称**。 通过使用友好名称，可以快速标识证书和用途。 如果将其留空，将自动生成一个名称。 设置键的 **位长度** ，或接受默认值 2048 位。 如果确定证书和私钥需要移动或复制到其他系统，请选择“将 **证书的私钥标记为可导出”** ，然后单击 **“下一步**”。
    
    > [!NOTE]
    > Skype for Business Server对可导出的私钥的要求最低。 其中一个位置位于池中的边缘服务器上，其中媒体中继身份验证服务使用证书副本，而不是池中每个实例的单个证书。 
  
9. 在 **“组织信息** ”页上，可以选择提供组织信息，然后单击 **“下一步**”。
    
10. 在“ **地理信息”** 页上，可以选择提供地理信息，然后单击 **“下一步**”。
    
11. 在 **“主题名称/使用者备用名称”** 页上，查看要添加的主题替代名称，然后单击 **“下一步**”。
    
12. 在 **“SIP 域设置** ”页上，选择 **“SIP 域**”，然后单击 **“下一步**”。
    
13. 在 **“配置其他使用者备用名称** ”页上，添加任何其他必需的使用者替代名称，包括将来其他 SIP 域可能需要的任何名称，然后单击 **“下一步**”。
    
14. 在 **“证书请求摘要** ”页上，查看摘要中的信息。 如果信息正确，请单击 **“下一步**”。 如果需要更正或修改设置，请单击 **“返回** 到正确的页面”进行更正或修改。
    
15. 在 **“执行命令”** 页上，单击 **“下一步”**。
    
16. 在 **“联机证书请求状态”** 页上，查看返回的信息。 应注意，证书已颁发并安装到本地证书存储中。 如果报告该证书已颁发并安装，但无效，请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。 请参阅 CA 文档，了解如何检索受信任的根 CA 证书。 如果需要查看检索到的证书，请单击 **“查看证书详细信息**”。 默认情况下，选中“将 **证书分配给Skype for Business Server证书用法的** 复选框。 如果要手动分配证书，请清除复选框，然后单击 **“完成**”。
    
17. 如果清除了将 **证书分配到上一页上Skype for Business Server证书用法** 的复选框，则会显示 **“证书分配**”页。 单击“**下一步**”。
    
18. 在 **“证书Microsoft Store**”页上，选择请求的证书。 如果要查看证书，请单击 **“查看证书详细信息**”，然后单击 **“下一步** ”继续。
    
    > [!NOTE]
    > 如果 **联机证书请求状态** 页报告了证书的问题（例如证书无效），请查看实际证书以获取解决问题的帮助。 可能导致证书无效的两个特定问题是前面提到的缺少受信任的根 CA 证书，以及与证书关联的缺失私钥。 请参阅 CA 文档来解决这两个问题。
  
19. 在 **“证书分配摘要** ”页上，查看显示的信息以确保这是应分配的证书，然后单击 **“下一步**”。
    
20. 在 **“执行命令** ”页上，查看命令的输出。 如果要查看分配过程或是否已发出错误或警告，请单击 **“查看日志** ”。 完成审阅后，单击 **“完成**”。
    
21. 在 **“证书向导** ”页上，确认所有服务都有一个绿色检查，以指示所有服务都已分配证书，包括 OAuthTokenIssuer，如图所示，然后单击 **“关闭**”。
    
     ![正确安装和分配的证书。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > 如果在实验室环境中安装并且刚刚使用 Active Directory 证书服务设置了证书颁发机构，则需要重新启动运行证书服务的服务器和前端服务器，然后证书分配才能成功完成。 
  
    > [!TIP]
    >  有关 Active Directory 证书服务中的证书的详细信息，请参阅 [Active Directory 证书服务](/windows/deployment/deploy-whats-new)。 
  
### <a name="step-4-start-services"></a>步骤 4："开始"菜单服务

1. 查看 **步骤 4："开始"菜单服务** 的先决条件。
    
2. 如果这是至少包含三台服务器的Enterprise Edition前端池，则使用Windows Fabric，并且必须使用 **"开始"菜单-CsPool** cmdlet。 如果使用单个服务器（Standard Edition始终是这种情况），则使用 **"开始"菜单-CsWindowsService** cmdlet。 在此示例中，我们将Enterprise Edition与池中的三台前端服务器配合使用，打开 **Skype for Business Server Management Shell** 并运行 **"开始"菜单-CsPool** cmdlet，如图所示。 对于所有其他角色（包括Standard Edition服务器），必须使用 **"开始"菜单-CsWindowsService**。 若要部署前端角色以外的角色，请参阅这些特定角色的文档。
    
     !["开始"菜单 Skype for Business服务。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. 在“正在执行命令”页上，成功启动所有服务后，单击“完成”。
    
    > [!IMPORTANT]
    > 在服务器上启动服务的命令是报告服务实际上已启动的最佳方法。 该命令可能无法反映服务的实际状态。 建议使用步骤 **服务状态 (可选)** 打开 MMC)  (Microsoft 管理控制台，并确认服务已成功启动，如图所示。 如果任何Skype for Business Server服务尚未启动，可以在 MMC 中右键单击该服务，然后单击 **"开始"菜单**。 
  
     ![验证服务是否已启动。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
