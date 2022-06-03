---
title: 安装 Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要：了解如何为安装Skype for Business Server准备环境。
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860583"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**总结：** 了解如何为安装Skype for Business Server准备环境。
  
本文将指导你完成Skype for Business Server的示例安装。 本文不尝试涵盖执行完整Skype for Business Server安装所需的所有过程。 目标是在包含基本见面和共享功能的狭义定义拓扑中提供示例过程。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Server的安装过程概述

安装Skype for Business Server包括许多不同的过程。 在环境中运行Skype for Business Server所需的过程取决于环境的具体情况。 例如，如果使用 Windows Server for DNS，则将受益于添加 DNS 条目的示例过程。 如果将另一个系统用于 DNS，则需要遵循特定 DNS 系统的过程。 对于本部分中的许多过程，情况确实如此。
  
Skype for Business Server在Standard Edition和Enterprise Edition中可用。 主要区别在于，Standard Edition不支持Enterprise Edition随附的高可用性功能。 
  
Skype for Business Server是一种高级产品，确切的安装过程在很大程度上取决于你的具体情况。 本部分将指导你完成安装产品的常规步骤。 但是，每个过程可能因环境和规划决策而异。 例如，对于小型组织来说，单个服务器，运行Skype for Business Server Standard Edition可能是合适的，而大型跨国组织可能在世界各地拥有 50 台专用于该产品的服务器。
  
> [!NOTE]
> 若要了解最新的累积更新，请参阅[Skype for Business Server更新](https://support.microsoft.com/kb/3061064)。 安装 CU1 修补程序后，管理员需要执行  `Update-CsAdminRole` cmdlet。 若要通过远程 PowerShell 访问新的 GCP cmdlet，需要此 cmdlet。
  
> [!IMPORTANT]
> 本部分中的过程是使用一组狭义定义的要求的示例，并假定已做出具体决定。 安装Skype for Business Server的实际过程可能大不相同。 仅将本部分中的过程用作示例，而不是作为在每个环境中安装Skype for Business Server的分步指南。 
  
首次启动和运行Skype for Business Server涉及八个主要步骤。 应了解本部分中的示例过程并不是安装Skype for Business Server所需的唯一过程。 以下八个步骤只是帮助你更好地了解整个过程并启动和运行基本工作环境的示例。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 这八个步骤是：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装Skype for Business Server的先决条件](install-prerequisites.md)：在构成Skype for Business Server拓扑的所有服务器上安装先决条件。 请注意，所有角色的先决条件都不一样。 例如，提供前端角色的服务器具有一组先决条件，而提供导演角色的服务器具有一组不同的先决条件。 有关更多详细信息，请参阅先决条件规划文档。
    
- [在Skype for Business Server中创建文件共享](create-a-file-share.md)：创建将在整个Skype for Business Server拓扑中由服务器使用的文件共享。
    
- [在Skype for Business Server中安装管理工具](install-administrative-tools.md)：管理工具包括拓扑生成器和控制面板。 必须在拓扑中的至少一台服务器上安装管理工具，或者在运行支持Skype for Business Server的Windows OS 版本的 64 位管理工作站上安装管理工具。
    
- [为Skype for Business Server准备 Active Directory](prepare-active-directory.md)：Skype for Business Server与 Active Directory 密切合作。 必须准备 Active Directory 域才能使用Skype for Business Server。 可以通过部署向导执行此操作，并且仅对域执行一次操作。 这是因为该过程会创建组并修改域，并且只需执行一次操作。
    
- [为Skype for Business Server创建 DNS 记录](create-dns-records.md)：为了使Skype for Business Server正常工作，必须设置多个 DNS 设置。 这样，客户端就知道如何访问服务，服务器彼此了解。 每个部署只需完成一次这些设置，因为分配 DNS 条目后，它在整个域中可用。
    
- [在Skype for Business Server中创建和发布新拓扑](create-and-publish-new-topology.md)：在拓扑中的每个服务器上安装Skype for Business Server系统之前，必须创建拓扑并发布它。 发布拓扑时，会将拓扑信息加载到中央管理Microsoft Store数据库中。 如果这是一个Enterprise Edition池，则会在首次发布新拓扑时创建中央管理Microsoft Store数据库。 如果Standard Edition，则在发布拓扑之前，需要从部署向导运行“准备第一Standard Edition服务器”进程。 这将通过安装 SQL Server Express Edition 实例并创建中央管理Microsoft Store来准备Standard Edition。
    
- [在拓扑中的服务器上安装Skype for Business Server](install-skype-for-business-server.md)：将拓扑加载到中央管理Microsoft Store，Active Directory 知道哪些服务器将执行哪些角色，需要在拓扑中的每个服务器上安装Skype for Business Server系统。
    
- [验证Skype for Business Server中的拓扑](verify-the-topology.md)：发布拓扑并在拓扑中的每个服务器上安装Skype for Business Server系统组件后，即可验证拓扑是否按预期工作。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域知道域中提供了Skype for Business。
    

