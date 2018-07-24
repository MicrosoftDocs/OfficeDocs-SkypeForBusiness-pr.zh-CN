---
title: 安装 Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要： 了解如何为业务服务器准备安装的 Skype 环境。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: d5c1290e4a7a1beeb2310c69f0c63d7f549e0d76
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026039"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要：** 了解如何为业务服务器准备安装的 Skype 环境。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为：[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
本文指导您完成的 Skype 示例安装业务服务器。 本文不会尝试覆盖所有执行完整 Skype Business Server 安装所需的过程。 目的是在包含基本会议和共享功能的狭义定义拓扑中提供过程示例。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype 业务服务器的安装过程的概述

Skype 业务服务器安装包括许多不同的过程。 您需要在您的环境中运行业务服务器获取 Skype 的过程取决于您环境的具体情况。 例如，如果您为 DNS 使用 Windows Server，则可在提供的添加 DNS 条目示例过程中获益。 如果您为 DNS 使用其他系统，则需要采用适用于特定 DNS 系统的过程。 本节中介绍的许多过程皆是如此。
  
Skype 业务服务器是 Standard Edition 和 Enterprise Edition 中可用。 主要区别在于，Standard Edition 不支持 Enterprise Edition 中包含的高可用性功能。 
  
Skype 业务服务器是高级的产品，并完全安装过程大量取决于具体环境。 本节概述了该产品的一般安装步骤。 但是，每个过程可能都有所不同，具体取决于您的环境和规划决策。 例如，小型组织的一台服务器运行 Skype 对于业务 Server Standard Edition 可能不适当，而大型跨国组织有 50 个服务器在专用于产品世界各地的位置。
  
> [!NOTE]
> 若要了解最新累积更新，请参阅[Updates for Business Server 的 Skype](https://support.microsoft.com/en-us/kb/3061064)。 安装 CU1 修补程序后管理员需要执行`Update-CsAdminRole`cmdlet。 需要此 cmdlet 才能通过远程 PowerShell 访问新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本节中的过程仅用作示例，其定义了一组狭窄的要求，并且假定已制定了特定的决策。 您需要安装业务服务器的 Skype 的实际过程可能会很大的不同。 使用中的过程本节示例仅为而不是一个分步指南 Skype 业务服务器安装在每个环境中。 
  
Skype 业务服务器启动并运行在首次涉及八个主要步骤。 您应了解本节中的示例过程不为业务服务器安装 Skype 所需的唯一过程。 可通过以下八个示例步骤来更好地理解总体流程和让基本的工作环境上线运行。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 这八个步骤包括：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装必备组件的业务服务器 Skype](install-prerequisites.md) ： 组成企业服务器拓扑的 Skype 的所有服务器上安装必备组件。 注意，所有角色的先决条件并不一定相同。 例如，提供前端角色的服务器具备一组先决条件，而提供控制器角色的服务器具备另一组先决条件。 有关更多详细信息，请参阅先决条件规划文档。
    
- [创建文件共享中的业务服务器 Skype](create-a-file-share.md) ： 创建将使用企业服务器拓扑整个 Skype 的服务器的文件共享。
    
- [安装管理工具中的业务服务器 Skype](install-administrative-tools.md) ： 管理工具包括拓扑生成器和 Control Panel。 您必须拓扑或 64 位管理工作站上运行的是业务服务器 Skype 支持的 Windows 操作系统版本中的至少一台服务器上安装管理工具。
    
- [准备 Active Directory 中的业务服务器 Skype](prepare-active-directory.md) ： 与 Active Directory 紧密合作 Skype 业务服务器。 您必须准备使用 Skype 业务服务器的 Active Directory 域。 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。
    
- [为 Skype 业务服务器创建 DNS 记录](create-dns-records.md)： 使业务服务器可以正常运行的 Skype 时，大量的 DNS 设置必须满足。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。
    
- [创建和发布新拓扑中 Skype 业务服务器](create-and-publish-new-topology.md)： 您可以在每个拓扑中的服务器上安装 Business Server system 的 Skype 之前，您必须创建一个拓扑，并将其发布。 发布拓扑时，拓扑信息会载入中央管理存储数据库。 如果这是 Enterprise Edition 池，您将在初次发布新拓扑时创建中央管理存储数据库。 如果是 Standard Edition，则需要运行部署向导中的“准备第一个 Standard Edition Server”过程，之后才能发布拓扑。 这将安装 SQL Server Express Edition 实例，并创建中央管理存储，从而为 Standard Edition 做好准备。
    
- [安装 Business 服务器拓扑中的服务器上的 Skype](install-skype-for-business-server.md) ： 拓扑加载到中央管理存储并 Active Directory 知道哪些服务器将执行哪些角色后，需要在每个安装 Business Server system 的 Skype拓扑中的服务器。
    
- [验证 Skype 业务服务器中的拓扑](verify-the-topology.md)： 发布的拓扑和业务服务器系统组件安装在每个拓扑中的服务器上的 Skype 后，即可验证拓扑是否按预期方式工作。 这包括验证的配置传播到所有 Active Directory 服务器，以便整个域知道 for Business 的 Skype 位于域中。
    

