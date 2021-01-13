---
title: 安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要：了解如何为安装 Skype for Business Server 准备环境。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: ef562a56e1129481954f9345a46483156bd1202f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801912"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要：** 了解如何为安装 Skype for Business Server 准备环境。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 位置为：
  
本文将引导你完成 Skype for Business Server 的示例安装。 本文并未尝试介绍执行完整 Skype for Business Server 安装所需的所有过程。 目标是在包含基本"开会"和"共享"功能的窄定义拓扑中提供示例过程。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for Business Server 的安装过程概述

Skype for Business Server 的安装包括许多不同的过程。 使 Skype for Business Server 在你的环境中运行所需的过程取决于你的环境的具体内容。 例如，如果对 DNS 使用 Windows Server，您将受益于添加 DNS 条目的示例过程。 如果使用其他 DNS 系统，则需要按照特定 DNS 系统的过程操作。 本节中的许多过程都是如此。
  
Skype for Business Server 在 Standard Edition 和企业版中可用。 主要区别在于 Standard Edition 不支持 Enterprise Edition 中包含的高可用性功能。 
  
Skype for Business Server 是一种高级产品，具体安装过程很大程度上取决于你的特定环境。 本部分将指导你完成安装产品的常规步骤。 但是，每个过程可能有所不同，具体取决于您的环境和规划决策。 例如，对于小型组织，运行 Skype for Business Server Standard Edition 的单台服务器可能适合，而大型跨国组织可能拥有 50 台服务器，它们位于世界各地的专用于该产品的位置。
  
> [!NOTE]
> 若要了解最新的累积更新，请参阅 [Skype for Business Server 更新](https://support.microsoft.com/kb/3061064)。 安装 CU1 修补程序后，管理员需要执行  `Update-CsAdminRole` cmdlet。 若要通过远程 PowerShell 访问新的 GCP cmdlet，需要此 cmdlet。
  
> [!IMPORTANT]
> 本节中的过程是使用一组定义较窄的要求的示例，并假定已做出特定决策。 安装 Skype for Business Server 所需的实际过程可能会非常不同。 仅将本节中的过程用作示例，而不是在每种环境中安装 Skype for Business Server 的分步指南。 
  
首次启动并运行 Skype for Business Server 涉及八个主要步骤。 您应该了解，本节中的示例过程不是安装 Skype for Business Server 所需的唯一过程。 以下八个步骤只是一些示例，可帮助您更好地了解整个过程，并启动并运行基本工作环境。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。 这八个步骤是：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装 Skype for Business Server](install-prerequisites.md) 的必备组件：在包含 Skype for Business Server 拓扑的所有服务器上安装必备组件。 请注意，所有角色的先决条件并不相同。 例如，提供前端角色的服务器具有一组先决条件，而提供控制器角色的服务器具有不同的一组先决条件。 有关详细信息，请参阅先决条件规划文档。
    
- [在 Skype for Business Server](create-a-file-share.md) 中创建文件共享：创建供整个 Skype for Business Server 拓扑中的服务器使用的文件共享。
    
- [在 Skype for Business Server](install-administrative-tools.md) 中安装管理工具：管理工具包括拓扑生成器和控制面板。 必须在拓扑中的至少一台服务器上安装管理工具，或在运行支持 Skype for Business Server 的 Windows OS 版本的 64 位管理工作站上安装管理工具。
    
- [为 Skype for Business Server](prepare-active-directory.md) 准备 Active Directory：Skype for Business Server 与 Active Directory 紧密配合。 必须准备 Active Directory 域以使用 Skype for Business Server。 可以通过部署向导完成此操作，并且仅对域执行一次此操作。 这是因为该过程将创建组并修改域，并且只需执行一次此操作。
    
- [为 Skype for Business Server](create-dns-records.md) 创建 DNS 记录：为了使 Skype for Business Server 正常工作，必须设置大量 DNS 设置。 这样，客户端就知道如何访问服务，并且服务器知道彼此。 每个部署只需完成一次这些设置，因为分配 DNS 条目后，它在整个域中都可用。
    
- [在 Skype for Business Server](create-and-publish-new-topology.md) 中创建新拓扑：必须先创建并发布拓扑，然后才能在拓扑中的每台服务器上安装 Skype for Business Server 系统。 发布拓扑时，将拓扑信息加载到中央管理存储数据库中。 如果这是 Enterprise Edition 池，则首次发布新拓扑时将创建中央管理存储数据库。 如果这是 Standard Edition，则需要在发布拓扑之前从部署向导运行"准备第一个 Standard Edition Server"过程。 这将通过安装 Express Edition SQL Server并创建中央管理存储来准备 Standard Edition。
    
- 在拓扑中的服务器上安装[Skype for Business Server：](install-skype-for-business-server.md)一旦拓扑加载到中央管理存储，并且 Active Directory 知道哪些服务器将执行哪些角色，则需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。
    
- 在[Skype for Business Server](verify-the-topology.md)中验证拓扑：在拓扑中每台服务器上发布拓扑并安装 Skype for Business Server 系统组件后，即可验证拓扑是否正常工作。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域知道 Skype for Business 在域中可用。
    

