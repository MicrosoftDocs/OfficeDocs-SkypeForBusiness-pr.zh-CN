---
title: 准备和安装最佳做法分析器
TOCTitle: 准备和安装最佳做法分析器
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg591347(v=OCS.15)
ms:contentKeyID: 49312878
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 准备和安装最佳做法分析器

 

_**上一次修改主题：** 2016-12-08_

您必须以 Administrators 组的成员身份登录以执行本主题中介绍的任务。

## 最佳做法分析器安装的系统要求

若要运行 Lync Server 2013 最佳做法分析器以扫描您的环境，计算机必须运行下列操作系统之一的 64 位版本：

  - Windows Server 2008 R2 Service Pack 1 (SP1) Standard 操作系统

  - Windows Server 2008 R2 SP1 Enterprise 操作系统

  - Windows Server 2008 R2 SP1 Datacenter 操作系统

  - Windows Server 2012 Datacenter 操作系统

  - Windows Server 2012 Standard 操作系统

  - Windows Server 2012 Enterprise 操作系统

  - Windows Server 2012 R2 Datacenter 操作系统

  - Windows Server 2012 R2 Standard 操作系统

  - Windows Server 2012 R2 Enterprise 操作系统

  - Windows 8 操作系统

  - Windows 7 操作系统

计算机还必须运行：

  - Microsoft .NET Framework 4.5。对于 Lync Server 2013，您必须先在服务器上手动安装 64 位版本的 Microsoft .NET Framework 4.5，然后才能安装 Lync Server 2013。

  - Lync Server 2013 核心组件。

  - WMI 向后兼容包。有关详细信息，请参阅迁移文档中的[安装 WMI 向后兼容包](install-wmi-backward-compatibility-package.md)。

  - Windows PowerShell 3.0。有关详细信息，请参阅部署文档中的[为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

虽然您可以在具有未运行 Lync Server 2013、核心组件或 WMI 向后兼容包的受支持的操作系统的计算机上安装最佳做法分析器，但您只能在这些计算机上使用最佳做法分析器来查看报告而非运行扫描。

## 选择计算机以进行安装

建议您在专用于管理 Lync Server 2013 的计算机上安装 Lync Server 2013 最佳做法分析器。您可以在运行 Lync Server 2013 的服务器上或运行 Lync Server 2013 管理工具的管理计算机上安装此工具。如果您在运行 Lync Server 的服务器上安装此工具，建议您使用此工具仅扫描该服务器。

## 安装最佳做法分析器

您可以下载 Lync Server 2013 最佳做法分析器，网址为 [http://go.microsoft.com/fwlink/?linkid=266539\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=266539%26clcid=0x804)。

若要安装最佳做法分析器，请在要安装此工具的计算机上启动 Microsoft Installer 文件 RtcBPA.msi，然后按照屏幕上显示的说明进行操作。将程序文件安装到的默认位置是 *\<系统驱动器\>*\\Program Files\\Lync Server 2013\\BPA。

