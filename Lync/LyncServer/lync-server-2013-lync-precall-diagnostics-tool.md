---
title: Lync 呼叫前诊断工具
TOCTitle: Lync 呼叫前诊断工具
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn451255(v=OCS.15)
ms:contentKeyID: 59602813
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 呼叫前诊断工具

 

_**上一次修改主题：** 2016-12-08_

Lync 呼叫前诊断工具 (PCD) 是一种基于客户端的应用程序，允许您查看当前网络状态可能对即将到来的企业语音呼叫的音频质量所造成的影响。

PCD 在最后一个网络跃点很弱的情况（例如，公共 WiFi 网络上的便携式计算机或家用计算机）下非常有用。PCD 会创建一个很小的数据流来遍历此最终网络线路。之后该工具将分析该数据流，评估这条线路的抖动和数据丢失可能对呼叫质量造成的影响，并提供相应的报告。您可以在客户端上持续运行 PCD，即使正在进行呼叫。运行 PCD 创建的数据流不会对带宽产生显著的影响。

**PCD 的最新版本 1.1 版包括以下增强功能：**

  - 支持较长密码，现在最多可包含 127 个字符

  - 身份验证登录问题的附加诊断

  - 更好地支持 Lync 混合部署

  - 凭据选取器更新

  - 稳定性改进

感谢您的任何反馈。请在 <pcdfb@microsoft.com> 将所有支持问题发送到 [PCD Feedback](mailto:pcdfb@microsoft.com) 别名。

本主题包括以下部分：

  - Lync PCD 版本

  - Lync PCD 系统要求

  - Lync PCD 功能

  - 运行 Lync PCD

  - 卸载 Lync PCD

## Lync PCD 版本

本主题介绍该工具的以下版本，这些版本可免费下载：

  - Windows 桌面应用 ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

  - Windows 8 现代应用 ([http://go.microsoft.com/fwlink/?LinkId=322110](http://go.microsoft.com/fwlink/p/?linkid=322110))

> [!NOTE]  
> Office 365 Lync 用户可以使用 PCD 的两个版本。



如果想要使用 PCD 的以前版本，请参阅以下内容：

  - 32 位版本的 PCD 可从 Microsoft 下载中心免费下载，网址为 [Office Communications Server 2007 R2，PreCallDiagnostic 资源工具包工具（32 位）](http://go.microsoft.com/fwlink/p/?linkid=164769)。

  - 64 位版本的 PCD 随 Office Communications Server 2007 R2 资源工具包工具提供，该工具包可从 Microsoft 下载中心免费下载，网址为 [Office Communications Server 2007 R2 资源工具包工具](http://go.microsoft.com/fwlink/p/?linkid=145159)。

## Lync PCD 系统要求

> [!NOTE]  
> PCD 要求在 Lync Server 部署中安装统一通信 Web API (UCWA) 并配置为支持移动客户端。UCWA 随 Lync Server 一起安装。



## Windows 桌面应用要求

  - Windows 7 或 Windows 8 操作系统的任何版本

  - Microsoft .NET Framework 4.5，网址为 [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Windows 8 现代应用要求

  - Windows 8 操作系统的任何版本

  - Microsoft .NET Framework 4.5，网址为 [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Lync PCD 功能

Lync PCD 包括以下功能：

  - 默认情况下按需运行（2 分钟）

  - 在始终打开模式下运行（在贴靠视图中最多 24 小时）

  - 测试运行的历史视图

  - 诊断登录失败（仅适用于 Windows 8 的 Lync PCD）

![Lync PCD 功能登录进度屏幕截图](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登录进度屏幕截图")

  - 网络指标的图形视图 – 全屏和贴靠视图中的网络 MOS、数据包丢失和到达间隔抖动。

**全屏视图**

![PreCall Diagnostic 工具测试结果图](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic 工具测试结果图")

**贴靠视图**

![PreCall Diagnostic 工具利用率测试结果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic 工具利用率测试结果")

## 运行 Lync PCD

## 运行 Windows 桌面应用

1.  要在 Windows 7 系统上启动 PCD，请从“开始”菜单中选择“呼叫前诊断”。
    
    要在 Windows 8 系统上启动 PCD，请在“开始”屏幕上选择图标，或者搜索“呼叫前诊断”。
    
    ![PreCall Diagnostic 工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic 工具图标")

2.  当该工具启动时，请选择提供凭据的首选方法，在“呼叫前诊断工具选项”对话框中选择网络操作模式，然后选择“确定”：

3.  选择“开始测试”按钮以开始运行诊断。
    
    如果选择“使用网络凭据”选项，测试将立即开始。
    
    如果选择“让我输入我的凭据”选项，则“Windows 安全性”对话框将会打开。在您输入凭据后，测试将会开始。


## 运行 Windows 8 现代应用

1.  要启动 PCD，请在“开始”屏幕上选择图标，或者搜索“呼叫前诊断”。
    
    ![PreCall Diagnostic 工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic 工具图标")

2.  当该工具启动时，请提供您的 Lync 凭据，然后选择“确定”。
    
    ![Lync PreCall Diagnostics 工具登录](images/Dn451255.88039914-4c68-48f6-a9fa-58cb4e3f3488(OCS.15).jpg "Lync PreCall Diagnostics 工具登录")

3.  选择“开始测试”按钮以开始运行诊断。


## 卸载 Lync PCD

要删除 Lync PCD，请按照适合您的操作系统的过程执行操作：

  - 在 Windows 7 系统上，打开“控制面板”，选择“程序和功能”，然后双击“Lync 2013 呼叫前诊断”。

  - 在 Windows 8 系统上，右键单击 PCD 磁贴，然后从开始屏幕底部的应用栏单击“卸载”。

