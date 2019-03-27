---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 恢复能力提供高可用性和灾难恢复的注册器池。 通过提供发生故障的主注册器，备份注册器可以接管失败的注册器，为备份注册器允许用户登录并进行通信。 用户可能可以体验缩减的功能，具体取决于其系统已失败的主注册器。
ms.openlocfilehash: afe640a5560c11f90381875aa67f5fe25c70044c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881097"
---
# <a name="registrar-settings-expander"></a>注册器设置扩展器
 
恢复能力提供高可用性和灾难恢复的注册器池。 通过提供发生故障的主注册器，备份注册器可以接管失败的注册器，为备份注册器允许用户登录并进行通信。 用户可能可以体验缩减的功能，具体取决于其系统已失败的主注册器。
  
在**编辑属性**对话框的 Survivable Branch Appliance 或 Survivable Branch Server**复原**部分中，您可以更改以下设置：
  
- **关联的用户服务和备份注册器池**在下拉列表中，选择 Enterprise Edition 前端池或 Standard Edition 前端服务器，以用作 Survivable Branch Appliance 或 Survivable Branch Server 备份注册器。
    
- **启用故障转移和故障回复**选择此设置，以注册器和主注册器是备份和已准备好继续注册器过程的自动确定允许自动检测失败。
    
- **故障检测间隔 （秒）** 键入确定主注册器已失败之前应经过的秒的数。 默认值为 120 秒。 如果选择**启用故障转移和故障回复**，则需要此字段。
    
- **回退检测间隔 （秒）** 键入确定备份的主注册器之前应经过的秒的数。 默认值为 240 秒。 如果选择**启用故障转移和回退**，则需要此字段。
    
> [!IMPORTANT]
> 定义故障检测间隔和回退检测间隔时, 是时间的注意不要输入间隔将导致故障转移和回退发生如果注册器没有响应期间较短。 则可能的主注册器可能不响应短期基于加载的池或服务器的时间。 
  

