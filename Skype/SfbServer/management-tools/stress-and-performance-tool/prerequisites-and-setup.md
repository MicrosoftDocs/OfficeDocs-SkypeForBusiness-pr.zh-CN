---
title: Skype for Business Stress and Performance Tool 的先决条件和设置
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 Stress and Performance Tool 的要求或先决条件。 如何安装或设置 Stress and Performance Tool。
ms.openlocfilehash: 9e59c314b546cf0e9204047eb9a86096fbdd5cd8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Business Stress and Performance Tool 的先决条件和设置
 
Skype for Business Server 2015 Stress and Performance Tool 的要求或先决条件。 如何安装或设置 Stress and Performance Tool。
  
在运行 Stress and Performance Tool 之前，你需要了解下面的硬件、软件和系统配置要求：
  
- [客户机硬件要求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [客户端软件要求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [配置要求](prerequisites-and-setup.md#ConfigReqs)
    
此外，还有下面的部分[安装 Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>客户端硬件要求
<a name="ClientHardwareReqs"> </a>

在对 Skype for Business Server 2015 部署运行 Stress and Performance Tool 时，至少需对测试中的每 4500 个用户满足以下硬件要求：
  
- 1 GB 的网络适配器
    
- 8 GB RAM
    
- 2 个双核 CPU
    
## <a name="client-software-requirements"></a>客户端软件要求
<a name="ClientSoftwareReqs"> </a>

Stress and Performance Tool 支持的操作系统有：
  
- Windows Server 2012
    
- Windows Server 2008（64 位）
    
此外，计算机还需满足以下软件要求：
  
- 需要安装 Microsoft .NET 4.5 Framework。 [下载.Net 4.5 以下框架。](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- 需要在 Windows 中启用桌面体验功能。
    
- 需要安装 Microsoft Visual C++ 2013 (x64)。 [在此处下载 Visual C++ 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- 需要成功部署 Skype for Business Server 2015。
    
## <a name="configuration-requirements"></a>配置要求
<a name="ConfigReqs"> </a>

需要先完成这些附加配置，才能成功运行 Stress and Performance Tool：
  
- 你需要以域或本地管理员组成员的身份登录服务器。
    
- 你无法在用户帐户所在的任何前端服务器或 Standard Edition 服务器上安装 Skype for Business Server 2015 User Creation 工具 (UserProvisioningTool.exe)。
    
- 多次运行 User Creation 工具时，为 Microsoft 统一通信启用的每个用户都需要有一个唯一电话号码。
    
- 页面文件大小应由系统管理，或至少为计算机系统中 RAM 量的 1.5 倍。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安装 Skype for Business Server 2015 Stress and Performance Tool
<a name="Installing"> </a>

安装非常简单。 你需要在要用来模拟用户流量的每台客户端计算机上以及要创建用户和联系人的每个池中的前端服务器上运行 Windows 安装程序文件 **CapacityPlanningTool.msi**。
  
进入下载中心链接下载.msi 文件，以及我们其他文章中提到的示例脚本： [Skype 业务服务器 2015年、 压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

