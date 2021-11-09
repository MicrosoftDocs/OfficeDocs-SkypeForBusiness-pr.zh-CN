---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。
ms.openlocfilehash: 599923fc8b85e57387ff2742a933c60a928a2dde
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837704"
---
# <a name="registrar-settings-expander"></a>注册器设置扩展器
 
复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。
  
在 Survivable Branch Appliance 或 Survivable Branch Server 的“编辑属性”对话框的“复原”部分，可以更改以下设置：
  
- **关联的用户服务和备份注册器池** 在下拉列表中，选择 Enterprise Edition 前端池或 Standard Edition 前端服务器，以用作 Survivable Branch Appliance 或 Survivable Branch Server 的备份注册器。
    
- **启用故障转移和故障回复** 选择此设置可自动检测发生故障的注册器，并自动确定主注册器已备份并准备好恢复注册器进程。
    
- **故障检测间隔 (秒)** 键入在确定主注册器已失败之前应经过的秒数。 默认值为 120 秒。 如果选择"启用故障转移和故障回复 **"，则此字段是必需的**。
    
- **回退检测间隔 (秒)** 键入确定备份主注册器之前应经过的秒数。 默认值为 240 秒。 如果选择"启用故障转移和回退 **"，则此字段是必需的**。
    
> [!IMPORTANT]
> 定义故障检测时间间隔和回退检测时间间隔时，请注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的时间间隔。主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。 
  

