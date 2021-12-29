---
title: 使用 PowerShell 执行"监控和存档"菜单上的任务
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 摘要：Skype for Business Server"菜单将"控制面板"映射到"监控和存档"菜单的 Cmdlet 映射。
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626035"
---
# <a name="monitoring-and-archiving"></a>监控和存档

本文介绍如何使用 cmdlet 实现与旧版控制面板中的"监控和存档"菜单项类似的结果。

本文介绍了以下子菜单：

- [监控和存档](#monitoring-and-archiving)
  - [呼叫详细信息记录](#call-detail-recording)
  - [用户体验质量数据](#quality-of-experience-data)
  - [存档策略](#archiving-policy)
  - [存档配置](#archiving-configuration)

## <a name="call-detail-recording"></a>呼叫详细信息记录

**"呼叫详细信息** 记录"子菜单使管理员能够管理 CDR 设置 (呼叫) 记录。CDR 使您能够跟踪对等即时消息会话、Internet 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。

让我们考虑用户在 CALL **DETAIL RECORDING** 上可以执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有 CDR 配置

   ![列出 Cdr 配置](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***示例***

```powershell
 Get-CsCdrConfiguration
```

---

> **方案 2：** 创建新的 CDR 配置

   ![创建 Cdr 配置](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***示例***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **方案 3：** 获取所选 CDR 配置的详细信息

   ![获取 Cdr 配置](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***示例***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的 CDR 配置

   ![删除 Cdr 配置](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***示例***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新 CDR 配置

   ![更新 Cdr 配置](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***示例***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>用户体验质量数据

利用 **"用户体验质量数据** "子菜单，管理员可以管理 QoE (用户体验) 设置。 在整个组织中;这包括管理组扩展、证书设置和允许的身份验证方法。 因为管理员可以在全局、站点和服务范围配置不同的设置 (但只能为唯一的 Web 服务) 配置这些设置，因此，管理员可以为不同用户和不同位置自定义 Web 服务功能。

让我们考虑用户可在 **WEB** 服务上执行的各种任务，以及这些任务Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有 QoE 配置

   ![列出 QoE 配置](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***示例***

```powershell
 Get-CsQoEConfiguration
```

---

> **方案 2：** 创建新的 QoE 配置

   ![新的 QoE 配置](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***示例***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **方案 3：** 获取所选 QoE 配置的详细信息

   ![获取 QoE 配置](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***示例***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的 QoE 配置

   ![删除 QoE 配置](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***示例***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新 QoE 配置

   ![更新 QoE 配置](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***示例***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>存档策略

管理员可以使用存档 **策略** 管理即时消息 (IM) 会话存档策略。存档策略使您能够存档在内部用户和/或内部用户与外部用户之间发生的所有 IM 和 Web 会议会话

让我们考虑用户可对存档策略执行的各种任务，以及这些任务Skype for Business cmdlet 映射到的 cmdlet。

---

> **方案 1：** 列出所有存档策略

   ![列出存档策略](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***示例***

```powershell
 Get-CsArchivingPolicy
```

---

> **方案 2：** 创建新的存档策略

   ![创建存档策略](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***示例***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **方案 3：** 获取所选存档策略的详细信息

   ![获取存档策略](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***示例***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **方案 4：** 删除所选的存档策略

   ![删除存档策略](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***示例***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **方案 5：** 更新存档策略

   ![更新存档策略](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***示例***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>存档配置

管理员可以使用 **存档配置** 来配置 (或) 即时消息 (IM) 会话是否存档在组织中。

让我们考虑用户可在存档配置上执行的各种任务，以及这些任务Skype for Business cmdlet 映射到的 cmdlet。

---

> **方案 1：** 列出所有存档配置

   ![列出存档配置](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***示例***

```powershell
 Get-CsArchivingConfiguration
```

---

> **方案 2：** 创建新的存档配置

   ![创建存档配置](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***示例***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **方案 3：** 获取所选存档配置的详细信息

   ![获取存档配置](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***示例***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的存档配置

   ![删除存档配置](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***示例***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新存档配置

   ![更新存档配置](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***示例***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
