---
title: 排除 Lync VDI 插件的故障
TOCTitle: 排除 Lync VDI 插件的故障
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204713(v=OCS.15)
ms:contentKeyID: 49312127
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 排除 Lync VDI 插件的故障

 

_**上一次修改主题：** 2012-10-10_

## 排除在瘦客户端上安装 Lync VDI 插件时出现的问题

如果在瘦客户端上安装 VDI 插件时出现问题，请检查以下几点：

  - 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。

  - 确保已关闭写保护。有关说明，请参阅设备制造商的文档。

## 排除配对问题

当 VDI 插件配对失败时，右下方的配对图标将显示为红色的“X”，如图所示：

![显示配对成功的 Lync VDI 图标](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "显示配对成功的 Lync VDI 图标")

以下是出现故障的可能原因以及可以采取的更正措施。

  - **用户在登录期间输入错误凭据。**
    
    用户应注销 Lync 并用正确凭据再次登录。配对对话框将重新出现，并显示配对是否成功。

  - **另一个远程桌面客户端的实例正在运行。**
    
    如果他们在 Windows 中使用远程桌面连接，用户应执行以下操作：
    
    1.  启动任务管理器：按“Alt+Ctrl+Delete”，然后单击“启动任务管理器”。
    
    2.  单击“进程”选项卡并在列表中查找名为“mstsc.exe”的所有进程。
    
    3.  突出显示每个“mstsc.exe”进程，然后单击“结束进程”。
    
    4.  启动新远程桌面会话并尝试再次连接。

  - **必要的文件未正确安装。**
    
    在本地计算机上安装插件后，C:\\Program Files\\Microsoft Office\\Office15（或适当的驱动器号）下应存在以下文件：
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    如果 VDI 配对出现任何问题，请检查以确保本地计算机上显示这些文件。

  - **Lync 客户端正在本地计算机上运行。**
    
    若要使用 Lync VDI 插件，Lync 客户端不得在本地计算机上运行，否则配对将失败。作为最佳实践，用户不应在本地计算机上安装 Lync 客户端。

