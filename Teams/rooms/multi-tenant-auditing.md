---
title: Microsoft Teams 会议室 门户
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 审核 TRM 的日志记录。
f1keywords: ''
ms.openlocfilehash: e5e5cd25385f6e8a71484c57aa9c44da5d4c9cd8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331212"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>审核托管服务Teams 会议室日志记录

使用 Teams 会议室 托管 (TRM) 服务中的审核功能可以搜索审核记录，查找用户和管理员在门户中执行的活动。 此功能默认已启用。 只有托管服务管理员有权导出并查看日志。

> [!NOTE]
> TRM 服务中执行的操作不会记录到Microsoft 365 Office 365审核 

## <a name="exporting-logs"></a>导出日志

导出 审核日志 搜索的所有结果时，来自统一 审核日志 的原始数据将复制到下载到本地计算机的逗号分隔值 (CSV) 文件中。 

**下载日志** 

1. 转到"**常规设置 >">审核日志"。**
1. 若要定义感兴趣的日志的日期范围，请输入 **"开始日期"和** " **结束日期"。**

   > [!NOTE]
   > 日志最多只能使用 180 天。

1. 选择" **下载日志"。**

   ![审核日志日期范围](../media/multi-tenant-auditing.png)

   窗口底部显示的消息会提示打开或保存 CSV 文件。 

1. 选择 **"**  >  **另存为**"，将 CSV 文件保存到本地计算机。 

1. 搜索所有活动时，或在广泛的日期范围内下载许多搜索结果需要一段时间。 CSV 文件下载完成后，窗口底部会显示一条消息。

## <a name="detailed-properties-in-the-audit-log"></a>属性中的详细审核日志

下表描述了 CSV 中包含的属性。

|属性|说明|
| - | - |
|activity.category|<p>执行的操作所针对的对象的类别。 可能的值：</p><p>**用户、分配、合作伙伴邀请、角色**</p>|
|activity.objectName|已修改的对象的名称。|
|activity.operation|执行的操作类型。 可能的值为 **：Create、Update、Delete** |
|activity.resultStatus|<p>指示在 **activity.operation** (中指定的操作) 是否成功。</p><p>值为"成功 **"** 或"**失败"。**</p>|
|activity.tenantId|执行该操作的租户的 GUID|
|creationTime|用户执行活动时，协调世界时 (UTC) 采用 ISO 格式。|
|user.userId|执行导致记录记录的操作的用户。|
|user.userTenantId|执行该操作的用户的租户 GUID|


