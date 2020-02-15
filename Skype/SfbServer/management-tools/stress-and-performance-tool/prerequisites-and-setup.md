---
title: Skype for Business 压力和性能工具的先决条件和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 压力和性能工具的要求或先决条件。 如何安装或设置压力和性能工具。
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005977"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Business 压力和性能工具的先决条件和设置
 
Skype for Business Server 2015 压力和性能工具的要求或先决条件。 如何安装或设置压力和性能工具。
  
在运行压力和性能工具之前，我们有以下部分需要了解的硬件、软件和系统配置要求：
  
- [客户端硬件要求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [客户端软件要求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [配置要求](prerequisites-and-setup.md#ConfigReqs)
    
此外，我们还提供了有关[安装 Skype For Business Server 2015 压力和性能工具](prerequisites-and-setup.md#Installing)的部分
  
## <a name="client-hardware-requirements"></a>客户端硬件要求
<a name="ClientHardwareReqs"> </a>

在对 Skype for business Server 2015 部署运行压力和性能工具时，至少需要满足测试中的每个4500个用户的以下硬件要求：
  
- 1个千兆网络适配器
    
- 8 GB RAM
    
- 2个双核 Cpu
    
## <a name="client-software-requirements"></a>客户端软件要求
<a name="ClientSoftwareReqs"> </a>

压力和性能工具的受支持的操作系统是：
  
- Windows Server 2012
    
- Windows Server 2008 （64-位）
    
此外，计算机需要满足以下软件要求：
  
- 你将需要安装 Microsoft .NET 4.5 Framework。 [在此处下载 .Net 4.5 框架。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- 你将需要在 Windows 中启用的 "桌面体验" 功能。
    
- 你将需要安装 Microsoft Visual c + + 2013 （x64）。 [在此处下载 Visual c + + 2013](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 你需要成功部署 Skype for Business Server 2015。
    
## <a name="configuration-requirements"></a>配置要求
<a name="ConfigReqs"> </a>

你将需要执行以下额外配置，以成功运行压力和性能工具：
  
- 您需要以域或本地管理员组的成员身份登录到服务器。
    
- 您无法在用户帐户将驻留的任何前端服务器或 Standard Edition 服务器上安装 Skype for Business Server 2015 用户创建工具（UserProvisioningTool）。
    
- 当用户创建工具运行多次时，为 Microsoft 统一通信启用的每个用户都需要具有唯一的电话号码。
    
- 页面文件大小应由系统管理，或者其他情况下必须至少为计算机系统中的 RAM 量的1.5 倍。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安装 Skype for Business Server 2015 压力和性能工具
<a name="Installing"> </a>

安装更为简单。 您需要在要用于模拟用户通信的每台客户端计算机上运行 Windows Installer 文件**CapacityPlanningTool**，并在要创建用户和联系人的每个池中的前端服务器上运行。
  
若要下载 .msi，以及我们其他文章中提到的示例脚本，请转到下载中心链接： [Skype For Business Server 2015、压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

