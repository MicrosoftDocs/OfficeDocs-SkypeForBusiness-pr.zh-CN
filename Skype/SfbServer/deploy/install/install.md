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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要：了解如何为安装 Skype for Business Server 准备环境。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042379"
---
# <a name="install-skype-for-business-server"></a>安装 Skype for Business Server
 
**摘要：** 了解如何为安装 Skype for Business Server 准备环境。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。
  
本文将引导您完成 Skype for Business Server 的安装示例。 本文不会尝试涵盖执行完整的 Skype for Business Server 安装所需的所有过程。 目标是在定义了狭窄的拓扑中提供示例过程，其中包括基本的匹配和共享功能。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype for business Server 的安装过程概述

Skype for Business Server 的安装包括许多不同的过程。 获取在环境中运行的 Skype for business 服务器所需的过程取决于环境的具体细节。 例如，如果您使用 Windows Server for DNS，您将受益于添加 DNS 条目的示例过程。 如果为 DNS 使用其他系统，则需要遵循特定 DNS 系统的过程。 本节中的许多过程都是如此。
  
Skype for Business Server 适用于 Standard Edition 和 Enterprise Edition。 主要区别在于，Standard Edition 不支持企业版中附带的高可用性功能。 
  
Skype for Business Server 是一种高级产品，确切的安装过程在特定情况下非常有用。 本部分将引导您完成安装产品的常规步骤。 但是，每个过程可能会有所不同，具体取决于您的环境和规划决策。 例如，对于小型组织，运行 Skype for Business Server Standard Edition 可能适用，而大型跨国组织可能在全球专用于产品的位置上有50台服务器。
  
> [!NOTE]
> 若要了解最新的累积更新，请参阅[Skype For Business Server 更新](https://support.microsoft.com/kb/3061064)。 安装 CU1 修补程序后，管理员需要执行`Update-CsAdminRole` cmdlet。 此 cmdlet 是通过远程 PowerShell 访问新的 GCP cmdlet 所必需的。
  
> [!IMPORTANT]
> 本部分中的过程是使用定义较窄的一组要求并假设已做出特定决策的示例。 安装 Skype for Business Server 所需的实际过程可能会有很大不同。 仅在每个环境中使用此部分中的过程作为示例，而不是作为安装 Skype for Business Server 的分步指南。 
  
第一次准备 Skype for business Server 并运行时涉及8个主要步骤。 您应了解本部分中的示例过程不是安装 Skype for Business Server 所需的唯一过程。 以下八个步骤只是帮助您更好地了解整体过程并使基本工作环境正常运行的简单示例。 您可以按任意顺序执行步骤1至5。 但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 这8个步骤如下：
  
![安装过程概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安装 skype for Business server 的必备组件](install-prerequisites.md)：在组成 Skype For business server 拓扑的所有服务器上安装必备组件。 请注意，所有角色的先决条件并不相同。 例如，提供前端角色的服务器具有一组先决条件，提供控制器角色的服务器具有一组不同的先决条件。 有关更多详细信息，请参阅必备项规划文档。
    
- [在 skype For Business server 中创建文件共享](create-a-file-share.md)：创建将由整个 Skype For business server 拓扑中的服务器使用的文件共享。
    
- [在 Skype For Business Server 中安装管理工具](install-administrative-tools.md)：管理工具包括拓扑生成器和 "控制面板"。 必须在拓扑中至少一台服务器上安装管理工具，或者在运行 Skype for Business Server 支持的 Windows OS 版本的64位管理工作站上安装管理工具。
    
- [为 skype for Business Server 准备 Active Directory](prepare-active-directory.md) ： Skype For business Server 与 Active directory 紧密协作。 您必须准备 Active Directory 域才能与 Skype for Business Server 配合使用。 您可以通过部署向导执行此操作，仅对域执行一次此操作。 这是因为该过程会创建组并修改域，您只需执行一次此操作。
    
- [为 skype for Business Server 创建 DNS 记录](create-dns-records.md)：为了使 Skype For business server 正常工作，必须有大量 DNS 设置。 这样，客户端就知道如何访问彼此相关的服务和服务器。 这些设置只需要针对每个部署完成一次，因为一旦分配了 DNS 条目，它就会在整个域中可用。
    
- [在 skype For Business server 中创建和发布新拓扑](create-and-publish-new-topology.md)：在拓扑中的每台服务器上安装 Skype For business Server 系统之前，必须创建一个拓扑并将其发布。 发布拓扑时，会将拓扑信息加载到中央管理存储数据库中。 如果这是一个 Enterprise Edition 池，您将在首次发布新的拓扑时创建中央管理存储数据库。 如果这是 Standard Edition，则需要在发布拓扑之前，先从部署向导运行准备第一个 Standard Edition Server 进程。 这将通过安装 SQL Server Express Edition 实例并创建中央管理存储来准备标准版。
    
- 在[拓扑中的服务器上安装 Skype For Business Server](install-skype-for-business-server.md) ：一旦将拓扑加载到中央管理存储中，并且 Active Directory 知道哪些服务器将执行哪些角色，您需要在拓扑中的每台服务器上安装 Skype For business server 系统。
    
- [验证 Skype For Business server 中的拓扑](verify-the-topology.md)：在发布拓扑后，在拓扑中的每台服务器上安装 Skype For business Server 系统组件后，即可验证拓扑是否按预期正常运行。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域都知道 Skype for Business 在域中可用。
    

