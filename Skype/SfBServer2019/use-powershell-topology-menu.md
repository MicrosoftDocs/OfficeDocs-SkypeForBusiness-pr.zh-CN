---
title: 对"拓扑"菜单上的任务使用 PowerShell
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
description: 摘要：Skype for Business Server控制面板映射到拓扑菜单的 Cmdlet。
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626034"
---
# <a name="topology"></a>拓扑

本文介绍如何使用 cmdlet 实现与旧版控制面板中的"拓扑"菜单项类似的结果。

本文介绍了以下子菜单：

- [拓扑](#topology)
  - [状态](#status)
  - [服务器应用程序](#server-application)
  - [简单 URL](#simple-url)
  - [受信任应用程序](#trusted-application)

## <a name="status"></a>状态

**"** 状态"子菜单使管理员能够管理拓扑中的计算机。

让我们考虑用户可在 **STATUS** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有计算机及其状态

   ![列出计算机和状态](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***示例***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***示例***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***示例***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>服务器应用程序

服务器应用程序是指在应用程序下运行Skype for Business Server。 **"服务器** 应用程序"子菜单为管理员提供了一种方法，用于返回有关 (或) 运行的应用程序的任何项目或Skype for Business Server。

让我们考虑用户可在 **SERVER APPLICATION** 上执行的各种任务，Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有服务器应用程序

   ![列出服务器应用程序](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***示例***

```powershell
 Get-CsServerApplication
```

---

> **方案 2：** 启用/禁用或选择关键/取消选择关键服务器应用程序

   ![编辑服务器应用程序](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***示例***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>简单 URL

简单 URL 使用户可以更轻松地加入会议，还便于管理员登录到 Skype for Business Server 控制面板。简单 **URL** 子菜单可帮助管理员查看它们。

让我们考虑用户可在 **简单 URL** 上执行的各种任务，Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有简单 URL 配置

   ![列出简单 URL](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***示例***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>受信任应用程序

受信任应用程序是由第三方开发的应用程序，该应用程序被赋予受信任的状态以作为 Skype for Business Server 的一部分运行，但它不是产品的内置部分。"**受信任的应用程序**"子菜单可帮助管理员查看它们。

让我们考虑用户可在受信任应用程序上执行的各种任务，Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有受信任应用程序

   ![列出受信任应用程序](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***示例***

```powershell
 Get-CsTrustedApplication
```

---
