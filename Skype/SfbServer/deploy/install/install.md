---
title: 安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: 摘要：了解如何准备环境以安装Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：。
ms.openlocfilehash: 6b99befcafea7467d0a7211b4e18add7395ebb75
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850345"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要：** 了解如何准备环境以安装Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) ：。
  
本文将指导你完成示例安装Skype for Business Server。 本文并未尝试涵盖执行完整安装过程所需的Skype for Business Server过程。 目标是在包含基本"会面和共享"功能的窄定义拓扑中提供示例过程。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>安装过程概述Skype for Business Server

安装 Skype for Business Server包括许多不同的过程。 在环境中Skype for Business Server运行所需的过程取决于环境的具体内容。 例如，如果将 Windows Server 用于 DNS，您将受益于添加 DNS 条目的示例过程。 如果对 DNS 使用另一个系统，则需要按照特定 DNS 系统的过程操作。 本节中的许多过程都如此。
  
Skype for Business Server在 Standard Edition 和 Enterprise Edition 中提供。 主要区别在于，Standard Edition不支持应用程序中包含的高可用性Enterprise Edition。 
  
Skype for Business Server是一种高级产品，具体的安装过程很大程度上取决于你的特定环境。 本部分将指导你完成安装产品的常规步骤。 但是，每个过程可能有所不同，具体取决于您的环境和规划决策。 例如，对于小型组织，运行 Skype for Business Server Standard Edition 可能适合，而大型跨国组织可能拥有 50 台服务器，它们位于世界各地的位置专用于该产品。
  
> [!NOTE]
> 若要了解最新的累积更新，请参阅更新[Skype for Business Server。](https://support.microsoft.com/kb/3061064) 安装 CU1 修补程序后，管理员需要执行  `Update-CsAdminRole` cmdlet。 需要此 cmdlet 才能通过远程 PowerShell 访问新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本节中的过程用作使用一组定义较窄的要求的示例，并假定已做出特定决策。 安装安装程序所需的实际Skype for Business Server可能会非常不同。 请仅将本节中的过程用作示例，而不是将本节中的过程用作在每种环境中Skype for Business Server的分步指南。 
  
首次Skype for Business Server启动并运行包括八个主要步骤。 您应该了解，本节中的示例过程不是安装 Skype for Business Server。 以下八个步骤只是一些示例，可帮助您更好地了解整个过程，并启动并运行基本工作环境。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按照图中的概述顺序执行步骤 6、7 和 8 以及步骤 1 到步骤 5 之后。 这八个步骤是：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装以下Skype for Business Server：](install-prerequisites.md)在包含拓扑的所有服务器上安装Skype for Business Server必备组件。 请注意，所有角色的先决条件并不相同。 例如，提供前端角色的服务器具有一组先决条件，而提供控制器角色的服务器具有不同的先决条件集。 有关详细信息，请参阅先决条件规划文档。
    
- [Create a file share in Skype for Business Server](create-a-file-share.md) ： Create a file share that will be used by servers throughout the Skype for Business Server topology.
    
- [在 Skype for Business Server](install-administrative-tools.md)中安装管理工具：管理工具包括拓扑生成器和控制面板。 必须在拓扑中的至少一台服务器或运行 Windows 操作系统版本的 64 位管理工作站上安装管理工具，Skype for Business Server。
    
- [准备 Active Directory Skype for Business Server：Skype for Business Server](prepare-active-directory.md)与 Active Directory 紧密配合。 必须准备 Active Directory 域，以使用Skype for Business Server。 可以通过部署向导完成此操作，并且仅对域执行一次此操作。 这是因为该过程将创建组并修改域，并且只需执行一次。
    
- [为 Skype for Business Server](create-dns-records.md)创建 DNS 记录：为了使Skype for Business Server正常工作，必须设置大量 DNS 设置。 这样，客户端就知道如何访问服务，并且服务器知道彼此。 每个部署只需完成一次这些设置，因为分配 DNS 条目后，它在整个域中都可用。
    
- [Create and publish new topology in Skype for Business Server](create-and-publish-new-topology.md) ： Before you can install the Skype for Business Server system on each the servers in the topology， you must create a topology and publish it. 发布拓扑时，将拓扑信息加载到中央管理存储数据库中。 如果这是一Enterprise Edition池，则首次发布新拓扑时将创建中央管理存储数据库。 如果Standard Edition，则需要在发布拓扑之前从部署向导运行"准备第一Standard Edition服务器"过程。 这将通过安装 Standard Edition Edition 实例并创建中央SQL Server Express存储来准备更新。
    
- 在拓扑中的服务器上安装[Skype for Business Server：](install-skype-for-business-server.md)一旦拓扑加载到中央管理存储，并且 Active Directory 知道哪些服务器将执行哪些角色，则需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。
    
- 在[Skype for Business Server](verify-the-topology.md)中验证拓扑：在拓扑中的每台服务器上发布拓扑并安装 Skype for Business Server 系统组件后，即可确认拓扑是否正常工作。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域知道Skype for Business域中可用。
    

