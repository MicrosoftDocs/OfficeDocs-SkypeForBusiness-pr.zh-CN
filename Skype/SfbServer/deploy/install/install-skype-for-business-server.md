---
title: 在拓扑内的服务器上安装 Skype for Business Server
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
description: 摘要：了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 8ecf298809a6c4c37b5c075e7ac16623f1669ff9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791750"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>在拓扑内的服务器上安装 Skype for Business Server
 
**摘要：** 了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。
  
将拓扑加载到中央管理存储并且 Active Directory 知道哪些服务器将执行哪些角色后，你需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 安装 Skype for Business 服务器系统是第7步，共8步。
  
![概述图表。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>安装 Skype for Business 服务器系统

发布拓扑后，您可以在拓扑结构中的每台服务器上安装 Skype for Business 服务器组件。 本部分将引导你完成以下步骤：安装 Skype for Business Server 和设置前端池的服务器角色以及与前端服务器 collocated 的任何服务器角色。 若要安装和设置服务器角色，请在要安装服务器角色的每台计算机上运行 Skype for Business 服务器部署向导。 使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。
  
> [!IMPORTANT]
> 必须使用拓扑生成器完成并发布拓扑，然后才能在服务器上安装 Skype for Business 服务器。 
  
> [!NOTE]
> 必须对拓扑中的所有服务器完成此步骤。 
  
> [!CAUTION]
> 在前端服务器上安装 Skype for Business 服务器后，首次启动服务时，必须确保 Windows 防火墙服务在服务器上运行。 
  
> [!CAUTION]
> 在执行这些步骤之前，请确保你使用既是本地管理员又是 RTCUniversalServerAdmins 组成员的域用户帐户登录到服务器。 
  
> [!NOTE]
> 如果以前未在此服务器上运行 Skype for Business Server 设置，系统将提示你输入安装的驱动器和路径。 如果您的组织要求安装到系统驱动器之外的某个驱动器上或者您考虑空间问题，这将允许您安装到非系统驱动器上。 你可以在 "**设置**" 对话框中将 Skype For business 服务器文件的安装位置路径更改为新的可用驱动器。 如果将安装文件安装到此路径（包括 OCSCore），则 Skype for business 服务器文件的其余部分也将部署到其中。
  
> [!IMPORTANT]
> 开始安装之前，请确保 Windows Server 是使用 Windows 更新的最新版本。 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>安装 Skype for Business 服务器系统

1. 插入 Skype for Business 服务器安装媒体。 如果安装未自动开始，请双击“**安装**”。
    
2. 安装介质需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。
    
3. 仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。 
    
4. 智能设置是 Skype for Business 服务器中的一项功能，您可以在其中连接到 Internet 以在安装过程中检查来自 Microsoft Update （MU）的更新，如图所示。 这能确保你获得最新产品更新，从而提供更好的体验。 单击“**安装**”开始安装。
    
    > [!NOTE]
    > 很多组织在其企业环境中部署了 Windows Server Update Services (WSUS)。 WSUS 可以让管理员完全管理通过 Microsoft Update 发布到其网络中的计算机的更新分发过程。 作为累积更新1发行版 Skype for Business 服务器的一部分，引入了对智能设置的支持，以便与 WSUS 配合使用。 如果客户首次部署 Skype for Business 服务器或从 Lync Server 2013 环境升级到 Lync Server 环境，使用就地升级功能将获得从 WSUS 获取 Skype for Windows 更新的智能设置，而不是提取更新从 MU 开始。 想使用智能设置的客户在运行 Setup.exe 之前，需要在所有计算机上运行 SmartSetupWithWSUS.psq。 
  
     ![智能设置屏幕截图。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. 在 "部署向导" 页面上，单击 "**安装或更新 Skype For Business 服务器系统**"。
    
6. 执行以下过程中的过程，完成这些过程后，单击 "**退出**" 以关闭 "部署向导"。 对池中的每台前端服务器重复此过程。
    
### <a name="step-1-install-local-configuration-store"></a>步骤 1：安装本地配置存储

1. 检查前提条件，单击”**步骤 1：安装本地配置存储**”旁边的“**运行**”。
    
    > [!NOTE]
    > 本地配置存储是中央管理存储的只读副本。在 Standard Edition 部署中，将使用前端服务器上的 SQL Server Express Edition 本地副本创建中央管理存储。在运行“准备第一台 Standard Edition Server”流程时将出现此情况。在 Enterprise Edition 部署中，在您发布包含 Enterprise Edition 前端池的拓扑时，将会创建中央管理存储。 
  
2. 在“**安装本地配置存储**”页面上，确保选择“**直接从中央管理存储中检索**”选项，然后单击“**下一步**”。
    
    SQL Server Express Edition 将安装到本地服务器上。SQL Server Express Edition 是本地配置存储的必要前提。
    
3. 完成本地服务器配置安装后，单击“**完成**”。
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>步骤2：设置或删除 Skype for Business 服务器组件

1. 查看必备条件，然后单击 "**步骤2：设置" 或 "删除 Skype For Business 服务器组件**" 旁边的 "**运行**"。
    
2. 在 "**设置 Skype For Business 服务器组件**" 页面上，单击 "**下一步**" 以设置在已发布拓扑中定义的组件。
    
3. “**正在执行命令**”页将显示安装过程中的命令和安装信息摘要。 完成后，你可以使用列表选择要查看的日志，然后单击 "**查看日志**"。
    
4. 当 Skype for Business Server 组件设置完成并且你已查看所需的日志时，请单击 "**完成**" 以在安装中完成此步骤。
    
    > [!NOTE]
    > 如果提示重新启动服务器（如果需要安装 Windows 桌面体验则可能会发生这种情况），请执行此操作。 当计算机恢复正常运行时，你需要再次运行此操作（步骤2：设置或删除 Skype for Business Server 组件）过程。 
  
    > [!NOTE]
    > 如果安装程序发现存在任何未满足的先决条件，系统将向您通知一条“不满足先决条件”消息，如图所示。 满足所需的先决条件，然后再开始（步骤2：设置或删除 Skype for Business Server 组件）过程。 
  
     ![需要必备组件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. 验证前两步已经如期完成。确认显示如图所示的绿色对勾和“**完成**”字样。
    
     ![安装组件时已完成的前两个步骤。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. 在安装 Skype for Business 服务器组件后，再次运行**Windows 更新**以检查是否有任何更新。
    
### <a name="step-3-request-install-or-assign-certificates"></a>步骤 3：请求、安装或分配证书

1. 检查先决条件，然后单击“**步骤 3：请求、安装或分配证书**”旁边的“**运行**”。
    
    > [!NOTE]
    > Skype for Business 服务器包括对 SHA-1 套件的支持（SHA-2 使用224、256、384或512位）的摘要哈希和签名算法的摘要哈希和签名算法来自运行 Windows 10、Windows 8、windows 7、Windows Server 2012 R2 和 Windows 的客户端的连接服务器2012或 Windows Server 2008 R2 操作系统。 要支持使用 SHA-2 套件进行外部访问，外部证书必须由公共 CA 颁发，公共 CA 也可颁发具有相同位长度摘要的证书。 
  
    > [!IMPORTANT]
    > 选择哪种哈希摘要和签名算法取决于将使用证书的客户端和服务器，客户端和服务器将与其通信的其他计算机和设备也必须知道如何使用证书中所用的算法。 有关操作系统和某些客户端应用程序支持哪些摘要长度的信息，请参阅[WINDOWS PKI 博客 SHA2 和 windows](https://go.microsoft.com/fwlink/p/?LinkId=287002)。 
  
    每台 Standard Edition 或前端服务器最多需要四个证书：oAuthTokenIssuer 证书、默认证书、Web 内部证书和 Web 外部证书。 但是，也可以请求和分配单个具有相应使用者替代名称条目的默认证书以及 oAuthTokenIssuer 证书。 有关证书要求的详细信息，请参阅 Skype for business 服务器2019的[环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 skype For business [Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
    
    > [!IMPORTANT]
    > 以下过程介绍了如何配置来自基于内部 Active Directory 证书服务的证书颁发机构的证书。 
  
2. 在“**证书向导**”页上，单击“**请求**”。
    
3. 在“**证书请求**”页上，填写相关数据，包括选择 SIP 域在内，然后单击“**下一步**”。
    
4. 在“**延迟的请求或即时请求**”页上，可通过单击“**下一步**”接受默认的“**立即将请求发送给联机证书颁发机构**”选项。如果选择此选项，具有自动联机注册的内部 CA 必须可用。如果选择了延迟请求的选项，系统将提示您输入用于保存证书请求文件的名称和位置。证书请求必须由组织内部的 CA 或公共 CA 提出和处理。然后您需要导入证书响应并将其分配给适当的证书角色。
    
5. 在 "**选择证书颁发机构（CA）** " 页面上，选择 "**从你的环境中检测到的列表中选择一个 CA** " 选项，然后从列表中选择一个已知（通过注册 Active DIRECTORY 域服务） ca。 或者，选择“**指定其他证书颁发机构**”选项，在框中输入其他 CA 的名称，然后单击“**下一步**”。
    
6. 在“**证书颁发机构帐户**”页上，将提示您提供凭据，以在 CA 中请求证书和处理证书请求。您应该已经确定提前请求证书是否需要用户名和密码。CA 管理员将拥有所需的信息，并且可能需要协助您完成此步骤。如果需要提供备用凭据，请选中相应的复选框，在文本框中输入用户名和密码，然后单击“**下一步**”。
    
7. 在“**指定替代证书模板**”页上，要使用默认的 Web 服务器模板，请单击“**下一步**”。
    
    > [!NOTE]
    > 如果组织已经创建了模板，以用作默认 Web 服务器 CA 模板的备用模板，请选中相应的复选框，然后输入备用模板的名称。您将需要 CA 管理员定义的模板名称。 
  
8. 在“**名称和安全设置**”页上，指定一个“**友好名称**”。 通过使用友好名称，您可以快速标识证书和目的。 如果将此处留空，则系统会自动生成一个名称。 设置密钥的“**位长度**”，或接受默认值 2048 位。 如果确定需要将证书和私钥移动或复制到其他系统，请选择 "将**证书的私钥标记为可导出**"，然后单击 "**下一步**"。
    
    > [!NOTE]
    > Skype for business 服务器对可导出私钥的要求最低。 其中一个可导出的位置是池中的边缘服务器，在这里媒体中继身份验证服务使用证书副本，而不是对池中的每个实例都分别使用单个证书。 
  
9. 在“**组织信息**”页上，可选择提供组织信息，然后单击“**下一步**”。
    
10. 在“**地理信息**”页上，可选择提供地理信息，然后单击“**下一步**”。
    
11. 在“**使用者名称/使用者替代名称**”页上，检查将添加的使用者替代名称，然后单击“**下一步**”。
    
12. 在“**SIP 域设置**”页上，选择“**SIP 域**”，然后单击“**下一步**”。
    
13. 在“**配置其他使用者替代名称**”页上，添加其他任何需要的使用者替代名称，包括将来其他 SIP 域可能需要的使用者替代名称，然后单击“**下一步**”。
    
14. 在“**证书请求摘要**”页上，检查摘要中的信息。如果信息正确，请单击“**下一步**”。如果需要更正或修改设置，请单击“**上一步**”返回相应的页面进行更正或修改。
    
15. 在“**正在执行命令**”页上，单击“**下一步**”。
    
16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. 如果报告为已颁发并已安装，但它无效，请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。 Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. 默认情况下，"**将证书分配给 Skype for Business 服务器证书使用**情况" 复选框处于选中状态。 If you want to manually assign the certificate, clear the check box, and then click **Finish**.
    
17. 如果已清除 "**将证书分配给以前页面上的 Skype for Business 服务器证书使用**情况" 复选框，则会显示 "**证书分配**" 页面。 Click **Next**.
    
18. 在“**证书存储**”页上，选择已请求的证书。如果要查看证书，请单击“**查看证书详细信息**”，然后单击“**下一步**”继续。
    
    > [!NOTE]
    > 如果“**联机证书请求状态**”页报告证书存在问题（例如证书无效），查看实际证书可协助解决问题。可能导致证书无效的两个具体问题为：先前提到的受信任根 CA 证书缺失，与证书相关联的私钥缺失。有关如何解决这两个问题的信息，请参阅 CA 文档。
  
19. 在“**证书分配摘要**”页上，检查显示的信息以确保此证书是应分配的证书，然后单击“**下一步**”。
    
20. 在“**正在执行命令**”页上，检查命令的输出。如果要检查分配过程或查看是否出现错误或警告，请单击“**查看日志**”。检查完成后，单击“**完成**”。
    
21. 在“**证书向导**”页上，确认所有服务均显示绿色对勾，指示均已分配证书，包括图中所示的 OAuthTokenIssuer 在内，然后单击“**关闭**”。
    
     ![已正确安装和分配的证书。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > 如果您在实验室环境中进行安装，并且使用 Active Directory 证书服务设置了证书颁发机构，您需要重新启动运行证书服务的服务器和前端服务器，然后才能成功颁发证书。 
  
    > [!TIP]
    >  有关 Active Directory 证书服务中的证书的详细信息，请参阅[Active Directory 证书服务](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx)。 
  
### <a name="step-4-start-services"></a>步骤 4：启动服务

1. 检查“**步骤 4：启动服务**”的先决条件。
    
2. If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet. 如果使用单个服务器（使用标准版时总是如此），则 muse 使用**CsWindowsService** cmdlet。 在此示例中，我们将企业版与池中的三个前端服务器配合使用，打开**Skype For Business Server 命令行管理**程序，并运行**CsPool** cmdlet，如下图所示。 For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**. To deploy roles other than the Front End role, see documentation for those particular roles.
    
     ![启动 Skype for Business 服务。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. 在“**正在执行命令**”页上，成功启动所有服务后，单击“**完成**”。
    
    > [!IMPORTANT]
    > 用于启动服务器上的服务的命令是报告实际上已启动服务的最佳方法。 该命令可能无法反映服务的实际状态。 建议使用步骤“**服务状态（可选）**”来打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动，如图所示。 如果任何 Skype for Business 服务器服务尚未启动，可以右键单击 MMC 中的该服务，然后单击 "**开始**"。 
  
     ![验证服务是否已启动。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

