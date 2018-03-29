---
title: 注册设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 恢复注册池提供具有高可用性和灾难恢复能力。 通过在出现故障的主注册，注册可以接管失败的教务主任，在备份时备份注册器允许用户进行登录和通讯。 用户可能会遇到缩减的功能，具体取决于系统出现故障的主注册。
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a>注册设置扩展器
 
恢复注册池提供具有高可用性和灾难恢复能力。 通过在出现故障的主注册，注册可以接管失败的教务主任，在备份时备份注册器允许用户进行登录和通讯。 用户可能会遇到缩减的功能，具体取决于系统出现故障的主注册。
  
在高存活力的分支装置或自动恢复分支服务器**编辑属性**对话框中的**弹性**部分中，您可以更改以下设置：
  
- **关联的用户服务和备份注册器池**在下拉列表中，选择标准版前端服务器是高存活力的分支装置或自动恢复分支服务器作为备份注册器的前端企业版池。
    
- **启用故障转移和故障自动恢复**选择此设置以允许自动检测失败注册和主注册器是备份并且准备好继续注册过程的自动确定。
    
- **故障检测时间间隔 （秒）**键入已确定由主注册器出现故障前应经过的秒数。 默认值为 120 秒。 如果您选择**启用故障转移和故障自动恢复**，则此字段是必需的。
    
- **回退检测间隔 （秒）**键入它取决于备份的主注册前所经过的秒数。 默认值为 240 秒。 此字段是必需的如果您选择**启用故障转移和备用**。
    
> [!IMPORTANT]
> 故障检测间隔和备用检测间隔定义时，要小心，不要输入会导致故障转移时间间隔和后备如果注册机没有响应的短时间内发生。 很可能主要注册可能不响应的短时期内根据加载的池或服务器。 
  

