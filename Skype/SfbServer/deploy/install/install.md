---
title: 安装 Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '摘要： 了解如何准备业务服务器 2015年安装 Skype 的环境。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6cb30ef44411705d16ce9175e92a9204d8b09766
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-skype-for-business-server-2015"></a>安装 Skype for Business Server 2015
 
**摘要：**了解如何准备业务服务器 2015年安装 Skype 的环境。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
本文引导您完成示例安装 Skype 业务服务器 2015年个。 这篇文章不会试图覆盖所有需要执行完整的 Skype 业务服务器安装的过程。 目的是在包含基本会议和共享功能的狭义定义拓扑中提供过程示例。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server-2015"></a>为业务服务器 2015年的 Skype 的安装过程概述

Skype 业务服务器的安装过程中包括多个不同的过程。 您需要获得 Skype 业务服务器环境中运行的步骤取决于您环境的具体情况。 例如，如果您为 DNS 使用 Windows Server，则可在提供的添加 DNS 条目示例过程中获益。 如果您为 DNS 使用其他系统，则需要采用适用于特定 DNS 系统的过程。 本节中介绍的许多过程皆是如此。
  
商业服务器 2015年的 Skype 是在标准版和企业版中可用。 主要区别在于，Standard Edition 不支持 Enterprise Edition 中包含的高可用性功能。 
  
Skype 业务服务器是一种高级的产品，并精确安装过程极大地取决于您的特定情况。 本节概述了该产品的一般安装步骤。 但是，每个过程可能都有所不同，具体取决于您的环境和规划决策。 例如，小型企业一台服务器运行业务服务器 2015年标准版 Skype 可能比较适合，虽然大型多国组织可能会在全球致力于该产品的位置使用 50 台服务器。
  
> [!NOTE]
> 要了解有关最新的累积更新，请参阅[更新业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/kb/3061064)。 安装 CU1 修补程序后管理员需要执行`Update-CsAdminRole`cmdlet。 需要此 cmdlet 才能通过远程 PowerShell 访问新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本节中的过程仅用作示例，其定义了一组狭窄的要求，并且假定已制定了特定的决策。 您需要为业务服务器安装 Skype 的实际过程可能会非常不同。 使用中的过程这一节示例中只并不是一个分步指南，Skype 业务服务器安装在每个环境中。 
  
Skype 业务服务器启动并运行第一次涉及八个主要步骤。 您应该了解此节中的示例过程不是所需的业务服务器中安装 Skype 的唯一过程。 可通过以下八个示例步骤来更好地理解总体流程和让基本的工作环境上线运行。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 这八个步骤包括：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装系统必备组件的业务服务器 2015 Skype](install-prerequisites.md) ： 构成 Skype 业务服务器拓扑中的所有服务器上安装系统必备组件。 注意，所有角色的先决条件并不一定相同。 例如，提供前端角色的服务器具备一组先决条件，而提供控制器角色的服务器具备另一组先决条件。 有关更多详细信息，请参阅先决条件规划文档。
    
- [创建一个文件共享中的业务服务器 2015 Skype](create-a-file-share.md) ： 创建将由业务服务器拓扑 Skype 整个服务器的文件共享。
    
- [安装管理工具中的业务服务器 2015 Skype](install-administrative-tools.md) ： 管理工具包括拓扑生成器和控制面板。 必须至少一个服务器拓扑或运行业务服务器为 Skype 支持的 Windows 操作系统版本的 64 位管理工作站上安装管理工具。
    
- [准备业务服务器 2015年的 Skype 的活动目录](prepare-active-directory.md)： Skype 业务服务器的紧密合作与活动目录。 您必须准备使用 Skype 业务服务器的 Active Directory 域。 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。
    
- [创建 DNS 记录业务服务器 2015年的 Skype](create-dns-records.md) ： 使 Skype 业务服务器正常工作，DNS 设置编号必须已存在。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。
    
- [创建并发布新的拓扑结构在 Skype 业务服务器 2015年](create-and-publish-new-topology.md)： 每个拓扑中的服务器上安装 Skype 业务服务器系统之前，您必须创建一个拓扑结构并将其发布。 发布拓扑时，拓扑信息会载入中央管理存储数据库。 如果这是 Enterprise Edition 池，您将在初次发布新拓扑时创建中央管理存储数据库。 如果是 Standard Edition，则需要运行部署向导中的“准备第一个 Standard Edition Server”过程，之后才能发布拓扑。 这将安装 SQL Server Express Edition 实例，并创建中央管理存储，从而为 Standard Edition 做好准备。
    
- [用于在拓扑中的服务器上的业务服务器 2015年安装 Skype](install-skype-for-business-server.md) ： 拓扑载入中央管理存储并 Active Directory 知道哪些服务器将执行哪些角色后，您需要安装 Skype 业务服务器系统上每个拓扑中的服务器。
    
- [验证在商业服务器 2015年的 Skype 的拓扑](verify-the-topology.md)： 发布拓扑和 Skype 业务服务器系统组件安装在每个拓扑中的服务器后，您就可以验证拓扑是否按预期的方式工作. 这包括验证的配置传播到所有 Active Directory 的服务器，以便整个域知道 Skype 业务域中是可用。
    

