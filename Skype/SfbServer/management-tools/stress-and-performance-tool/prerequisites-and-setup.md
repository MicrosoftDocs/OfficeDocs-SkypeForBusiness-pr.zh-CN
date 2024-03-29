---
title: 总线压力和性能Skype组件的先决条件和设置
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 压力和性能工具的要求或先决条件。 如何安装或设置压力和性能工具。
ms.openlocfilehash: ec7e2b66427d360a9d54c38146289e4d08f9238d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399616"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>总线压力和性能Skype组件的先决条件和设置
 
Skype for Business Server 2015 压力和性能工具的要求或先决条件。 如何安装或设置压力和性能工具。
  
在运行压力和性能工具之前，我们具有以下需要了解的硬件、软件和系统配置要求：
  
- [客户端硬件要求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [客户端软件要求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [配置要求](prerequisites-and-setup.md#ConfigReqs)
    
此外，我们在下面还有一个部分用于安装 [Skype for Business Server 2015 压力和性能工具](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>客户端硬件要求
<a name="ClientHardwareReqs"> </a>

针对 Skype for Business Server 2015 部署运行压力和性能工具时，至少需要满足测试中每 4500 个用户的硬件要求：
  
- 1 GB 网络适配器
    
- 8 GB RAM
    
- 2 个双核 CPU
    
## <a name="client-software-requirements"></a>客户端软件要求
<a name="ClientSoftwareReqs"> </a>

压力和性能工具支持的操作系统包括：
  
- Windows Server 2012
    
- Windows Server 2008 (64 位) 
    
此外，计算机还需要满足以下软件要求：
  
- 需要安装 Microsoft .NET 4.5 Framework。 [在此处下载 .Net 4.5 Framework。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- 你需要在桌面体验中启用桌面Windows。
    
- 你将需要安装 Microsoft Visual C++ 2013 (x64) 。 [在此处Visual C++ 2013](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 你需要成功部署 Skype for Business Server 2015。
    
## <a name="configuration-requirements"></a>配置要求
<a name="ConfigReqs"> </a>

你需要完成以下附加配置，以成功运行压力和性能工具：
  
- 您需要以 Domain 或 Local Administrator 的组的成员登录到服务器。
    
- 不能将 Skype for Business Server 2015 用户创建工具 (UserProvisioningTool.exe) 安装在用户帐户将驻留的任何前端服务器或 Standard Edition 服务器上。
    
- 多次运行用户创建工具时，启用了 Microsoft 统一通信的每个用户都需要有唯一的电话号码。
    
- 页面文件大小应进行系统管理，否则需要至少是计算机系统中 RAM 容量的 1.5 倍。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安装 Skype for Business Server 2015 压力和性能工具
<a name="Installing"> </a>

安装非常简单。 您需要在要用于模拟用户流量的每个客户端计算机上以及您将创建用户和联系人的每个池中的前端服务器上运行 Windows Installer 文件 **CapacityPlanningTool.msi**。
  
若要下载.msi脚本以及其他文章中提及的示例脚本，请转到下载中心链接：[Skype for Business Server 2015，压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

