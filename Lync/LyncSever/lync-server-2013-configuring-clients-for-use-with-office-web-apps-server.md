---
title: 在 Lync Server 2013 中将客户端配置为与 Office Web Apps Server 结合使用
TOCTitle: 将客户端配置为与 Office Web Apps Server 结合使用
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205339(v=OCS.15)
ms:contentKeyID: 49314561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将客户端配置为与 Office Web Apps Server 结合使用

 

_**上一次修改主题：** 2013-02-25_

如果想让用户体验 Office Web App Server 的完整功能，则应将这些用户升级到 Microsoft Lync 2013；仅 Lync 2013 的用户能够执行这样的操作，因为在 PowerPoint 幻灯片中滚动独立于实际的 PowerPoint 演示文稿（即：这些用户可在演示中随时查看任何幻灯片，而不会干扰任何实际的演示）。不使用 Lync 2013 的用户仍能够加入联机会议和查看 PowerPoint 演示文稿；但是，他们无法单独滚动这些幻灯片，也无法看到幻灯片转换或查看嵌入的视频。

请注意，这些功能始终可用于 Lync 2013 的用户；即使 PowerPoint 演示者正在运行 Microsoft Lync 2010 也是如此。如果 PowerPoint 演示文稿由运行 Lync 2010 的用户托管，则 Lync Server 2013 将与 Office Web Apps Server 协作以确保 Lync 2013 用户查看该演示的 Office Web Apps Server 版本。Office Web Apps Server 不为运行 Lync 2013 之外的客户端的用户提供 PowerPoint 服务。但是，这些用户将连接到会议服务器服务并查看 PowerPoint 演示文稿，这与他们在 Microsoft Lync Server 2010 中执行的操作相同。这还意味着，这些用户仅有权访问 Lync Server 2010 提供的更加有限的功能。

尽管 Office Web Apps Server 无需任何客户端配置（而不是将用户升级到 Lync 2013），但建议将会议参与者升级到 Internet Explorer 9。尽管可使用 Internet Explorer 8 访问会议，但对使用 Web 浏览器有一些限制。例如，Internet Explorer 8 的用户无法将 PowerPoint 阶段的大小重新调整为自定义大小；而是将其限制为使用三个预定义阶段大小之一。Internet Explorer 8 用户将很有可能无法播放媒体文件。

