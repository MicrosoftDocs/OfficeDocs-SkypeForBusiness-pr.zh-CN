---
title: 安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '摘要: 了解如何为安装 Skype for Business 服务器准备环境。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: f15a305a660586e017984a171db217636e2e09ff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244333"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要:** 了解如何为安装 Skype for Business 服务器准备环境。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
本文将指导你完成 Skype for Business 服务器的安装示例。 本文不会尝试涵盖执行完整的 Skype for Business 服务器安装所需的所有过程。 目的是在包含基本会议和共享功能的狭义定义拓扑中提供过程示例。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for business 服务器安装过程概述

Skype for business 服务器的安装包括许多不同的过程。 获取在环境中运行的 Skype for business 服务器所需的过程取决于你的环境的具体细节。 例如，如果您为 DNS 使用 Windows Server，则可在提供的添加 DNS 条目示例过程中获益。 如果您为 DNS 使用其他系统，则需要采用适用于特定 DNS 系统的过程。 本节中介绍的许多过程皆是如此。
  
Skype for business 服务器在标准版和企业版中可用。 主要区别在于，Standard Edition 不支持 Enterprise Edition 中包含的高可用性功能。 
  
Skype for Business 服务器是一种高级产品, 准确的安装过程在特定情况下非常有用。 本节概述了该产品的一般安装步骤。 但是，每个过程可能都有所不同，具体取决于您的环境和规划决策。 例如, 对于小型组织, 运行 Skype for business Server Standard Edition 可能是合适的, 而大型跨国组织可能在世界各地的50服务器上专用于产品。
  
> [!NOTE]
> 若要了解有关累积更新的最新信息, 请参阅[Skype For Business 服务器更新](https://support.microsoft.com/en-us/kb/3061064)。 在安装 CU1 修补程序后, 管理员需要执行`Update-CsAdminRole` cmdlet。 需要此 cmdlet 才能通过远程 PowerShell 访问新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本节中的过程仅用作示例，其定义了一组狭窄的要求，并且假定已制定了特定的决策。 安装 Skype for Business 服务器所需的实际过程可能会有很大的不同。 本部分中的过程仅用作示例, 而不是在每个环境中安装 Skype for Business 服务器的分步指南。 
  
第一次获取 Skype for business 服务器并运行时涉及八个主要步骤。 您应了解本部分中的示例过程不是安装 Skype for Business 服务器所需的唯一过程。 可通过以下八个示例步骤来更好地理解总体流程和让基本的工作环境上线运行。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 这八个步骤包括：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装 skype for Business server 的先决条件](install-prerequisites.md): 在组成 Skype For business server 拓扑的所有服务器上安装先决条件。 注意，所有角色的先决条件并不一定相同。 例如，提供前端角色的服务器具备一组先决条件，而提供控制器角色的服务器具备另一组先决条件。 有关更多详细信息，请参阅先决条件规划文档。
    
- [在 skype For Business server 中创建文件共享](create-a-file-share.md): 创建将由整个 Skype For business server 拓扑中的服务器使用的文件共享。
    
- [在 Skype For Business 服务器中安装管理工具](install-administrative-tools.md): 管理工具包括拓扑生成器和控制面板。 必须在拓扑中至少有一台服务器上安装管理工具, 或者在运行 Skype for business 服务器支持的 Windows 操作系统版本的64位管理工作站中安装管理工具。
    
- [为 skype for Business 服务器准备 Active directory](prepare-active-directory.md) : skype For business 服务器与 Active directory 密切协作。 必须准备 Active Directory 域才能使用 Skype for Business 服务器。 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。
    
- [为 skype for Business 服务器创建 DNS 记录](create-dns-records.md): 为了使 Skype For business 服务器正常工作, 必须有大量 DNS 设置。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。
    
- [在 Skype For Business server 中创建和发布新拓扑](create-and-publish-new-topology.md): 在拓扑中的每台服务器上安装 Skype For business Server 系统之前, 必须创建一个拓扑并将其发布。 发布拓扑时，拓扑信息会载入中央管理存储数据库。 如果这是 Enterprise Edition 池，您将在初次发布新拓扑时创建中央管理存储数据库。 如果是 Standard Edition，则需要运行部署向导中的“准备第一个 Standard Edition Server”过程，之后才能发布拓扑。 这将安装 SQL Server Express Edition 实例，并创建中央管理存储，从而为 Standard Edition 做好准备。
    
- 在[拓扑中的服务器上安装 Skype For Business 服务器](install-skype-for-business-server.md): 将拓扑加载到中央管理存储并且 Active Directory 知道哪些服务器将执行哪些角色后, 你需要在每个服务器上安装 Skype For business server 系统拓扑中的服务器。
    
- [验证 Skype For Business 服务器中的拓扑](verify-the-topology.md): 在已发布拓扑以及拓扑中的每台服务器上安装了 Skype For business Server 系统组件后, 即可验证拓扑是否按预期工作。 这包括验证配置是否已传播到所有 Active Directory 服务器, 以便整个域知道 Skype for business 在域中可用。
    

