---
title: 适用于 Skype for Business Server 2015 核心基础结构的最佳做法
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 你可能已经着手设计系统容错能力，做法有：确保硬件冗余、防止断电、例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅您 Skype 业务服务器基础架构，而且您的整个网络中获益。 如果不实现这些做法，我们建议您这样做之前业务服务器部署 Skype。
ms.openlocfilehash: 9d79f98ebc66807f21f8d1eef468efc400dd5fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 核心基础结构的最佳做法
 
你可能已经着手设计系统容错能力，做法有：确保硬件冗余、防止断电、例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅您 Skype 业务服务器基础架构，而且您的整个网络中获益。 如果不实现这些做法，我们建议您这样做之前业务服务器部署 Skype。
  
要帮助您 Skype 业务服务器部署中的服务器免受意外或有意的伤害可能会导致停机，可采取下列预防措施：
  
- 使用安全更新使服务器保持最新状态。 订阅 Microsoft 安全性通知服务来帮助你确保收到关于任何 Microsoft 产品的安全公告发布的最新通知。 若要订阅，请转到[Microsoft 技术安全通知网站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。
    
- 确保正确设置访问权限。
    
- 将服务器部署在可阻止未经授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。
    
- 我们建议您禁用不要求您安装 Skype 业务服务器的计算机的 Windows Server 操作系统服务。
    
- 除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。
    
- 除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。 很容易就能发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。
    

