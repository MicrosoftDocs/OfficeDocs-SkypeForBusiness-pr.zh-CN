---
title: 更新 Outlook 启用的列表
TOCTitle: 更新 Outlook 启用的列表
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215438(v=OCS.15)
ms:contentKeyID: 49312987
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 更新 Outlook 启用的列表

 

_**上一次修改主题：** 2013-01-07_

通过创建将 Microsoft Lync 2013 联机会议外接程序包含在用于 Outlook 的外接程序管理列表中的策略，您可以确保该程序始终对用户保持启用状态。外接程序管理列表策略包含在组策略管理控制台的 Office 管理模板文件中。它在 HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList 下创建注册表项。您可以将 ucaddin.dll 的值添加到此项中，并配置 ucaddin.dll 值，以便它始终处于启用状态并且用户无法手动禁用它

## 将 ucaddin.dll 添加到 Outlook 外接程序列表中

  - 向位于 HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList 下的 AddinList 注册表项中添加以下值：
    
      - 注册表类型 = REG\_SZ
    
      - 名称 = ucaddin.dll
    
      - 值 = 1（指定外接程序始终保持启用状态，且无法由最终用户管理）

