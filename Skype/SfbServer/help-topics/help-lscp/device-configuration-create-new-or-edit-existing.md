---
title: 设备配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 "新建设备配置" 或 "编辑设备配置" 页面上，您可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: 95ce62b5d3505e10049d61ead77ce79ee7f2f51b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822925"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>设备配置：创建新的或编辑现有的
 
在 "**新建设备配置**" 或 "**编辑设备配置**" 页面上，您可以创建或修改用于管理 Skype for business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建设备配置**”或“**编辑设备配置**”页上执行以下任务：
  
- 添加新的设备配置。
    
- 修改现有设备配置的属性。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围**标识设备配置的作用域（全局或网站）。
    
- **名称**你可以添加或修改设备配置的名称。
    
- **SIP 安全性**你可以配置 Skype for business Phone Edition 设备的传输和身份验证要求。 可以从以下选项中进行选择：
    
  - **低**允许任何类型的授权或传输。
    
  - **中等**需要使用 NTLM 或 Kerberos 进行用户身份验证。
    
  - **高**需要使用 NTLM 或 Kerberos 进行用户身份验证，并且需要使用 TLS 进行 SIP 连接。
    
- **日志记录级别**可以在 UC 设备上启用日志记录。 有效值为： Off;盘中期和高。 默认值为 Off。
    
- **语音服务质量（QoS）** 你可以从 Skype for business Phone Edition 设备指定分配给语音流量 emanating 的 DSCP 值。 默认值为40。 但是，40不是通常用于音频流量的值;相反，音频流量几乎始终标有 DSCP 代码46。 为了保持整个网络的一致性，你可能希望将此值更改为46。
    
- **电话锁定**你可以指定 UC 电话是否会在指定的非活动期后自动锁定其自身。 以下是你可以配置的设置：
    
  - **强制执行设备锁定**你可以通过选中此复选框来强制执行设备锁定。
    
  - **最小 PIN 长度**你可以指定用于解锁手机的个人识别码（PIN）的最小长度。 PIN 长度的范围是4到15个数字。 默认长度为6个数字。
    
  - **电话锁定超时**你可以指定电话锁定自身之前的最短时间长度。 超时的范围是0到60分钟;默认值为10分钟。 以 HH： MM： SS 格式输入值。
    
## <a name="see-also"></a>另请参阅

[设备配置](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
