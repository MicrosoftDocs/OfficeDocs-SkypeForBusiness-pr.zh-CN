---
title: 设备配置新建或编辑现有的
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 在新设备配置或编辑设备配置页上，您可以创建或修改的用于管理业务电话版的 Skype 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a>设备配置：创建新的或编辑现有的
 
在**新设备配置**或**编辑设备配置**页上，您可以创建或修改的用于管理业务电话版的 Skype 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建设备配置**”或“**编辑设备配置**”页上执行以下任务：
  
- 添加新的设备配置。
    
- 修改现有设备配置的属性。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **作用域**标识设备配置的范围 （全局或站点）。
    
- **名称**您可以添加或修改设备配置的名称。
    
- **SIP 安全**您可以配置传输和身份验证要求 Skype 的商务电话版设备。 您可以从以下选项中进行选择：
    
  - **低**允许任何类型的授权或传输。
    
  - **中等深浅**NTLM 或 Kerberos，则需要进行用户身份验证。
    
  - **高**NTLM 或 Kerberos，则需要进行用户身份验证，不需要对 SIP 连接 TLS。
    
- **日志记录级别**您可以启用日志记录在 UC 设备上。 有效值为： 关闭;低;中等;和高。 默认值是禁用。
    
- **语音服务质量 (QoS)**您可以指定分配给 Skype 业务电话版设备产生的语音流量的 DSCP 值。 默认值为 40。 但是，40 不值通常用于音频通信;相反，音频通信几乎总是被标上 DSCP 代码 46 中。 为了维持整个网络的一致性，您可能希望将此值更改为 46。
    
- **电话锁定**您可以指定 UC 手机将自动将自己锁定在一段指定的不活动时间之后。 您可以配置的设置如下：
    
  - **实施设备锁定**您可以强制执行设备通过选中该复选框锁定。
    
  - **小针长度**您可以指定的最小长度为用于解锁手机的个人身份号 (PIN)。 PIN 长度的范围是到 15 个四位数字。 默认长度为 6 位数字。
    
  - **电话锁定超时**您可以自己指定前电话锁定时间的最小长度。 超时值的范围是 0 到 60 分钟;默认值为 10 分钟。 格式： 分： 秒输入的值。
    
## <a name="see-also"></a>另请参阅

#### 

[设备配置](device-configuration.md)
#### 

[一组 CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

