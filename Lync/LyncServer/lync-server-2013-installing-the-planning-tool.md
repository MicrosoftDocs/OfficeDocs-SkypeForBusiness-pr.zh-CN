---
title: Lync Server 2013：安装规划工具
TOCTitle: 安装规划工具
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615046(v=OCS.15)
ms:contentKeyID: 52061165
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中安装规划工具

 

_**上一次修改主题：** 2013-11-07_

使用 Microsoft Lync Server 2013 规划工具开始设计和规划 Lync Server 2013 基础结构之前，必须首先安装 规划工具。无需将 规划工具部署到计划安装 Lync Server 2013 的域或基础结构中的工作站或服务器。规划工具随附的自述文件详细介绍了有关安装和使用该工具的重要信息。为明确起见，此处复述了自述文件中的某些信息。

> [!IMPORTANT]
> 规划工具要求执行安装的用户具有要安装该工具的计算机上的管理员权限。


支持安装和操作 规划工具的操作系统有：

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7 32 位版本

  - Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本

  - Windows Server 2008 R2，使用 WOW

此外， 规划工具还需要 Microsoft .NET Framework 4.5。

满足安装前的要求后，即可安装 规划工具。

## 安装规划工具

1.  以 Administrators 组成员的身份登录本地计算机。

2.  使用 Windows 资源管理器或命令窗口，找到下载 规划工具安装文件的目录。

3.  找到 LyncPlanningTool.msi，在 Windows 资源管理器中双击该文件。在命令窗口中，键入文件的名称，然后按“Enter”运行该文件。

4.  在“Microsoft Lync Server 2013 规划工具安装向导”的“欢迎”页上，单击“下一步”。

5.  查看“最终用户许可协议”，如果选择接受许可协议中的使用条款，则选择“我接受许可协议中的条款”，然后单击“下一步”。

6.  选择安装规划工具文件的位置。默认位置是 C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool。如果要更改安装位置，请单击“更改”。在“更改目标文件夹”上，浏览或键入要安装这些文件的位置，单击“确定”，然后单击“下一步”。

7.  安装程序现已准备好安装规划工具。单击“安装”开始安装过程。

8.  将开始安装，并将显示进度。成功完成安装后，单击“完成”。

9.  规划工具即可供使用。

## 另请参阅

#### 概念

[在 Lync Server 2013 中安装可选软件](lync-server-2013-installing-optional-software.md)

