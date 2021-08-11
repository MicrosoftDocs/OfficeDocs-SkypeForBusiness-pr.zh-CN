---
title: 验证配置设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以通过在中央管理存储所在的内部计算机或安装了 Skype for Business Server 2019 核心组件 (OcsCore.msi) 的任何加入域的计算机上运行 Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus cmdlet，验证配置信息是否复制到边缘服务器。
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335742"
---
# <a name="verify-configuration-settings"></a>验证配置设置

您可以通过在中央管理存储所在的内部计算机或安装了 Skype for Business Server 2019 核心组件 (OcsCore.msi) 的任何加入域的计算机上运行 Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet，验证配置信息的复制到边缘服务器。 
  
初始结果可能指示复制的状态为“False”而非“True”。如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。 
  

