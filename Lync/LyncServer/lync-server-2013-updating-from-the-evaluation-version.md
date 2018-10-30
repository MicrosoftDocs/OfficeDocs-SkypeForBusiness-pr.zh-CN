---
title: 从 Lync Server 2013 评估版更新
TOCTitle: 从 Lync Server 2013 评估版更新
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521005(v=OCS.15)
ms:contentKeyID: 49313039
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从 Lync Server 2013 评估版更新

 

_**上一次修改主题：** 2012-06-20_

如果已安装 Microsoft Lync Server 2013 的评估版本，您最终需要将该安装更新为此软件的许可副本，因为评估版本将在安装后 180 天到期。但是，在安装许可版本之前，您无需完全卸载此评估版本。而是在获取有效许可密钥后，通过在充当 Lync Server 前端服务器、控制器或边缘服务器的每台计算机上执行以下过程来更新 Lync Server 2013 的评估版本。注意，您无需更新担当其他服务器角色（如监控服务器或存档服务器）的计算机。

## 更新 Microsoft Lync Server 2013 的评估版本

要将计算机从 Lync Server 2013 的评估版本更新到该软件的许可版本，请执行以下操作：

**更新 Microsoft Lync Server 2013 的评估版本**

1.  以本地管理员身份登录到计算机。

2.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

3.  在 Lync Server 命令行管理程序中，键入以下命令，然后按 Enter：
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    注意，您可能需要指定文件 server.msi 的完整路径。此文件位于 Lync Server 批量介质安装文件的 Setup 文件夹中。

4.  安装程序完成运行后，在命令提示符中键入以下内容，然后按 Enter 键：
    
        Enable-CsComputer

5.  在运行 Lync Server 评估副本的任何其他前端服务器、控制器或边缘服务器上重复此过程。此外，还应在使用 Lync Server 媒体安装文件部署的任何 Branch Office Server 上执行此过程。

如果不确定 Lync Server 的评估版本是否正在给定计算机上运行，可以通过从 Lync Server 命令行管理程序中运行以下命令进行验证：

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsServerVersion) cmdlet 将分析本地计算机并返回以下内容之一：

  - 已在计算机上安装了 Lync Server 批量许可证密钥，表示无需任何更新。

  - 已安装了 Lync Server 评估许可证密钥，表示必须更新计算机。

  - 计算机上无需批量许可证密钥。只有在前端服务器、控制器和边缘服务器上才需要从评估版本更新到许可版本。

