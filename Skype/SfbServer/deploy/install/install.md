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
description: 摘要：了解如何为 Skype for Business Server 的安装准备环境。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: f15a305a660586e017984a171db217636e2e09ff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244333"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要**：了解如何为 Skype for Business 服务器的安装准备环境。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
本文将引导你完成 Skype for Business Server 的安装示例。 本文并未尝试涵盖完整 Skype for Business Server 安装所需的所有过程。 本文的目的是在包含基本的“会面和共享”功能的已狭义定义拓扑中提供示例过程。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for business Server 安装过程概述

Skype for Business Server 的安装包括许多不同的过程。 使 Skype for Business Server 在环境中正常运行所需的过程根据环境的细节不同而有所不同。 例如，如果您为 DNS 使用 Windows Server，则可在提供的添加 DNS 条目示例过程中获益。 如果您为 DNS 使用其他系统，则需要采用适用于特定 DNS 系统的过程。 本节中介绍的许多过程皆是如此。
  
Skype for Business Server 提供标准版和企业版。 主要区别在于，标准版不支持企业版中包含的高可用性功能。 
  
Skype for Business Server 是一款高级产品，具体的安装流程很大程度上取决于你的具体环境。 本节概述了该产品的一般安装步骤。 但是，每个过程可能都有所不同，具体取决于您的环境和规划决策。 例如，对于小型组织而言，运行 Skype for Business Server 标准版的单台服务器可能比较合适，而对于大型跨国组织而言，可能会在全球范围内设立 50 台服务器来专为该产品服务。
  
> [!NOTE]
> 要了解最新的累积更新，请参阅 [Skype for Business Server 的更新](https://support.microsoft.com/zh-CN/kb/3061064)。 在安装 CU1 修补程序之后，管理员需要执行 `Update-CsAdminRole` cmdlet。 需要此 cmdlet 才能通过远程 PowerShell 访问新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本节中的过程仅用作示例，其定义了一组狭窄的要求，并且假定已制定了特定的决策。 安装 Skype for Business Server 所需的实际过程很可能极为不同。 请仅将本节中的过程用作示例，而非在每个环境中安装 Skype for Business Server 的逐步指南。 
  
首次让 Skype for Business Server 上线运行的过程涉及八个主要步骤。 你应该理解，本节中的示例过程并非是安装 Skype for Business Server 所需的唯一过程。 可通过以下八个示例步骤来更好地理解总体流程和让基本的工作环境上线运行。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 这八个步骤包括：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装 Skype for Business Server 的必备组件](install-prerequisites.md)：在组成 Skype for Business Server 拓扑的所有服务器上安装必备组件。 注意，所有角色的先决条件并不一定相同。 例如，提供前端角色的服务器具备一组先决条件，而提供控制器角色的服务器具备另一组先决条件。 有关更多详细信息，请参阅先决条件规划文档。
    
- [在 Skype for Business Server 中创建文件共享](create-a-file-share.md)：创建 Skype for Business Server 拓扑中的服务器将使用的文件共享。
    
- [在 Skype for Business Server 中安装管理工具](install-administrative-tools.md)：管理工具包括拓扑生成器和控制面板。 管理工具必须安装在拓扑中至少一台服务器上或安装在运行 Windows（Skype for Business Server 支持的操作系统版本）的 64 位管理工作站上。
    
- [针对 Skype for Business Server 准备 Active Directory](prepare-active-directory.md)：Skype for Business Server 与 Active Directory 紧密协同工作。 必须准备 Active Directory 域以与 Skype for Business Server 进行协作。 将在部署向导中完成此流程，且仅对该域执行一次该流程。 这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。
    
- [为 Skype for Business Server 创建 DNS 记录](create-dns-records.md)：要使 Skype for Business Server 正常运行，必须完成许多 DNS 设置。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。
    
- [在 Skype for Business Server 中创建和发布新拓扑](create-and-publish-new-topology.md)：必须先创建拓扑并发布，才能在拓扑中的每个服务器上安装 Skype for Business Server 系统。 发布拓扑时，拓扑信息会载入中央管理存储数据库。 如果这是 Enterprise Edition 池，您将在初次发布新拓扑时创建中央管理存储数据库。 如果是 Standard Edition，则需要运行部署向导中的“准备第一个 Standard Edition Server”过程，之后才能发布拓扑。 这将安装 SQL Server Express Edition 实例，并创建中央管理存储，从而为 Standard Edition 做好准备。
    
- [在拓扑中的服务器上安装 Skype for Business Server](install-skype-for-business-server.md)：在拓扑载入中央管理存储，Active Directory 了解哪台服务器将执行哪个角色之后，需要在拓扑内的每台服务器上安装 Skype for Business Server 系统。
    
- [在 Skype for Business Server 中验证拓扑](verify-the-topology.md)：在你发布拓扑并在拓扑中的每台服务器上安装 Skype for Business Server 系统组件后，你便已准备好验证拓扑是否能够按预期运行。 这包括验证配置是否已传播至所有 Active Directory 服务器，使得整个域都知道Skype for Business 在域中可用。
    

