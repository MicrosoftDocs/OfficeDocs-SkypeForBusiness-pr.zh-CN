---
title: Skype for Business Server 中核心基础结构的最佳实践
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 您可能已经着手设计系统容错能力了，做法有：确保硬件冗余，防止断电，例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅对 Skype for Business Server 基础结构，而且对整个网络都大有益处。 如果你尚未实施这些做法，我们建议你在部署 Skype for Business Server 之前这样做。
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832242"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Skype for Business Server 中核心基础结构的最佳实践
 
您可能已经着手设计系统容错能力了，做法有：确保硬件冗余，防止断电，例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅对 Skype for Business Server 基础结构，而且对整个网络都大有益处。 如果你尚未实施这些做法，我们建议你在部署 Skype for Business Server 之前这样做。
  
为了帮助保护 Skype for Business Server 部署中的服务器免受可能导致停机的意外或故意损害，请采取以下预防措施：
  
- 使用安全更新使服务器保持最新状态。 订阅 Microsoft 安全性通知服务有助于确保您收到任何 Microsoft 产品的安全公告发布的最新通知。 若要订阅，请转到 [Microsoft 技术安全通知网站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。
    
- 确保正确设置访问权限。
    
- 将服务器部署在可防止未授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。
    
- 建议在安装 Skype for Business Server 的计算机上禁用不需要的 Windows Server 操作系统服务。
    
- 除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。
    
- 除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。 可以轻松发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。
    

