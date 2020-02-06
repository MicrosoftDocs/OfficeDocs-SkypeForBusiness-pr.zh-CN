---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For CsManagementStoreReplicationStatus cmdlet 验证配置信息到边缘服务器的复制，或者在任何安装了 Skype for business Server 2019 核心组件（OcsCore）的加入域的计算机。
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812750"
---
# <a name="verify-configuration-settings"></a>验证配置设置

你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For **CsManagementStoreReplicationStatus** cmdlet，或者在安装了 Skype For business Server 2019 核心组件（OcsCore）的任何加入域的计算机上运行 skype For business server，来验证配置信息到边缘服务器的复制。 
  
初始结果可能表明状态为 "False"，而不是 "True" 用于复制。 如果是这样，请运行**CsManagementStoreReplication** cmdlet 并等待复制完成，然后再再次运行**Get CsManagementStoreReplicationStatus** 。 
  

