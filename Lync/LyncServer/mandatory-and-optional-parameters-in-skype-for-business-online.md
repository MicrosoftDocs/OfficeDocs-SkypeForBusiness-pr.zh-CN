---
title: 强制参数和可选参数
TOCTitle: 强制参数和可选参数
ms:assetid: e766362f-e2e9-4598-a595-fdf5eedd9ad6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362851(v=OCS.15)
ms:contentKeyID: 56271216
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 强制参数和可选参数

 

_**上一次修改主题：** 2015-06-22_

Windows PowerShell 参数分为两类：强制参数和可选参数。*强制参数*是指当您运行命令时必须包括的参数。例如，[Remove-CsUserAcp](remove-csuseracp.md) cmdlet 用于取消分配之前分配给用户的音频会议提供商。当您运行 **the Remove-CsUserAcp** cmdlet 时，必须包括 Identity 参数。该参数告诉 cmdlet 哪个用户需要删除其音频会议提供商。正如您可能期望的那样，不带任何参数运行此命令没有任何意义：

    Remove-CsUserAcp

在类似情形中，该 cmdlet 不知道哪个用户需要删除其音频会议提供商。您必须指定用户的标识：

    Remove-CsUserAcp -Identity "Ken Myer"

通常，如果您在试图运行命令时忽略强制参数，Windows PowerShell 将提示您。例如，您可能会键入以下内容，然后按 Enter：

    Remove-CsUserAcp

如果这样做，Windows PowerShell 不会运行此不完整的命令。相反，它将提示您缺少强制参数：

    命令管道位置 1 处的 cmdlet Remove-CsUserAcp
    为以下参数提供值:
    Identity:

如果您输入有效的 Identity 参数并按 Enter，Windows PowerShell 将运行 **Remove-CsUserAcp** cmdlet 并删除会议音频提供商。如果您改变主意，决定不运行命令，请按 Ctrl-C 终止命令。

这并不是一个万无一失的系统，Windows PowerShell 不始终能够提示您必需的一组参数。例如，一些 cmdlet 经过构造，以便参数 A 或参数 B（而不是两者都）是强制性的。Windows PowerShell 可能会提示您同时使用参数 A 和 B；然而，您的命令将会失败，因为不能在相同命令中同时使用参数 A 和参数 B。由于类似情形，最好是在运行命令时包括所有必需参数，而不是依赖 Windows PowerShell 提示您所需信息。

也请注意，设置参数值的格式可能有时是一个不够直观方便的过程。例如，当使用包含空格的参数值时，您需要使用双引号将该值引起来：

    -Identity "Ken Myer"

但是，只有当您作为要执行的命令的一部分键入参数和参数值时，才应使用引号。如果您试图运行 **Remove-CsUserAcp** cmdlet，而无意中未使用 Identity 参数，则 Windows PowerShell 将提示您提供用户标识：

    命令管道位置 1 处的 cmdlet Remove-CsUserAcp
    为以下参数提供值:
    Identity:

然后您键入 Ken Myer，并将 Identity 参数用双引号引起来：

    命令管道位置 1 处的 cmdlet Remove-CsUserAcp
    为以下参数提供值:
    Identity:"Ken Myer"

如果这样做，命令将会失败，并显示以下错误消息：

    Remove-CsUserAcp : 找不到标识"{0}"的管理对象。

在这种情况下，搜索标识为“Ken Myer”的用户，双引号也成为 Identity 参数的一部分。如果系统提示您输入参数值，请不要包括双引号：

    命令管道位置 1 处的 cmdlet Remove-CsUserAcp
    为以下参数提供值:
    Identity:Ken Myer

相比之下，*可选参数*顾名思义：参数不需要输入，cmdlet 即可运行。例如，Remove-CsUserAcp 有可选参数 Name。如果在命令中包括 Name 参数，则只将删除指定的音频会议提供商。此命令删除名为 Fabrikam ACP 的音频会议提供商，但不删除分配给 Ken Myer 的任何其他音频会议提供商：

    Remove-CsUserAcp -Identity "Ken Myer" -Name "Fabrikam ACP"

如果不使用此可选参数，命令仍将运行。然而在这种情况下，Remove-CsUserAcp 将删除分配给 Ken Myer 的所有音频会议提供商：

    Remove-CsUserAcp -Identity "Ken Myer"

## 另请参阅

#### 概念

[Windows PowerShell 和 Lync Online 简介](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

