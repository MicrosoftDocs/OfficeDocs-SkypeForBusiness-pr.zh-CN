---
title: 在拓扑中的服务器上安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 摘要：了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: e6aa1dde01f7f91b7d1c18b1664a3658911cf50b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801682"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>在拓扑中的服务器上安装 Skype for Business Server
 
**摘要：** 了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从 Microsoft 评估中心下载 Skype for Business Server [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
一旦拓扑加载到中央管理存储，并且 Active Directory 知道哪些服务器将执行哪些角色，则需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。 可以按任意顺序执行步骤 1 到步骤 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如图中所述。 安装 Skype for Business Server 系统是步骤 7/8。
  
![概述图表。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>安装 Skype for Business Server 系统

发布拓扑后，可以在拓扑中的每台服务器上安装 Skype for Business Server 组件。 本部分将指导您安装 Skype for Business Server，并设置前端池的服务器角色以及与前端服务器并排的任何服务器角色。 若要安装和设置服务器角色，您可以在要安装服务器角色的每台计算机中运行 Skype for Business Server 部署向导。 使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。
  
> [!IMPORTANT]
> 必须先使用拓扑生成器完成和发布拓扑，然后才能在服务器上安装 Skype for Business Server。 
  
> [!NOTE]
> 必须为拓扑中所有服务器完成此过程。 
  
> [!CAUTION]
> 在前端服务器上安装 Skype for Business Server 后，首次启动服务时，必须确保 Windows 防火墙服务正在服务器上运行。 
  
> [!CAUTION]
> 在按照这些步骤操作之前，请确保使用同时是本地管理员和 RTCUniversalServerAdmins 组的一个成员的域用户帐户登录到服务器。 
  
> [!NOTE]
> 如果之前尚未在此服务器上运行 Skype for Business Server 安装程序，系统将提示你输入安装驱动器和路径。 如果你的组织需要它，或者如果你有空间问题，这将提供安装到系统驱动器驱动器外的其他驱动器的功能。 你可以将"安装"对话框中 Skype for Business Server 文件的安装位置路径更改为新的可用驱动器。 如果将安装程序文件安装到此路径（包括 OCSCore.msi，则其余的 Skype for Business Server 文件也将部署在此路径中。
  
> [!IMPORTANT]
> 在开始安装之前，请确保使用 Windows 更新使 Windows Server 是最新的。 
  
![Windows Server 最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>安装 Skype for Business Server 系统

1. 插入 Skype for Business Server 安装媒体。 如果安装程序不会自动开始，请双击"设置 **"。**
    
2. 安装媒体需要 Microsoft Visual C++ 来运行。 将弹出一个对话框，询问是否要安装它。 单击 **"是"。**
    
3. 仔细阅读许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"**确定"。** 
    
4. 智能安装是 Skype for Business Server 中的一项功能，你可以连接到 Internet 以在安装过程中检查 Microsoft Update (MU) 的更新，如图所示。 这通过确保你拥有产品的最新更新提供了更好的体验。 单击 **“安装”**，开始安装。
    
    > [!NOTE]
    > 许多组织在企业环境中 (WSUS) Windows Server Update Services。 WSUS 使管理员能够完全管理通过 Microsoft 更新发布的更新分发到其网络中计算机。 作为累积更新 1 发行版的一部分，Skype for Business Server 引入了对智能安装程序的支持，以使用 WSUS。 首次部署 Skype for Business Server 或使用 In-Place 升级功能从 Lync Server 2013 环境升级的 WSUS 客户将拥有智能安装程序，从 WSUS 获取 Skype for Windows 更新，而不是从 MU 获取更新。 想要使用智能安装程序的客户需要在运行智能安装程序之前在所有计算机上运行 SmartSetupWithWSUS.psqSetup.exe。 
  
     ![智能设置屏幕截图。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. 在"部署向导"页上，单击 **"安装或更新 Skype for Business Server 系统"。**
    
6. 执行以下过程的过程，完成后，单击"退出"关闭部署向导。  对池中的每个前端服务器重复这些过程。
    
### <a name="step-1-install-local-configuration-store"></a>步骤 1：安装本地配置存储

1. 查看先决条件，然后单击"步骤 1：安装本地配置存储"旁边的 **"运行"。** 
    
    > [!NOTE]
    > 本地配置存储是中央管理存储的只读副本。 在 Standard Edition 部署中，中央管理存储是使用前端服务器上 SQL Server Express Edition 的本地副本创建的。 当您运行"准备第一个 Standard Edition Server"过程时，将发生这种情况。 在 Enterprise Edition 部署中，在发布包含 Enterprise Edition 前端池的拓扑时，将创建中央管理存储。 
  
2. 在"**安装本地配置存储**"页上，确保已选中"直接从中央管理存储检索"选项，然后单击"下一 **步"。**
    
    SQL Server Express Edition 安装在本地服务器上。 SQL Server配置存储需要 Express Edition。
    
3. 完成本地服务器配置安装后，单击 **“完成”**。
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>步骤 2：安装或删除 Skype for Business Server 组件

1. 查看先决条件，然后单击"步骤 2：设置或删除 Skype for Business Server 组件"旁边的 **"运行"。** 
    
2. 在 **"设置 Skype for Business Server** 组件"页上，单击"下一步"设置已发布拓扑中定义的组件。
    
3. " **正在执行命令** "页会在设置进行时显示命令和安装信息的摘要。 完成后，可以使用列表选择要查看的日志，然后单击"查看 **日志"。**
    
4. 完成 Skype for Business Server 组件设置并根据需要查看日志后，单击"完成"以完成安装中的此步骤。
    
    > [!NOTE]
    > 如果系统提示重新启动 (当需要安装 Windows 桌面体验时，可能会) 。 当计算机备份并运行时，你需要再次 (步骤 2：安装或删除 Skype for Business Server 组件) 过程。 
  
    > [!NOTE]
    > 如果安装程序找到任何未满足的先决条件，您将收到"不满足先决条件"消息，如图所示。 满足所需的先决条件，然后再次 (步骤 2：安装或删除 Skype for Business Server) 过程。 
  
     ![必备组件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. 验证前两个步骤是否按照预期完成。 确认有一个绿色选中标记，其单词为 **"完成**"，如图所示。
    
     ![安装组件的前两个步骤已完成。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. 再次 **运行 Windows** 更新，检查安装 Skype for Business Server 组件后是否有更新。
    
### <a name="step-3-request-install-or-assign-certificates"></a>步骤 3：请求、安装或分配证书

1. 查看先决条件，然后单击"步骤 3：请求、安装或分配证书"旁边的 **"运行"。** 
    
    > [!NOTE]
    > Skype for Business Server 支持 SHA-2 套件 (SHA-2 使用摘要长度为 224、256、384 或 512 位) 的摘要哈希，以及来自运行 Windows 10、Windows 8、Windows 7、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 操作系统的客户端的连接签名算法。 为了支持使用 SHA-2 套件进行外部访问，外部证书由公共 CA 颁发，公共 CA 也可以颁发具有相同位长度摘要的证书。 
  
    > [!IMPORTANT]
    > 选择哪种哈希摘要和签名算法取决于将使用证书的客户端和服务器，以及客户端和服务器将通信的其他计算机和设备，这些计算机和设备还必须知道如何使用证书中使用的算法。 有关操作系统和一些客户端应用程序中支持摘要长度的信息，请参阅[Windows PKI 博客 - SHA2 和 Windows。](https://go.microsoft.com/fwlink/p/?LinkId=287002) 
  
    每个 Standard Edition 或前端服务器最多需要四个证书：oAuthTokenIssuer 证书、默认证书、Web 内部证书和 Web 外部证书。 但是，您可以请求并分配具有相应主题备用名称条目的单个默认证书以及 oAuthTokenIssuer 证书。 有关证书要求的详细信息，请参阅 [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 的环境要求或 Skype for Business Server [2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
    
    > [!IMPORTANT]
    > 以下过程介绍如何从基于内部 Active Directory 证书服务的证书颁发机构配置证书。 
  
2. 在 **“证书向导”** 页上，单击 **“请求”**。
    
3. 在"**证书请求**"页上，填写数据，包括选择 SIP 域，然后单击"下一 **步"。**
    
4. 在"**延迟请求"或**"即时请求"页上，可以通过单击"下一步"接受默认的"立即将请求发送到联机证书颁发机构 **"选项**。 如果选择此选项，则具有自动联机注册的内部 CA 必须可用。 如果选择延迟请求的选项，系统将提示您输入名称和位置以保存证书请求文件。 证书请求必须由组织内部的 CA 或公共 CA 提供和处理。 然后，您需要导入证书响应并将其分配给适当的证书角色。
    
5. 在"选择证书颁发机构 **(CA) "** 页上，选择"从环境中检测到的列表中选择 CA"选项，然后通过注册 Active Directory 域服务) CA 从列表中选择已知 (。 或者，选择"**指定其他证书颁发** 机构"选项，在框中输入另一个 CA 的名称，然后单击"下一 **步"。**
    
6. 在 **"证书颁发机构帐户** "页上，系统会提示您提供凭据，以在 CA 请求并处理证书请求。 您应该已确定提前请求证书时是否有必要使用用户名和密码。 CA 管理员将拥有所需信息，可能必须协助你执行此步骤。 如果需要提供备用凭据，请选中该复选框，在文本框中提供用户名和密码，然后单击"下一 **步"。**
    
7. 在"**指定备用证书模板**"页上，若要使用默认 Web 服务器模板，请单击"下一 **步"。**
    
    > [!NOTE]
    > 如果组织已创建模板以用作默认 Web 服务器 CA 模板的替代模板，请选中该复选框，然后输入备用模板的名称。 您需要 CA 管理员定义的模板名称。 
  
8. 在 **"名称和安全设置"** 页上，指定 **友好名称**。 通过使用友好名称，您可以快速标识证书和用途。 如果保留为空，将自动生成一个名称。 设置 **密钥的位** 长度，或接受默认值 2048 位。 如果 **确定证书** 和私钥需要移动或复制到其他系统，请选择"将证书的私钥标记为可导出"，然后单击"下一 **步"。**
    
    > [!NOTE]
    > Skype for Business Server 对可导出私钥的要求最低。 其中一个此类位置位于池中的边缘服务器上，其中媒体中继身份验证服务使用证书的副本，而不是池中每个实例的单个证书。 
  
9. 在"**组织信息**"页上，可以选择提供组织信息，然后单击"下一 **步"。**
    
10. 在"**地理信息"** 页上，可以选择提供地理信息，然后单击"下一 **步"。**
    
11. 在"**主题名称/主题备用** 名称"页上，查看将添加的备用主题名称，然后单击"下一 **步"。**
    
12. 在 **"SIP 域设置**"页上，选择 **SIP 域**，然后单击"下一 **步"。**
    
13. 在 **"配置其他主题替代** 名称"页上，添加任何其他所需的主题替代名称，包括将来其他 SIP 域可能需要的任何名称，然后单击"下一 **步"。**
    
14. 在 **"证书请求摘要"** 页上，查看摘要中的信息。 如果信息正确，请单击"下一 **步"。** 如果需要更正或修改设置，请单击"返回到正确的页面"进行更正或修改。
    
15. 在 **“执行命令”** 页上，单击 **“下一步”**。
    
16. 在 **"联机证书请求状态** "页上，查看返回的信息。 请注意，证书已颁发并安装到本地证书存储中。 如果报告其已颁发和安装，但无效，请确保已在服务器的受信任根 CA 存储中安装了 CA 根证书。 请参阅 CA 文档，了解如何检索受信任的根 CA 证书。 如果需要查看检索到的证书，请单击 **"查看证书详细信息"。** 默认情况下，选中"将证书分配给 **Skype for Business Server 证书用法** "复选框。 如果要手动分配证书，请清除该复选框，然后单击"完成 **"。**
    
17. 如果在上一页上清除了"将证书分配给 **Skype for Business Server** 证书用法"复选框，则将会显示"证书分配 **"** 页。 单击“**下一步**”。
    
18. 在 **"证书存储** "页上，选择您请求的证书。 如果要查看证书，请单击" **查看** 证书详细信息"，然后单击"下一步 **"继续** 。
    
    > [!NOTE]
    > 如果 **"联机证书请求** 状态"页报告证书问题，例如证书无效，则查看实际证书，以寻求帮助解决问题。 可能导致证书无效的两个特定问题是前面提到的缺少受信任的根 CA 证书，以及缺少与该证书关联的私钥。 请参阅 CA 文档来解决这两个问题。
  
19. 在 **"证书分配摘要**"页上，查看显示的信息以确保这是应分配的证书，然后单击"下一 **步"。**
    
20. 在 **"正在执行命令"** 页上，查看命令的输出。 如果要 **查看** 工作分配过程，或者出现错误或警告，请单击"查看日志"。 完成审阅后，单击"完成 **"。**
    
21. 在"证书向导"页上，确认所有服务都有绿色检查，以指示所有服务都分配有证书，包括 OAuthTokenIssuer（如图所示），然后单击"关闭 **"。**
    
     ![正确安装和分配证书。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > 如果要在实验室环境中安装，并且刚刚使用 Active Directory 证书服务设置证书颁发机构，则需要重新启动运行证书服务的服务器和前端服务器，然后才能成功完成证书分配。 
  
    > [!TIP]
    >  有关 Active Directory 证书服务中的证书详细信息，请参阅 [Active Directory 证书服务](https://technet.microsoft.com/windowsserver/dd448615.aspx)。 
  
### <a name="step-4-start-services"></a>步骤 4：启动服务

1. 查看步骤 **4 的先决条件：启动服务**。
    
2. 如果这是至少具有三台服务器的 Enterprise Edition 前端池，则使用 Windows Fabric，并且必须使用 **Start-CsPool** cmdlet。 如果使用单台服务器（Standard Edition 始终如此），则使用 **Start-CsWindowsService** cmdlet。 在此示例中，我们将 Enterprise Edition 与池中的三台前端服务器一同使用，打开 **Skype for Business Server 命令行** 管理程序并运行 **Start-CsPool** cmdlet，如图所示。 对于所有其他角色，包括 Standard Edition Server，必须使用 **Start-CsWindowsService。** 若要部署前端角色外的角色，请参阅这些特定角色的文档。
    
     ![启动 Skype for Business 服务。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. 在“正在执行命令”页上，成功启动所有服务后，单击“完成”。
    
    > [!IMPORTANT]
    > 用于启动服务器上服务的命令是报告服务实际上已启动的最佳方法。 该命令可能无法反映服务的实际状态。 建议您使用步骤"服务状态 **" (可选)** 打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动，如图所示。 如果任何 Skype for Business Server 服务尚未启动，可以在 MMC 中右键单击该服务，然后单击"**开始"。** 
  
     ![验证服务是否启动。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

