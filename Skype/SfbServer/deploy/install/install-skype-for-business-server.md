---
title: 在拓扑中的服务器上安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 0fe1c7b6088732932457d25c68a8fd6476a1bfbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018243"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>在拓扑中的服务器上安装 Skype for Business Server
 
**摘要：** 了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business Server 的免费试用版。
  
将拓扑加载到中央管理存储中，并且 Active Directory 知道哪些服务器将执行哪些角色后，您需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。 您可以按任意顺序执行步骤1至5。 但是，您必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 安装 Skype for Business Server 系统是第7步（共8步）。
  
![概述关系图。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>安装 Skype for Business Server 系统

发布拓扑后，可以在拓扑中的每台服务器上安装 Skype for Business Server 组件。 本部分指导您安装 Skype for Business Server，并为前端池以及与前端服务器并置的任何服务器角色设置服务器角色。 若要安装和设置服务器角色，请在要安装服务器角色的每台计算机上运行 Skype for Business Server 部署向导。 您可以使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。
  
> [!IMPORTANT]
> 您必须使用拓扑生成器完成并发布拓扑，然后才能在服务器上安装 Skype for Business Server。 
  
> [!NOTE]
> 必须为拓扑中的所有服务器完成此过程。 
  
> [!CAUTION]
> 在前端服务器上安装 Skype for Business Server 之后，首次启动服务时，必须确保 Windows 防火墙服务正在服务器上运行。 
  
> [!CAUTION]
> 在执行这些步骤之前，请确保您使用具有本地管理员和 RTCUniversalServerAdmins 组成员的域用户帐户登录到服务器。 
  
> [!NOTE]
> 如果之前未在此服务器上运行 Skype for Business Server 安装程序，系统会提示你提供安装的驱动器和路径。 这样，如果你的组织需要，还可以将其安装到除系统驱动器之外的驱动器，或者如果你有空间问题。 可以在 "**设置**" 对话框中将 Skype For business Server 文件的安装位置路径更改为新的可用驱动器。 如果将安装文件安装到此路径（包括 OCSCore），则其他 Skype for Business Server 文件也将部署到其中。
  
> [!IMPORTANT]
> 在开始安装之前，请确保 Windows Server 处于最新状态，使用 Windows 更新。 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>安装 Skype for Business Server 系统

1. 插入 Skype for Business Server 安装媒体。 如果安装程序未自动开始，请双击 "**设置**"。
    
2. 安装介质需要 Microsoft Visual c + + 才能运行。 将弹出一个对话框，询问您是否要安装它。 单击 **"是"。**
    
3. 仔细阅读许可协议，如果您同意，请选择 "**我接受许可协议中的条款**"，然后单击 **"确定"**。 
    
4. Smart Setup 是 Skype for Business Server 中的一项功能，您可以在其中连接到 Internet 以在安装过程中检查 Microsoft Update （MU）的更新，如图所示。 这样可以确保拥有产品的最新更新，从而提供了更好的体验。 单击 **“安装”**，开始安装。
    
    > [!NOTE]
    > 许多组织在其公司环境中部署了 Windows Server Update Services （WSUS）。 通过 WSUS，管理员可以完全管理通过 Microsoft Update 发布到其网络中的计算机的更新的分发。 作为累积更新1发行版 Skype for Business Server 的一部分，引入了对智能安装程序的支持以与 WSUS 配合使用。 具有 WSUS 的客户首次部署 Skype for Business Server 或从 Lync Server 2013 环境升级使用就地升级功能将获得智能安装从 WSUS 提取 Skype for Windows 更新，而不是获取更新从 MU。 希望使用智能安装的客户需要先在所有计算机上运行 SmartSetupWithWSUS，然后再运行 Setup.exe。 
  
     ![智能安装程序屏幕截图。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. 在 "部署向导" 页上，单击 "**安装或更新 Skype For Business Server 系统**"。
    
6. 执行以下过程中的过程，在完成这些过程后，单击 "**退出**" 以关闭部署向导。 对池中的每台前端服务器重复这些过程。
    
### <a name="step-1-install-local-configuration-store"></a>步骤1：安装本地配置存储

1. 查看先决条件，然后单击 "**步骤1：安装本地配置存储**" 旁边的 "**运行**"。
    
    > [!NOTE]
    > 本地配置存储是中央管理存储的只读副本。 在标准版部署中，使用前端服务器上的 SQL Server Express Edition 的本地副本创建中央管理存储。 当您运行 "准备第一个 Standard Edition Server" 过程时，会发生这种情况。 在企业版部署中，当您发布包含 Enterprise Edition 前端池的拓扑时，将会创建中央管理存储。 
  
2. 在 "**安装本地配置存储**" 页上，确保选择了 "**直接从中央管理存储区检索**" 选项，然后单击 "**下一步**"。
    
    SQL Server Express Edition 安装在本地服务器上。 本地配置存储需要 SQL Server Express Edition。
    
3. 完成本地服务器配置安装后，单击 **“完成”**。
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>步骤2：安装或删除 Skype for Business Server 组件

1. 查看先决条件，然后单击 "**步骤2：设置" 或 "删除 Skype For Business Server 组件**" 旁边的 "**运行**"。
    
2. 在 "**设置 Skype For Business Server 组件**" 页上，单击 "**下一步**" 设置在已发布拓扑中定义的组件。
    
3. "**正在执行命令**" 页将在设置发生时显示命令和安装信息的摘要。 完成后，可以使用列表选择要查看的日志，然后单击 "**查看日志**"。
    
4. 当 Skype for Business Server 组件安装完成且您已根据需要查看日志时，请单击 "**完成**" 以完成安装中的此步骤。
    
    > [!NOTE]
    > 如果出现提示，请重新启动服务器（如果需要安装 Windows 桌面体验，可能会发生这种情况）。 当计算机重新启动并运行时，需要再次运行此过程（步骤2：安装或删除 Skype for Business Server 组件）。 
  
    > [!NOTE]
    > 如果安装程序发现任何尚未满足的先决条件，将会收到 "先决条件不满意" 消息的通知，如图所示。 满足所需的先决条件，然后重新启动（步骤2：安装或删除 Skype for Business Server 组件）过程。 
  
     ![需要必备组件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. 验证前两个步骤是否按预期完成。 确认在单词 "已**完成**" 中有绿色的复选标记，如图所示。
    
     ![完成安装组件前的两个步骤。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. 在安装 Skype for Business Server 组件后，再次运行**Windows Update**以检查是否有任何更新。
    
### <a name="step-3-request-install-or-assign-certificates"></a>步骤3：请求、安装或分配证书

1. 查看先决条件，然后单击 "**步骤3：请求、安装或分配证书**" 旁边的 "**运行**"。
    
    > [!NOTE]
    > Skype for Business Server 包括对 SHA-1 套件（SHA-1）的支持。对运行 Windows 10、windows 8、windows 7、Windows Server 2012 R2、Windows Server R2 的客户端连接的摘要哈希和签名算法，使用摘要长度为224、256、384或512位）的摘要。服务器2012或 Windows Server 2008 R2 操作系统。 若要使用 SHA-1 套件支持外部访问，外部证书由公共 CA 颁发，也可以颁发具有相同位长度摘要的证书。 
  
    > [!IMPORTANT]
    > 选择哪种散列摘要和签名算法取决于客户端和将使用证书的服务器，以及客户端和服务器与之通信的其他计算机和设备，这些计算机和设备还必须知道如何使用中使用的算法真品. 有关操作系统和一些客户端应用程序中支持的摘要长度的信息，请参阅[WINDOWS PKI 博客-SHA2 和 windows](https://go.microsoft.com/fwlink/p/?LinkId=287002)。 
  
    每个 Standard Edition 或前端服务器最长需要四个证书： oAuthTokenIssuer 证书、默认证书、web 内部证书和 web 外部证书。 但是，可以使用相应的使用者可选名称条目和 oAuthTokenIssuer 证书请求和分配单个默认证书。 有关证书要求的详细信息，请参阅 skype for business [server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
    
    > [!IMPORTANT]
    > 以下过程介绍如何从基于内部 Active Directory 证书服务的证书颁发机构配置证书。 
  
2. 在 **“证书向导”** 页上，单击 **“请求”**。
    
3. 在 "**证书请求**" 页上，填写相关数据，包括选择 SIP 域和，单击 "**下一步**"。
    
4. 在 "**延迟或即时请求**" 页上，可以通过单击 "**下一步**" 接受默认的 "**立即将请求发送到联机证书颁发机构"** 选项。 如果选择此选项，则必须提供具有自动联机注册的内部 CA。 如果你选择延迟请求的选项，系统会提示你输入名称和位置以保存证书请求文件。 证书请求必须由组织内部的 CA 或公用 CA 提供和处理。 然后，您需要导入证书响应，并将其分配给正确的证书角色。
    
5. 在 "**选择证书颁发机构（CA）** " 页上，选择 "**从您的环境中检测到的 CA** " 选项，然后从列表中选择一个已知的（通过在 Active Directory 域服务中注册） ca。 或者，选择 "**指定另一个证书颁发机构**" 选项，在框中输入另一个 CA 的名称，然后单击 "**下一步**"。
    
6. 在 "**证书颁发机构帐户**" 页上，系统会提示您提供凭据以请求和处理 CA 的证书请求。 您应该已确定是否需要用户名和密码才能提前请求证书。 你的 CA 管理员将拥有所需的信息，可能需要在此步骤中为你提供帮助。 如果需要提供备用凭据，请选中此复选框，在文本框中提供用户名和密码，然后单击 "**下一步**"。
    
7. 在 "**指定备用证书模板**" 页上，若要使用默认 Web 服务器模板，请单击 "**下一步**"。
    
    > [!NOTE]
    > 如果您的组织已创建用于替代默认 Web 服务器 CA 模板的模板，则选中 "" 复选框，然后输入备用模板的名称。 你将需要由 CA 管理员定义的模板名称。 
  
8. 在 "**名称和安全设置**" 页上，指定一个**友好名称**。 通过使用友好名称，可以快速标识证书和用途。 如果将其保留为空，则会自动生成一个名称。 设置密钥的**位长度**，或接受默认值2048位。 如果您确定需要将证书和私钥移动或复制到其他系统，请选择 "将**证书的私钥标记为可导出**"，然后单击 "**下一步**"。
    
    > [!NOTE]
    > Skype for Business Server 对可导出私钥的要求最低。 其中一种位置是位于池的边缘服务器上，媒体中继身份验证服务使用证书副本，而不是池中每个实例的单独证书。 
  
9. 在 "**组织信息**" 页上，选择提供组织信息，然后单击 "**下一步**"。
    
10. 在 "**地理信息**" 页上，选择提供地理位置信息，然后单击 "**下一步**"。
    
11. 在 "**使用者名称/主题替代名称**" 页上，查看将添加的 "使用者替代名称"，然后单击 "**下一步**"。
    
12. 在 " **SIP 域设置**" 页上，选择**sip 域**，然后单击 "**下一步**"。
    
13. 在 "**配置附加主题备用名称**" 页上，添加任何其他所需的主题替代名称，包括将来其他 SIP 域可能需要的任何其他主题，然后单击 "**下一步**"。
    
14. 在 "**证书请求摘要**" 页上，查看摘要中的信息。 如果信息正确，请单击 "**下一步**"。 如果需要更正或修改设置，请单击 "**返回**到正确的页面" 以进行更正或修改。
    
15. 在 **“执行命令”** 页上，单击 **“下一步”**。
    
16. 在 "**联机证书请求状态**" 页上，查看返回的信息。 应注意，已颁发证书并已将其安装到本地证书存储中。 如果报告为已颁发并已安装，但它无效，请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。 有关如何检索受信任的根 CA 证书，请参阅 CA 文档。 如果需要查看检索到的证书，请单击 "**查看证书详细信息**"。 默认情况下，将选中 "**将证书分配给 Skype for Business Server 证书使用**情况" 复选框。 如果要手动分配证书，请清除复选框，然后单击 "**完成**"。
    
17. 如果清除了 "将证书分配给前一页上的**Skype for Business 服务器证书使用**情况" 复选框，则会显示 "**证书分配**" 页。 单击“**下一步**”。
    
18. 在 "**证书存储**" 页上，选择所请求的证书。 如果要查看证书，请单击 "**查看证书详细信息**"，然后单击 "**下一步**" 继续。
    
    > [!NOTE]
    > 如果 "**联机证书请求状态**" 页报告了证书的问题，例如证书无效，请查看实际证书以获取帮助以解决问题。 可能导致证书无效的两个具体问题是前面提到的缺少受信任的根 CA 证书，以及与证书相关联的缺少私钥。 请参阅 CA 文档以解决这两个问题。
  
19. 在 "**证书分配摘要**" 页上，查看显示的信息，以确保这是应分配的证书，然后单击 "**下一步**"。
    
20. 在 "**正在执行命令**" 页上，查看命令的输出。 如果要查看分配过程，或者如果发出错误或警告，请单击 "**查看日志**"。 完成审阅后，单击 "**完成**"。
    
21. 在 "**证书向导**" 页上，确认所有服务都有一个绿色的复选标记，以指示已为所有服务分配了一个证书（包括 OAuthTokenIssuer），如图所示，然后单击 "**关闭**"。
    
     ![正确安装和分配的证书。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > 如果要在实验室环境中进行安装，并且只是使用 Active Directory 证书服务设置证书颁发机构，则需要重新启动运行证书服务的服务器以及证书前的前端服务器。工作分配可以成功完成。 
  
    > [!TIP]
    >  有关 Active Directory 证书服务中的证书的详细信息，请参阅[Active Directory 证书服务](https://technet.microsoft.com/windowsserver/dd448615.aspx)。 
  
### <a name="step-4-start-services"></a>步骤4：启动服务

1. 查看**步骤4：启动服务**的先决条件。
    
2. 如果这是一个至少具有三台服务器的 Enterprise Edition 前端池，则使用 Windows Fabric，并且您必须使用**start-cspool** cmdlet。 如果使用的是一台服务器（标准版总是如此），则必须使用**start-cswindowsservice** cmdlet。 在此示例中，我们在池中使用了具有三个前端服务器的 Enterprise Edition，打开**Skype For Business Server 命令行管理**程序，然后运行**start-cspool** cmdlet，如图所示。 对于所有其他角色（包括 Standard Edition server），必须使用**start-cswindowsservice**。 若要部署前端角色之外的角色，请参阅这些特定角色的文档。
    
     ![启动 Skype for Business 服务。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. 在“正在执行命令”**** 页上，成功启动所有服务后，单击“完成”****。
    
    > [!IMPORTANT]
    > 在服务器上启动服务的命令是报告已启动的服务的最佳方法。 该命令可能无法反映服务的实际状态。 建议使用 "步骤**服务状态" （可选）** 打开 Microsoft 管理控制台（MMC），并确认服务已成功启动，如图所示。 如果任何 Skype for Business Server 服务尚未启动，则可以在 MMC 中右键单击该服务，然后单击 "**启动**"。 
  
     ![验证服务是否已启动。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

