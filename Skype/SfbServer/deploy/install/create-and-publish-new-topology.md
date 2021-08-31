---
title: 在部署中新建和发布Skype for Business Server
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 摘要：了解如何在安装新拓扑之前创建、发布和验证Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：。
ms.openlocfilehash: 322b59a064f15dcd7bada74c0d3d5f563e6b8f64
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725991"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>在部署中新建和发布Skype for Business Server
 
**摘要：** 了解如何在安装新拓扑之前创建、发布和验证Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) ：。
  
必须先创建拓扑并Skype for Business Server拓扑，然后才能在拓扑中每台服务器上安装系统。 发布拓扑时，将拓扑信息加载到中央管理存储数据库中。 如果这是一Enterprise Edition池，则首次发布新拓扑时将创建中央管理存储数据库。 如果已Standard Edition，则需要在发布拓扑之前从部署向导运行"准备第一Standard Edition服务器"过程。 这将通过安装 Standard Edition Edition SQL Server Express并创建中央管理存储，为更新做好准备。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按照图中的概述顺序执行步骤 6、7 和 8 以及步骤 1 到步骤 5 之后。 How to create and publish a new topology is described in step 6 of 8.
  
![概述图表。](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>创建和发布新拓扑

可以使用拓扑Skype for Business Server设计、定义、配置和发布拓扑。 此工具是在您安装本文前面介绍的管理工具时安装的。 创建拓扑时，可以做出许多不同的选择。 在此过程中，您将创建具有会议的基本拓扑。
  
> [!IMPORTANT]
> Skype for Business Server需要SQL Server才能运行。 主数据库称为中央管理存储。 如果要部署Enterprise Edition，则使用以下步骤发布拓扑时将创建这些数据库。 在这种情况下，拓扑生成器会要求您提供要安装SQL Server信息。 如果计划部署Standard Edition，则需要先安装 SQL Server Express Edition，然后才能定义和发布新拓扑。 若要安装 SQL Server Express Edition，应在将充当前端的服务器上打开部署向导，然后运行"准备第一个Standard Edition服务器"。 单击"准备第一Standard Edition服务器"时，部署向导会自动安装 SQL Server Express Edition 并创建中央管理存储数据库。 
  
### <a name="create-a-new-topology"></a>创建新拓扑

1. 以具有拓扑生成器访问权限的标准用户登录。
    
2. 打开Skype for Business Server生成器"。
    
3. 选择 **"新建拓扑"，** 然后单击 **"确定**"。
    
4. 选择拓扑配置文件的位置和文件名。
    
    > [!NOTE]
    > 拓扑配置另存为拓扑生成器 XML (.tbxml) 文件。 发布拓扑时，将配置信息从文件推送到SQL Server数据库。 将来打开拓扑生成器时，可以将现有配置从 SQL Server 直接下载到拓扑生成器中，并将其发布回 SQL Server 或将其另存为拓扑生成器配置文件。 
  
5. 在"**定义主域"屏幕上**，输入 **主 SIP 域**，然后单击"下一 **步"。** 在此例中，我们使用 **contoso.local，** 如图所示。
    
     ![定义主 sip 域。](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. 添加任何其他支持的 SIP 域，然后单击"下一 **步"。**
    
7. 为网站 **位置** 的第 **一** 个 (输入名称和) ，然后单击"下一步"，如图所示。 
    
     ![定义第一个站点 (位置) 。](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. 输入 **网站的城市****、省/市**/自治区和国家 **/地区** 代码，然后单击"下一步 **"。**
    
9. 单击 **"** 完成"完成定义新拓扑的过程。 "新建前端向导"会自动启动。
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>定义前端池或Standard Edition服务器

1. 查看向导先决条件，然后单击"下一 **步"。**
    
2. 输入池的完全限定域名 (FQDN) ，然后选择 **"Enterprise Edition 前端** 池"或 **"Standard Edition 服务器**"，然后单击"下 **一步**"，如图所示。
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition可以包括多台协同工作以提供前端角色的服务器。 当使用多个服务器来履行角色时，它称为池。 因此，协同工作以提供前端角色的多个服务器也称为前端池。 Skype for Business Server Standard Edition只能包含一台服务器来提供前端角色。 通常，即使只有一台服务器提供角色，也通常引用前端池。 
  
     ![定义前端池。](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. 输入池中所有 (FQDN) 完全限定的域名，然后单击"下一步"，如图所示。 
    
     ![定义池中的计算机。](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. 选择此拓扑中将包含的功能，然后单击"下一步 **"，如图** 所示。
    
    > [!NOTE]
    > Skype for Business Server包括许多高级功能。 查看要使用的每个特定功能的计划和部署文档。 
  
     ![选择部署功能。](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. 在" **选择并排服务器** 角色"页上，可以选择在前端服务器上并排中介服务器，也可以选择将其部署为独立服务器。
    
    如果要在前端池上并Enterprise Edition中介服务器，请确保选中该复选框。 将在池服务器上部署服务器角色。 如果要将中介服务器部署为独立服务器，请清除相应的复选框。 完全部署前端服务器后，您将在单独的部署步骤中部署中介服务器。 有关并置的规划详细信息，请参阅[Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md)。
    
6. 通过使用" **将服务器角色与前端** 池关联"页，可以定义服务器角色并将其与前端池关联。 以下角色可用：
    
    **启用边缘池** 定义并关联单个边缘服务器或边缘服务器池。 边缘服务器可促进组织内部用户与组织外部人员（包括联盟用户）之间的通信和协作。
    
    有两种可能的方案可用于部署和关联服务器角色。
    
    方案一，为新的安装定义新的拓扑。 可以通过以下两种方法之一完成安装：
    
   - 将复选框保留为清除，并定义拓扑。 发布、配置和测试前端服务器角色和后端服务器角色后，可以再次运行拓扑生成器以向拓扑中添加角色服务器。 通过使用此策略，可以测试前端池和运行 SQL Server，而不需要其他角色的额外复杂性。 完成初始测试后，可以再次运行拓扑生成器以选择需要部署的角色。
    
   - 选择需要安装的角色，然后设置硬件以适应所选择的角色。
    
     对于方案二，您具有现有部署，并且您的基础结构已准备好使用新角色，或者您需要将现有角色与新的前端服务器关联。
    
   - 在这种情况下，您将选择要部署的角色或将其与新的前端服务器关联。 无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。
    
7. 接下来，将SQL Server拓扑中使用的存储。 此示例使用 Default 实例。 有关高可用性等SQL Server，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
   - 若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“SQL 存储”中的一个实例。
    
   - 若要定义新的 SQL Server实例以存储池信息，请单击"新建"，然后在"定义新的SQL Server存储"对话框中指定 SQL **FQDN。** 
    
   - 要指定 SQL Server 实例的名称，请选择“命名实例”，然后指定实例的名称。
    
   - 要使用默认实例，请单击“默认实例”。
    
   - 若要使用SQL镜像，请选择"启用 **SQL镜像"，** 然后选择现有实例或创建新实例。

     > [!NOTE]
     > SQL镜像在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。
    
     对于此示例，我们输入 SQL Server **FQDN，** 并配置任何相关的高可用性设置，然后单击 **"确定**"，如图所示。
    
     ![创建SQL Server存储。](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. 决定是否要启用镜像SQL Server或SQL Server镜像见证，然后单击"下一步 **"。**
    
9. 定义想要使用的文件共享。
    
   - 要使用已经在拓扑中定义的文件共享，请选择“使用先前定义的文件共享”。
    
   - 要定义新文件共享，请选择“定义新的文件共享”，在“文件服务器 FQDN”框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“文件共享”框中输入文件共享的名称。
    
     对于此示例，我们将单击"定义 **新的文件存储"，** 输入文件服务器 **FQDN** 和 **文件共享**，然后单击"下一步 **"。**
    
     > [!NOTE]
     > 可以并Skype for Business Server文件共享，但出于性能原因不建议这样做。 请注意，此示例中的文件共享位于将充当文件共享的单个专用服务器上。 但是，建议使用其他更强大的文件共享系统，如使用 Windows Server 2012 R2 的 DFS。 有关受支持的文件共享系统的详细信息，请参阅 Requirements [for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 有关创建文件共享的信息，请参阅 Create [a file share in Skype for Business Server](create-a-file-share.md)。 可以在尚未创建文件共享的情况下定义文件共享。 在发布拓扑之前，您将需要在定义的位置创建文件共享。 
  
10. 在"指定 Web 服务 URL"页上，必须决定是否需要覆盖内部 Web 服务池基 URL。 此覆盖的原因与负载平衡有关。 基本 SIP 流量可以通过简单的 DNS 负载平衡进行负载平衡。 但是，HTTP/S Web 服务网络流量必须使用受支持的硬件或软件负载平衡解决方案。 有关支持的负载平衡器，请参阅[基础结构Skype for Business。](../../../SfbPartnerCertification/certification/infra-gateways.md) 在此例中，我们将 DNS 负载平衡用于 SIP 流量和支持的软件负载平衡解决方案。 由于我们按这种方式划分流量，因此需要覆盖内部 Web 服务池 FQDN。 或者，如果我们有一个顶线负载平衡器并通过它发送所有流量，而不是对 SIP 流量使用 DNS 负载平衡，则不需要覆盖 Web 服务 URL。 
    
    在本主题的 DNS 部分中，我们为 webint.contoso.local 创建了 A 记录。 这是我们用于 Web 服务 HTTP/S 流量的 URL，它必须经过我们设置的支持的软件负载平衡器。 因此，此示例中，我们重写 URL 以让 Skype for Business Server 知道所有 HTTP/S 流量应转到 webint.contoso.local，而不是 pool.contoso.local，如图所示。 有关负载平衡的更多信息，请参阅[load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)。
    
    > [!IMPORTANT]
    > 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 https://webint.contoso.local ，则基 URL 为 webint.contoso.local。 
  
    - 如果要配置 DNS 负载平衡，如本例所示，请选中"覆盖内部 Web 服务池 **FQDN"** 复选框，然后输入内部基 URL (该 URL 必须与内部基 URL 中的池 FQDN) **不同**。 
    
    > [!CAUTION]
    > 如果您决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。 **定义 URL 或** (时，请仅使用标准字符) 包括 A-Z、a-z、0-9 和连字符。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共证书颁发机构 (CA)  (通常不支持 URL 或 FQDN 中的非标准字符，即当必须将 URL 或 FQDN 分配给证书) 中的主题名称或主题替代名称时。
  
    - （可选）在"外部基 URL"中输入 **外部基 URL。** 您将输入外部基 URL 以将其与内部域名区分。 例如，内部域为 contoso.local，但外部域名 contoso.com。 您将使用域名 contoso.com URL，因为它必须从公共 DNS 解析。 如果是反向代理，这也很重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 移动客户端上的即时消息和状态需要访问前端池的 HTTP。
    
      ![替代 Web 服务。](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. 如果在"**选择功能"** 页上选择了"会议"，则系统将会要求您选择Office Web Apps 服务器。 单击 **"新建** "以启动对话框。
    
12. 在"**定义新的 Office Web Apps 服务器**"对话框中，在"Office Web Apps 服务器 **FQDN"框中键入 Office Web Apps 服务器的 FQDN;** 当您这样做时，Office Web Apps 服务器发现 URL 应自动输入到"Office **Web Apps 服务器发现 URL"** 框中。
    
    如果 Office Web Apps 服务器安装在本地，并且与 Skype for Business Server 位于同一网络区域中，请不要选择选项 Office Web Apps Server 部署在外部网络 (即 **外围/Internet) 中**。
    
    如果 Office Web Apps 服务器部署在内部防火墙之外，请选择选项"Office Web Apps Server 部署在外部网络 (即外围 **/Internet) "。**
    
13. 单击 **"完成** "完成配置。 如果在"将服务器角色与此前端池关联"页上定义了其他角色服务器，将打开单独的角色配置向导页，您可以在其中配置服务器角色。 本示例中，我们仅选择会议。
    
### <a name="configure-simple-urls"></a>配置简单 URL

1. 在拓扑生成器中，右键单击Skype for Business Server **节点，** 然后单击"编辑属性"，如图所示。
    
     ![右键单击Skype for Business Server并选择"编辑属性"。](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. 在"**简单 URL"** 窗格中，选择要编辑的 电话 访问 **URL： (** Dial-in) 或 **Meeting URLs：** (Meet) to edit，然后单击"编辑 **URL"。**
    
3. 将 URL 更新为所需的值，然后单击“确定”保存已编辑的 URL。 您应该使用外部 SIP 域配置简单 URL，以便外部用户可以加入会议，例如，contoso.com，它是外部的，而不是 contoso.local，它是内部域。 因此，SIP 域应能够通过外部 DNS 进行解析。
    
4. 如有必要，使用相同的步骤编辑会议 URL。
    
### <a name="to-define-the-optional-admin-simple-url"></a>定义可选的管理简单 URL

1. 在拓扑生成器中，右键 **单击"Skype for Business Server"** 节点，然后单击"编辑 **属性"。**
    
2. 在"**管理访问 URL"** 框中，输入要用于管理访问"控制面板"Skype for Business Server URL，然后单击"确定 **"。**
    
    > [!TIP]
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项是 https://admin 。 _\<domain\>_ 管理 URL 可以是内部或外部域，例如 contoso.local 或 contoso.com，只要任一记录可在内部 DNS 中解析即可。 
  
    > [!IMPORTANT]
    > 如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。 如果更改影响简单 URL 的基础，则还必须更改 DNS 记录和证书。 例如，从 更改为 将基 URL 从 sfb.contoso.com 更改为 meet.contoso.com，因此您需要更改 DNS 记录和证书以引用 https://sfb.contoso.com/Meet https://meet.contoso.com meet.contoso.com。 如果您将简单 URL 从 更改为 ，则 sfb.contoso.com URL 保持不变，因此不需要 https://sfb.contoso.com/Meet https://sfb.contoso.com/Meetings 更改 DNS 或证书。 但是，只要更改简单 URL 名称，就必须在每个控制器和前端服务器上运行 **Enable-CsComputer** cmdlet 以注册更改。
  
### <a name="publish-and-verify-the-topology"></a>发布和验证拓扑

1. 检查所有简单 URL 是否配置正确。
    
2. 确认基于SQL Server的服务器联机，并可供安装了拓扑生成器的计算机使用，包括任何必要的防火墙规则。
    
3. 确认文件共享可用，并且定义了适当的权限。
    
4. 确认拓扑中定义了满足部署要求的正确服务器角色。
    
5. 验证服务器是否存在于 Active Directory 域服务 (AD DS) 。 当您将服务器加入域时，会自动发生这种情况。
    
    如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。 如果存在验证错误，则必须更正错误，然后才能发布拓扑。
    
6. 右键单击 **"Skype for Business Server"** 节点，然后单击"发布 **拓扑"。**
    
7. 在“发布拓扑”页上，单击“下一步”。
    
8. 在" **选择中央管理服务器** "页上，选择一个前端池，如图所示。
    
    > [!NOTE]
    > 可以单击 **"高级"** 配置数据库文件位置。
  
     ![选择中央管理存储服务器。](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. 在 **"选择数据库** "页上，选择要发布的数据库。
    
    > [!NOTE]
    > 如果您没有创建数据库的适当权限，可以清除这些数据库旁边的复选框，并且具有相应权限的用户可以稍后创建数据库。 有关要求的详细信息，请参阅 server [requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
10. 也可以单击“高级”。 通过使用高级SQL Server数据文件放置选项，您可以在以下选项中进行选择： 
    
    - **自动确定数据库文件位置**- 此选项通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器的磁盘配置确定最佳运行性能。
    
    - **使用SQL Server默认设置**- 此选项使用实例设置将日志和数据文件SQL Server基于服务器的服务器上。 此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。 通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”，然后单击“下一步”。 
    
11. （可选）单击"**高级"。** 通过使用高级SQL Server数据文件放置选项，您可以在以下选项中进行选择： 
    
    - **自动确定数据库文件位置**- 此选项通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器的磁盘配置确定最佳运行性能。
    
    - **使用SQL Server默认设置**- 此选项使用实例设置将日志和数据文件SQL Server基于服务器的服务器上。 此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。 通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”。
    
12. 单击“下一步”完成发布过程。
    
    > [!NOTE]
    > 此步骤的一个常见故障是SQL Server数据库。 当该过程无法完成时，会提供一个错误，如图所示。 最可能的原因是尝试创建数据库的用户没有适当的权限，或者由于防火墙或其他网络问题，无法联系 SQL Server 系统。 
  
     ![创建中央管理存储时出错。](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. 发布过程完成后，将显示一个链接，以打开下一步的列表。 单击 **"单击此处打开要执行的列表**"以查看接下来的步骤，然后单击"完成 **"。** 
    
    数据库创建时显示"已完成，带警告"消息并不意味着出现错误。 安装过程必须更改 SQL Server 中的Skype for Business Server，Skype for Business Server正常工作。 当设置在SQL Server更改时，它将记录为警告，以便SQL Server管理员能够准确了解安装过程完成了哪些操作。 如果收到警告，您可以选择该记录，然后单击"查看日志"以查看警告的详细信息。
    
    成功发布拓扑后，可以在拓扑中运行中央管理存储的每个服务器上开始Skype for Business Server副本。 建议您从第一个前端池开始。 
