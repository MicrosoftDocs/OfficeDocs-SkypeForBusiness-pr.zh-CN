---
title: 返回用户的筛选列表
TOCTitle: 返回用户的筛选列表
ms:assetid: f2c4d13b-8601-4192-8b94-e9a57969da11
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362858(v=OCS.15)
ms:contentKeyID: 56271218
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回用户的筛选列表

 

_**上一次修改主题：** 2015-06-22_

通过使用 [Get-CsOnlineUser](get-csonlineuser.md) cmdlet 和 LdapFilter 或 Filter 参数，您可以轻松地返回有关一组目标用户的信息。例如，此命令将返回在财务部门工作的所有用户：

    Get-CsOnlineUser -LdapFilter "department=Finance"

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

