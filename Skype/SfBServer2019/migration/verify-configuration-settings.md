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
description: 您可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 Get-csmanagementstorereplicationstatus cmdlet，或在已安装 Skype for Business Server 2019 核心组件（OcsCore.msi）的任何加入域的计算机上运行 Skype for Business Server cmdlet，来验证是否将配置信息复制到边缘服务器。
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752144"
---
# <a name="verify-configuration-settings"></a>验证配置设置

您可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 **get-csmanagementstorereplicationstatus** cmdlet，或在安装了 Skype For business Server 2019 核心组件（OcsCore.msi）的任何加入域的计算机上运行 Skype For business server cmdlet，来验证是否将配置信息复制到边缘服务器。 
  
初始结果可能指示复制的状态为“False”而非“True”。 如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。 
  

