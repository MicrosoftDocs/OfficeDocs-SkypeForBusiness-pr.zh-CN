---
title: 设备配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 在"新建设备配置"或"编辑设备配置"页上，可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807302"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>设备配置：创建新的或编辑现有的
 
在 **"新建设备配置** " **或** "编辑设备配置"页上，可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“新建设备配置”或“编辑设备配置”页上执行以下任务：
  
- 添加新的设备配置。
    
- 修改现有设备配置的属性。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围** 标识设备 (全局) 站点范围。
    
- **名称** 你可以添加或修改设备配置的名称。
    
- **SIP 安全性** 你可以为 Skype for Business Phone Edition 设备配置传输和身份验证要求。 可以从以下选项中进行选择：
    
  - **低** 允许任何类型的授权或传输。
    
  - **中** 用户身份验证需要 NTLM 或 Kerberos。
    
  - **高** 用户身份验证需要 NTLM 或 Kerberos，SIP 连接需要 TLS。
    
- **日志记录级别** 可以在 UC 设备上启用日志记录。 有效值为：Off;低;中等;高。 默认值为 Off。
    
- **QoS (语音服务质量)** 你可以指定分配给来自 Skype for Business Phone Edition 设备的语音流量的 DSCP 值。 默认值为 40。 但是，40 并不是通常用于音频流量的值；音频流量几乎始终用 DSCP 代码 46 进行标记。 为了在整个网络中保持一致性，您可能需要将此值更改为 46。
    
- **电话锁定** 可以指定 UC 电话是否将在指定的非活动时间后自动锁定自身。 以下是可以配置的设置：
    
  - **强制设备锁定** 可以通过选中此复选框来强制设备锁定。
    
  - **最小 PIN 长度** 你可以指定用于解锁电话的个人标识号 (PIN) 密码。 PIN 长度的范围为 4 到 15 位数字。 默认长度为六位数。
    
  - **电话锁定时间** 你可以指定电话自行锁定之前的最小时间长度。 该时间的范围是 0 到 60 分钟;默认值为 10 分钟。 以 HH：MM：SS 格式输入值。
    
## <a name="see-also"></a>另请参阅

[设备配置](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
