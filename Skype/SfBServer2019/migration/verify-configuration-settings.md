---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以通过在中央管理存储是位于，或对任何内部计算机上运行业务服务器 2019 Get-csmanagementstorereplicationstatus cmdlet Skype 验证到边缘服务器的配置信息的复制加入域的计算机的业务 Server 2019 核心组件 (OcsCore.msi) 的 Skype 已安装。
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231355"
---
# <a name="verify-configuration-settings"></a>验证配置设置

您可以通过中央管理存储所在，在内部计算机上运行业务服务器 2019 **Get-csmanagementstorereplicationstatus** cmdlet Skype 验证到边缘服务器的配置信息的复制或在其上任何加入域的计算机上安装 Skype 的业务 Server 2019 核心组件 (OcsCore.msi)。 
  
初始结果可能指示的状态为"False"而不是"True"进行复制。 如果是这样，运行**Invoke CsManagementStoreReplication** cmdlet，并允许再次运行**Get-csmanagementstorereplicationstatus**之前完成复制的时间。 
  

