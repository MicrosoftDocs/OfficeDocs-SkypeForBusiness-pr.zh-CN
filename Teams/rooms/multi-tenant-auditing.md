---
title: MTR Pro 门户中的审核日志记录
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: MTR Pro 门户的审核日志记录。
f1keywords: ''
ms.openlocfilehash: 0436618e257128deb38d890cb92813ae13921e7d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243913"
---
# <a name="audit-logging-in-the-mtr-pro-portal"></a>MTR Pro 门户中的审核日志记录

通过 MTR Pro 门户的审核日志，可以搜索用户和管理员执行的活动审核记录。 默认情况下启用此功能。 只有托管服务管理员有权导出，然后查看日志。

> [!NOTE]
> 在 MTR Pro 门户中执行的操作不会记录在 Microsoft 365 或Office 365审核中 

## <a name="exporting-logs"></a>导出日志

导出审核日志搜索的所有结果时，将统一审核日志中的原始数据复制到一个逗号分隔值 (CSV) 文件，该文件将下载到本地计算机。 

**下载日志** 

1. 转到 **“设置”>常规>审核日志**。
1. 若要定义感兴趣的日志的日期范围，请输入 **开始日期** 和 **结束日期。**

   > [!NOTE]
   > 日志最多只能使用 180 天。

1. 选择 **“下载日志”。**

   ![审核日志日期范围](../media/multi-tenant-auditing.png)

   窗口底部显示的消息提示你打开或保存 CSV 文件。 

1. 选择 **“另存** > **为**”，并将 CSV 文件保存到本地计算机。 

1. 在搜索所有活动时或在广泛的日期范围内下载许多搜索结果需要一段时间。 下载完 CSV 文件后，会显示窗口底部的消息。

## <a name="detailed-properties-in-the-audit-log"></a>审核日志中的详细属性

下表描述了 CSV 中包含的属性。

|属性|说明|
| - | - |
|activity.category|<p>所执行操作的对象的类别。 可能的值：</p><p>**用户、分配、PartnerInvitation、角色**</p>|
|activity.objectName|已修改的对象的名称。|
|activity.operation|执行的操作类型。 可能的值为： **创建、更新、删除** |
|activity.resultStatus|<p>指示 **activity.operation** 属性中指定的操作 () 是否成功。</p><p>值为 **“成功** ”或 **“失败**”。</p>|
|activity.tenantId|执行操作的租户的 GUID|
|creationTime|协调世界时 (UTC 的日期和时间在用户执行活动时) ISO 格式。|
|user.userId|执行导致记录记录的操作的用户。|
|user.userTenantId|执行操作的用户的租户 GUID|


