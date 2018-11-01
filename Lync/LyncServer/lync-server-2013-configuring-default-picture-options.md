---
title: 配置默认图片选项
TOCTitle: 配置默认图片选项
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn205074(v=OCS.15)
ms:contentKeyID: 53901757
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置默认图片选项

 

_**上一次修改主题：** 2013-03-22_

默认情况下，用户的图片将自动显示。如果用户希望隐藏其图片，则他们可以在 Lync 客户端中选择“隐藏我的图片”选项。但是，此设置将被其他一些 Office 应用程序忽略。

如果即使用户关闭图片显示时也可能显示图片是要考虑的问题，您可以为站点或服务全局更改 Lync 图片显示设置，以便用户的图片默认情况下不显示。使用以下 Lync Server 命令行管理程序 cmdlet，以便用户的图片不会显示，除非他们在客户端中显式选择“显示我的图片”：

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序 文档中的 [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)。

