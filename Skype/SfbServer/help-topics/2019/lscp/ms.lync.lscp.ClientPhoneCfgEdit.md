---
title: 设备配置创建新的或编辑现有的
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 在新的设备配置或编辑设备配置页上，您可以创建或修改用于管理业务 Phone edition 的 Skype 的设置的集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: 9e91313db84a870ef4f85105ddf2b2138d8948aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997928"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>设备配置：创建新的或编辑现有的
 
在**新的设备配置**或**编辑设备配置**页上，您可以创建或修改用于管理业务 Phone edition 的 Skype 的设置的集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建设备配置**”或“**编辑设备配置**”页上执行以下任务：
  
- 添加新的设备配置。
    
- 修改现有设备配置的属性。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围**标识设备配置的范围 （全局或站点）。
    
- **名称**您可以添加或修改设备配置的名称。
    
- **SIP 安全**您可以配置传输和身份验证要求 Skype 业务 Phone Edition 设备。 您可以从以下选项中进行选择：
    
  - **低**允许任意类型的授权或传输。
    
  - **中等**NTLM 或 Kerberos 才能进行用户身份验证。
    
  - **高**NTLM 或 Kerberos 才能进行用户身份验证，并且需要 TLS 才能进行 SIP 连接。
    
- **日志记录级别**您可以启用 UC 设备上的日志记录。 有效值为： 关闭;低;中等;和高。 默认值已关闭。
    
- **语音服务质量 (QoS)** 您可以指定分配给产生 Skype 业务 Phone Edition 设备的语音流量的 DSCP 值。 默认值为 40。 但是，40 不是通常用于音频流量; 的值而是音频流量始终标记替换为 DSCP 代码 46。 为了保持一致性整个网络，您可能想要将此值更改为 46。
    
- **电话锁定**您可以指定 UC 电话将自己在后自动锁定停止活动一段。 您可以配置的设置如下：
    
  - **强制设备锁定**您可以强制设备锁定选中此复选框。
    
  - **最小 PIN 长度**您可以指定用于解锁电话的个人识别号 (PIN) 的最小长度。 PIN 长度的范围是 4 到 15 位数字。 默认长度为 6 个数字。
    
  - **电话锁定超时**您可以指定电话锁定之前的时间的最小长度，本身。 超时的范围是 0 到 60 分钟;默认值为 10 分钟。 Mm: ss 的格式输入该值。
    
## <a name="see-also"></a>另请参阅

[设备配置](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)