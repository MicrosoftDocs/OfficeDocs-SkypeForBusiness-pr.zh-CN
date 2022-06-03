---
title: 在Skype for Business Server中创建和发布新拓扑
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
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 摘要：了解如何在安装Skype for Business Server之前创建、发布和验证新拓扑。
ms.openlocfilehash: 9ae6ee05a20f75946a87e611e972341094a11864
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860553"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>在Skype for Business Server中创建和发布新拓扑
 
**总结：** 在安装Skype for Business Server之前，了解如何创建、发布和验证新拓扑。
  
在拓扑中的每个服务器上安装Skype for Business Server系统之前，必须先创建拓扑并发布它。 发布拓扑时，会将拓扑信息加载到中央管理Microsoft Store数据库中。 如果这是一个Enterprise Edition池，则会在首次发布新拓扑时创建中央管理Microsoft Store数据库。 如果这是Standard Edition，则在发布拓扑之前，需要从部署向导运行“准备第一Standard Edition服务器”进程。 这将通过安装 SQL Server Express Edition 实例并创建中央管理Microsoft Store来准备Standard Edition。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 第 8 步中的步骤 6 介绍了如何创建和发布新拓扑。
  
![概述图。](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>创建和发布新拓扑

可以使用Skype for Business Server拓扑生成器来设计、定义、配置和发布拓扑。 在本文前面安装管理工具时，已安装此工具。 创建拓扑时，可以做出许多不同的选择。 在此过程中，你将创建包含会议的基本拓扑。
  
> [!IMPORTANT]
> Skype for Business Server需要SQL Server才能运行。 主数据库称为中央管理Microsoft Store。 如果要部署Enterprise Edition，则使用以下步骤发布拓扑时会创建这些数据库。 在这种情况下，拓扑生成器会向你询问SQL Server安装的连接信息。 如果计划部署Standard Edition，则需要在定义和发布新拓扑之前安装 SQL Server Express Edition。 若要安装 SQL Server Express Edition，应在将充当前端的服务器上打开部署向导，然后运行“准备第一Standard Edition服务器”。 单击“准备第一Standard Edition服务器”时，部署向导会自动安装SQL Server Express版本，并创建中央管理Microsoft Store数据库。 
  
### <a name="create-a-new-topology"></a>创建新的拓扑

1. 以有权访问拓扑生成器的标准用户身份登录。
    
2. 打开Skype for Business Server拓扑生成器。
    
3. 选择 **“新建拓扑**”，然后单击 **“确定**”。
    
4. 为拓扑配置文件选择位置和文件名。
    
    > [!NOTE]
    > 拓扑配置保存为拓扑生成器 XML (.tbxml) 文件。 发布拓扑时，将配置信息从文件推送到SQL Server数据库。 将来打开拓扑生成器时，可以将现有配置从SQL Server直接下载到拓扑生成器中，并将其发布回SQL Server或将其另存为拓扑生成器配置文件。 
  
5. 在 **“定义主域”屏幕上**，输入 **主 SIP 域**，然后单击 **“下一步**”。 在此示例中，我们将使用 `contoso.local`，如图所示。
    
     ![定义主 sip 域。](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. 添加任何其他受支持的 SIP 域，然后单击 **“下一步**”。
    
7. 输入第一个网站的 **名称** 和 **说明** (位置) ，然后单击 **“下一步**”，如图所示。
    
     ![定义第一个站点 (位置) 。](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. 输入 **网站的城市**、 **州/省** 和国家 **/地区代码** ，然后单击 **“下一步**”。
    
9. 单击 **“完成** ”以完成定义新拓扑的过程。 新的前端向导会自动启动。
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>定义前端池或Standard Edition服务器

1. 查看向导先决条件，然后单击 **“下一步**”。
    
2. 在池的 FQDN)  (输入完全限定的域名，然后选择 **Enterprise Edition前端池** 或 **Standard Edition服务器**，然后单击 **“下一步**”，如图所示。
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition可以包括多个协同工作的服务器来提供前端角色。 使用多个服务器来履行角色时，它称为池。 因此，多个服务器协同工作以提供前端角色也称为前端池。 Skype for Business Server Standard Edition只能包含一个服务器来提供前端角色。 即使只有一台服务器提供该角色，也通常引用前端池。 
  
     ![定义前端池。](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. 输入池中所有计算机的完全限定域名 (FQDN) ，然后单击 **下一步** ，如图所示。
    
     ![定义池中的计算机。](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. 选择将包含在此拓扑中的功能，然后单击 **下一步** ，如图所示。
    
    > [!NOTE]
    > Skype for Business Server包含许多高级功能。 查看要使用的每个特定功能的规划和部署文档。 
  
     ![选择部署的功能。](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. 在 **“选择并置服务器角色** ”页上，可以选择在前端服务器上并置中介服务器，也可以选择将其部署为独立服务器。
    
    如果要将中介服务器并置在Enterprise Edition前端池中，请确保选中复选框。 将在池服务器上部署服务器角色。 如果打算将中介服务器部署为独立服务器，请清除相应的复选框。 完全部署前端服务器后，将在单独的部署步骤中部署中介服务器。 有关并置的规划详细信息，请参阅 [Skype for Business Server 的拓扑基础](../../plan-your-deployment/topology-basics/topology-basics.md)知识。
    
6. 通过将 **“关联服务器角色”与此前端池页配合** 使用，可以定义服务器角色并将其与前端池相关联。 以下角色可用：
    
    **启用 Edge 池** 定义和关联单个边缘服务器或边缘服务器池。 边缘服务器有助于组织内部用户与组织外部人员（包括联合用户）之间的通信和协作。
    
    有两种可能的方案可用于部署和关联服务器角色。
    
    方案一，为新的安装定义新的拓扑。 可以通过以下两种方式之一来接近安装：
    
   - 使复选框保持清晰，并定义拓扑。 发布、配置和测试前端和后端服务器角色后，可以再次运行拓扑生成器，将角色服务器添加到拓扑。 通过使用此策略，可以测试前端池和运行SQL Server的服务器，而无需其他角色产生其他复杂性。 完成初始测试后，可以再次运行拓扑生成器以选择需要部署的角色。
    
   - 选择需要安装的角色，然后设置硬件以适应所选择的角色。
    
     对于方案 2，你有一个现有部署，并且基础结构已准备好使用新角色，或者需要将现有角色与新的前端服务器相关联。
    
   - 在这种情况下，你将选择要部署或与新的前端服务器关联的角色。 无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。
    
7. 接下来，你将定义要与拓扑一起使用的SQL Server存储。 在此示例中，我们使用默认实例。 有关SQL Server功能（如高可用性）的详细信息，请参阅 [Skype for Business Server 中的高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
   - 若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“SQL 存储”中的一个实例。
    
   - 若要定义用于存储池信息的新SQL Server实例，请单击 **“新建**”，然后在“**定义新SQL Microsoft Store**”对话框中指定 **SQL Server FQDN**。
    
   - 要指定 SQL Server 实例的名称，请选择“命名实例”，然后指定实例的名称。
    
   - 要使用默认实例，请单击“默认实例”。
    
   - 若要使用SQL镜像，请选择 **“启用SQL镜像**”，然后选择现有实例，或创建新实例。

     > [!NOTE]
     > SQL镜像在 2015 Skype for Business Server提供，但在 2019 Skype for Business Server不再受支持。 Skype for Business Server 2019 中首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和SQL故障转移群集方法。
    
     在此示例中，输入 **SQL Server FQDN**，并配置任何相关的高可用性设置，然后单击 **“确定**”，如图所示。
    
     ![创建SQL Server存储。](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. 确定是要启用SQL Server存储镜像还是SQL Server镜像见证，然后单击 **“下一步**”。
    
9. 定义要使用的文件共享。
    
   - 要使用已经在拓扑中定义的文件共享，请选择“使用先前定义的文件共享”。
    
   - 要定义新文件共享，请选择“定义新的文件共享”，在“文件服务器 FQDN”框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“文件共享”框中输入文件共享的名称。
    
     对于此示例，我们将单击 **“定义新文件存储”**，输入 **文件服务器 FQDN** 和 **文件共享**，然后单击 **“下一步**”。
    
     > [!NOTE]
     > Skype for Business Server的文件共享可以并置，但出于性能原因，不建议这样做。 请注意，在此示例中，文件共享位于将充当文件共享的单个专用服务器上。 但是，建议使用其他更可靠的文件共享系统（例如使用 Windows Server 2012 R2 的 DFS）。 有关受支持的文件共享系统的详细信息，请参阅[Skype for Business环境的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 有关创建文件共享的详细信息，请参阅[Skype for Business Server中创建文件共享](create-a-file-share.md)。 可以在尚未创建文件共享的情况下定义文件共享。 在发布拓扑之前，您将需要在定义的位置创建文件共享。 
  
10. 在“指定 Web 服务 URL”页上，必须决定是否需要重写内部 Web 服务池基 URL。 此重写的原因与负载均衡有关。 基本 SIP 流量可以通过简单的 DNS 负载均衡进行负载均衡。 但是，HTTP/S Web Services 网络流量必须使用支持的硬件或软件负载均衡解决方案。 有关支持的负载均衡器，请参阅[基础结构Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md)。 在此示例中，我们使用 DNS 负载均衡来处理 SIP 流量和受支持的软件负载均衡解决方案。 由于我们正以这种方式划分流量，因此需要覆盖内部 Web 服务池 FQDN。 或者，如果我们有一个顶线负载均衡器并通过它发送所有流量，而不是对 SIP 流量使用 DNS 负载均衡，则无需重写 Web 服务 URL。 
    
    在本主题的 DNS 部分中，我们为 `webint.contoso.local`其创建了一条 A 记录。 这是我们用于 Web 服务 HTTP/S 流量的 URL，它必须经过我们设置的受支持的软件负载均衡器。 因此，在此示例中，我们重写 URL，让Skype for Business Server知道所有 HTTP/S 流量都应转到`webint.contoso.local`，而不是`pool.contoso.local`像图中所示。 有关负载均衡的详细信息，请参阅[Skype for Business的负载均衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。
    
    > [!IMPORTANT]
    > 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 `https://webint.contoso.local`基 URL `webint.contoso.local`。 
  
    - 如果要配置 DNS 负载均衡，如本示例所示，请选中 **“替代内部 Web 服务池 FQDN** ”复选框，然后输入内部基 URL (，该 URL 必须与 **内部基 URL** 中的池 FQDN) 不同。 
    
    > [!CAUTION]
    > 如果决定使用自定义 FQDN 替代内部 Web 服务，则每个 FQDN 必须唯一来自任何其他前端池、Director 或 Director 池。 定义 URL 或完全限定的域名时，**仅使用标准字符** (包括 A-Z、a-z、0-9 和连字符) 。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共证书颁发机构通常不支持 URL 或 FQDN 中的非标准字符 (CA)  (即，当必须将 URL 或 FQDN 分配给证书) 中的使用者名称或使用者替代名称时。
  
    - （可选）在 **外部基 URL 中输入外部基 URL**。 输入外部基 URL 以将其与内部域名区分开来。 例如，内部域为 `contoso.local`，但外部域名为 `contoso.com`。 你将使用域名定义 URL， `contoso.com` 因为它必须可从公共 DNS 解析。 如果是反向代理，这也很重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 对于移动客户端上的即时消息和状态，需要 HTTP 访问前端池。
    
      ![替代 Web 服务。](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. 如果在“**选择功能**”页上选择了 **“会议**”，系统将要求你选择Office Web 应用服务器。 单击 **“新建** ”以启动对话框。
    
12. 在“**定义新Office Web 应用服务器**”对话框中，在“Office Web 应用 **服务器 FQDN”框中键入Office Web 应用服务器的 FQDN**;执行此操作时，应会自动将Office Web 应用服务器发现 URL 输入到 **Office Web 应用服务器发现 URL** 框。
    
    如果Office Web 应用服务器安装在本地，并且与Skype for Business Server位于同一网络区域中，请勿选择在 **外部网络 (（即外围/Internet) ）中部署服务器Office Web 应用** 选项。
    
    如果Office Web 应用服务器部署在内部防火墙之外，请选择Office Web 应用 **服务器部署在外部网络 (（即外围/Internet)**）中的选项。
    
13. 单击 **“完成** ”以完成配置。 如果在 **“关联服务器角色”上定义了其他角色服务器和此前端池** 页，则单独的角色配置向导页将打开，你可以在其中配置服务器角色。 在此示例中，我们仅选择会议。
    
### <a name="configure-simple-urls"></a>配置简单的 URL

1. 在拓扑生成器中，右键单击 **Skype for Business Server** 顶部节点，然后单击 **“编辑属性**”，如图所示。
    
     ![右键单击Skype for Business Server，然后选择“编辑属性”。](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. 在 **“简单 URL”** 窗格中，选择 **电话访问 URL：** (电话拨入) 或 **会议 URL：** (会议) 进行编辑，然后单击 **“编辑 URL**”。
    
3. 将 URL 更新为所需的值，然后单击“确定”保存已编辑的 URL。 应使用外部 SIP 域配置简单的 URL，以便外部用户可以加入会议，例如 `contoso.com`外部会议，而不是 `contoso.local`内部域。 因此，SIP 域应该能够由外部 DNS 解析。
    
4. 如有必要，使用相同的步骤编辑会议 URL。
    
### <a name="to-define-the-optional-admin-simple-url"></a>定义可选的管理简单 URL

1. 在拓扑生成器中，右键单击 **Skype for Business Server** 节点，然后单击 **“编辑属性**”。
    
2. 在 **“管理访问 URL**”框中，输入要用于管理访问Skype for Business Server 控制面板的简单 URL，然后单击 **“确定**”。
    
    > [!TIP]
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项是 https://admin. . _\<domain\>_ 例如，管理员 URL 可以是内部域或外部域，`contoso.local`或者`contoso.com`只要在内部 DNS 中可解析任何记录。 
  
    > [!IMPORTANT]
    > 如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。 如果更改影响简单 URL 的基础，则也必须更改 DNS 记录和证书。 例如，从 `https://sfb.contoso.com/Meet` `https://meet.contoso.com` sfb 更改基 URL。`contoso.com` 因此 `meet.contoso.com`，需要更改要引用 `meet.contoso.com`的 DNS 记录和证书。 如果将简单 URL 更改 `https://sfb.contoso.com/Meet` 为 `https://sfb.contoso.com/Meetings`，则基本 URL `sfb.contoso.com` 保持不变，因此无需 DNS 或证书更改。 但是，每当更改简单 URL 名称时，必须在每个 Director 和前端服务器上运行 **Enable-CsComputer** cmdlet 以注册更改。
  
### <a name="publish-and-verify-the-topology"></a>发布和验证拓扑

1. 检查所有简单 URL 是否配置正确。
    
2. 确认基于SQL Server的服务器处于联机状态，并且可用于安装拓扑生成器的计算机，包括任何必要的防火墙规则。
    
3. 确认文件共享可用，以及是否定义了适当的权限。
    
4. 确认拓扑中定义了满足部署要求的正确服务器角色。
    
5. 验证Active Directory 域服务 (AD DS) 中是否存在服务器。 当你将服务器加入域时，会自动发生这种情况。
    
    如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。 如果存在验证错误，则必须更正这些错误，然后才能发布拓扑。
    
6. 右键单击 **Skype for Business Server** 节点，然后单击 **“发布拓扑**”。
    
7. 在“发布拓扑”页上，单击“下一步”。
    
8. 在 **“选择中央管理服务器** ”页上，选择前端池，如图所示。
    
    > [!NOTE]
    > 可以单击 **“高级** ”配置数据库文件位置。
  
     ![选择中央管理Microsoft Store服务器。](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. 在 **“选择数据库”** 页上，选择要发布的数据库。
    
    > [!NOTE]
    > 如果没有适当的权限来创建数据库，则可以清除这些数据库旁边的复选框，具有适当权限的人以后可以创建数据库。 有关要求的详细信息，请参阅[服务器Skype for Business Server要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
10. 也可以单击“高级”。 通过使用高级SQL Server数据文件放置选项，可以在以下选项之间进行选择： 
    
    - **自动确定数据库文件位置** - 此选项通过将日志和数据文件分发到最佳位置，根据基于SQL Server服务器上的磁盘配置确定最佳操作性能。
    
    - **使用SQL Server实例默认** 值 - 此选项使用实例设置将日志和数据文件置于基于SQL Server的服务器上。 此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。 通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”，然后单击“下一步”。 
    
11. （可选）单击 **“高级**”。 通过使用高级SQL Server数据文件放置选项，可以在以下选项之间进行选择： 
    
    - **自动确定数据库文件位置** - 此选项通过将日志和数据文件分发到最佳位置，根据基于SQL Server服务器上的磁盘配置确定最佳操作性能。
    
    - **使用SQL Server实例默认** 值 - 此选项使用实例设置将日志和数据文件置于基于SQL Server的服务器上。 此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。 通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”。
    
12. 单击“下一步”完成发布过程。
    
    > [!NOTE]
    > 此步骤的常见故障是无法创建SQL Server数据库。 当进程无法完成时，将提供错误，如图所示。 最可能的原因是尝试创建数据库的用户没有适当的权限，或者由于防火墙或其他网络问题，无法联系SQL Server系统。 
  
     ![创建中央管理存储时出错。](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. 发布过程完成后，会显示一个链接来打开后续步骤的列表。 单 **击此处打开待操作列表** 以查看后续步骤，然后单击 **“完成**”。 
    
    数据库创建的“带警告完成”消息并不意味着存在错误。 安装过程必须更改SQL Server中的设置，Skype for Business Server才能正常工作。 在SQL Server中更改设置时，会将其记录为警告，以便SQL Server管理员可以确切地了解安装过程的完成情况。 如果收到警告，可以选择记录，然后单击 **“查看日志** ”查看警告的详细信息。
    
    成功发布拓扑后，可以在拓扑中运行Skype for Business Server的每个服务器上开始安装中央管理存储的本地副本。 建议从第一个前端池开始。 
