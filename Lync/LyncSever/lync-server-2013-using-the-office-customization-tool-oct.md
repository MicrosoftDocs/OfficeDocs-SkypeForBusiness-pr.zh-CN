---
title: 使用 Office 自定义工具 (OCT)
TOCTitle: 使用 Office 自定义工具 (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204748(v=OCS.15)
ms:contentKeyID: 49312287
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Office 自定义工具 (OCT)

 

_**上一次修改主题：** 2016-12-08_

Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。可将该文件放在网络安装点上的 Updates 文件夹中。在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。Updates 文件夹只能用于在初始安装 Office 2013 期间部署软件更新。

OCT 是安装程序的一部分且包括在产品的批量许可版本中。通过在命令行中从包含 Office 2013 源文件的网络安装点的根目录键入 `setup.exe /admin` 可运行 OCT。例如，可使用以下命令：

`\\server\share\Office15\setup.exe /admin`

管理员可使用 OCT 创建安装程序自定义 .msp 文件。和在 Microsoft Office 2010 OCT 中一样，管理员可以自定义以下区域：

  - **安装** 用于指定客户端上的默认安装位置和默认自定义名称，其他网络安装源，产品密钥，最终用户许可协议，显示级别，要删除的早期版本的 Office，要在安装期间运行的自定义程序，安全设置以及安装程序属性。

  - **功能** 用于配置用户设置和自定义 Office 功能的安装方式。管理员可使用 OCT 指定用户的 Office 应用程序设置的初始默认值。用户可以在安装后修改其中大多数设置。

  - **其他内容** 用于添加或删除文件，添加或删除注册表项，以及配置快捷方式。

  - **Outlook** 用于自定义用户的默认 Outlook 配置文件，指定 Exchange 设置，添加帐户，删除帐户和导出设置，并指定发送\\接收组。

有关 OCT 的信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x804)。

