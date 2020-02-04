---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 复原功能为注册机构池提供高可用性和灾难恢复。 通过在主注册机出现故障的情况下提供备份注册机构，备份注册机构可以接管失败的注册机构，从而允许用户登录和通信。 用户可能会遇到缩减功能，具体取决于使用主注册器失败的系统。
ms.openlocfilehash: cc025bdd09026ac3c3b15d2408d0c99b3494a04f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688035"
---
# <a name="registrar-settings-expander"></a>注册器设置扩展器
 
复原功能为注册机构池提供高可用性和灾难恢复。 通过在主注册机出现故障的情况下提供备份注册机构，备份注册机构可以接管失败的注册机构，从而允许用户登录和通信。 用户可能会遇到缩减功能，具体取决于使用主注册器失败的系统。
  
在 Survivable 分支装置或 Survivable 分支服务器的 "**编辑属性**" 对话框的 "**弹性**" 部分中，您可以更改以下设置：
  
- **关联的用户服务和备份注册机构池**在下拉列表中，选择要用作 Survivable 分支装置或 Survivable 分支服务器的备份注册机构的企业版前端池或标准版前端服务器。
    
- **启用故障转移和故障回复**选择此设置以允许自动检测失败的注册机构，并自动确定主注册机构是否已备份并准备好继续注册过程。
    
- **故障检测间隔（秒）** 键入在确定主注册机构失败之前应经过的秒数。 默认值为120秒。 如果选择 "**启用故障转移和故障回复**"，则此字段是必需的。
    
- **回退检测间隔（秒）** 键入在确定主注册器备份之前应经过的秒数。 默认值为240秒。 如果选择 "**启用故障转移和回退**"，则此字段是必需的。
    
> [!IMPORTANT]
> 当您定义 "故障检测间隔" 和 "回退检测间隔" 时，请注意不要输入一个时间间隔，如果注册机构在短时间内无法响应，则会导致故障转移和回退发生。 主注册器可能不会根据加载池或服务器的短时间进行响应。 
  

