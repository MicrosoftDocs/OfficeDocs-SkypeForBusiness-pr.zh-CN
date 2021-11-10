---
title: 使用 PowerShell 执行 IM 和状态菜单上的任务
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
description: 摘要：Skype for Business Server"IM 和状态"菜单的 Cmdlet 映射。
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888730"
---
# <a name="im-and-presence"></a>IM 和状态

本文介绍如何使用 cmdlet 实现与旧版控制面板中的 IM 和 **状态** 菜单项类似的结果。

本文介绍了以下子菜单：

- [IM 和状态](#im-and-presence)
  - [文件筛选器](#file-filter)
  - [URL 筛选器](#url-filter)

## <a name="file-filter"></a>文件筛选器

**通过"** 文件筛选器"子菜单，管理员可以管理组织的文件传输筛选器配置。 这些配置用于阻止用户传输某些类型的文件 (例如，具有 .vbs 或 .ps1 文件扩展名的文件) 使用 Skype for Business Server 客户端。

让我们考虑用户可在 FILE **FILTER** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有文件筛选器

   ![列表文件筛选器](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***示例***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **方案 2：** 创建新的文件筛选器

   ![创建文件筛选器](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***示例***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **方案 3：** 获取所选文件筛选器的详细信息

   ![获取文件筛选器](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***示例***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选文件筛选器

   ![删除文件筛选器](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***示例***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新文件筛选器

   ![更新文件筛选器](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***示例***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>URL 筛选器

通过 **"IM** 和状态"下的"URL 筛选器"子菜单项，管理员可以配置 URL 筛选器，以便阻止具有特定前缀的超链接或不处于活动状态。  (也就是说，参与者不能只单击链接并转到 URI 引用的网站;他们必须手动将链接复制并粘贴到浏览器中。) 

让我们考虑用户可在 **URL FILTER** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有 Web URL 筛选器

   ![列表 URL 筛选器](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***示例***

```powershell
 Get-CsImFilterConfiguration
```

---

> **方案 2：** 创建新的 URL 筛选器

   ![新 URL 筛选器](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***示例***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **方案 3：** 获取所选 URL 筛选器的详细信息

   ![获取 URL 筛选器](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***示例***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的 URL 筛选器

   ![删除 URL 筛选器](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***示例***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新 URL 筛选器

   ![更新 URL 筛选器](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***示例***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
