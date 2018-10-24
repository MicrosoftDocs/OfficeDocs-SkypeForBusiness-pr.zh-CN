---
title: 启用/禁用会议记录
TOCTitle: 启用/禁用会议记录
ms:assetid: f6c5afab-081c-495c-97f7-135dcc2f6085
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362857(v=OCS.15)
ms:contentKeyID: 56271221
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用/禁用会议记录

 

_**上一次修改主题：** 2015-06-22_

如果不希望用户拥有录制联机会议的能力，请使用 [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md) cmdlet 并将 AllowConferenceRecording 参数的值设置为 False ($False)：

    Set-CsMeetingConfiguration -AllowConferenceRecording $False

要恢复录制联机会议的能力，请将 AllowConferenceRecording 参数的值设置为 True ($True)：

    Set-CsMeetingConfiguration -AllowConferenceRecording $True

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

