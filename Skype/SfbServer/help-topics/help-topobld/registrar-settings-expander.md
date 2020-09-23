---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217153"
---
# <a name="registrar-settings-expander"></a>注册器设置扩展器
 
复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。
  
在 Survivable Branch Appliance 或 Survivable Branch Server 的“编辑属性”**** 对话框的“复原”**** 部分，可以更改以下设置：
  
- **关联的用户服务和备份注册器池** 在下拉列表中，选择要充当 Survivable 分支设备或 Survivable 分支服务器的备份注册器的 Enterprise Edition 前端池或 Standard Edition 前端服务器。
    
- **启用故障转移和故障回复** 选择 "此设置" 可允许自动检测失败的注册器，并自动确定主注册器已备份并准备好恢复注册器进程。
    
- ** (sec) 的故障检测间隔 ** 键入在确定主注册器失败之前应经过的秒数。 默认值为 120 秒。 如果选择 " **启用故障转移和故障回复**"，则此字段是必需的。
    
- ** (sec) 的回退检测间隔 ** 键入在确定主注册器已备份之前应经过的秒数。 默认值为240秒。 如果选择 " **启用故障转移和回退**"，则此字段是必需的。
    
> [!IMPORTANT]
> 定义故障检测时间间隔和回退检测时间间隔时，请注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的时间间隔。主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。 
  

