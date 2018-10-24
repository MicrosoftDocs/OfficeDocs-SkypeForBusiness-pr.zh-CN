---
title: 删除以前分配给用户的音频会议提供商
TOCTitle: 删除以前分配给用户的音频会议提供商
ms:assetid: 85d59e6c-d646-4908-9767-adb48763f6de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362808(v=OCS.15)
ms:contentKeyID: 56271174
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除以前分配给用户的音频会议提供商

 

_**上一次修改主题：** 2015-06-22_

要删除分配给用户的所有音频会议提供商，请不带任何参数（Identity 参数以外的其他参数，该参数指明相关用户）运行 [Remove-CsUserAcp](remove-csuseracp.md) cmdlet：

    Remove-CsUserAcp -Identity "Ken Myer"

如果某用户被分配了多个音频会议提供商，您可以通过包括 Name 参数而后跟要删除的提供商的名称来删除单个提供商：

    Remove-CsUserAcp -Identity "Ken Myer" -Name "Contoso ACP"

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

