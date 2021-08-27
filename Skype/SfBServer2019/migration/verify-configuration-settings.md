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
ms.localizationpriority: medium
description: 您可以通过在中央管理存储所在的内部计算机或安装了 Skype for Business Server 2019 核心组件 (OcsCore.msi) 的任何加入域的计算机上运行 Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus cmdlet，验证配置信息是否复制到边缘服务器。
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594260"
---
# <a name="verify-configuration-settings"></a>验证配置设置

您可以通过在中央管理存储所在的内部计算机或安装了 Skype for Business Server 2019 核心组件 (OcsCore.msi) 的任何加入域的计算机上运行 Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet，验证配置信息的复制到边缘服务器。 
  
初始结果可能指示复制的状态为“False”而非“True”。如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。 
  

