---
title: Lync Server 2013： Lync PreCall 诊断工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63743c634c9e87c743928d7641609ce12c464cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013 中的 lync PreCall 诊断工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-11-04_

Lync PreCall 诊断工具（PCD）是一种基于客户端的应用程序，可让你查看网络的当前状态在即将进行的企业语音呼叫中可能会产生的音频质量。

在网络的最后一个跃点可能是最弱的情况（例如，在公共 WiFi 网络或家庭用户的便携式计算机上）时，PCD 非常有用。 PCD 创建一个可遍历此网络最终网段的小型数据包流。 然后，该工具将分析数据包流，以估计沿此段流量的抖动和丢失可能影响呼叫质量的方式，然后提供报告。 可以在客户端上连续运行 PCD，甚至在发出呼叫时也可以。 数据包流对带宽的影响不大。

**1.1 版本的 PCD 的最新版本包括以下增强功能：**

  - 支持较长的密码，该密码现在最长可为127个字符

  - 对身份验证登录问题的其他诊断

  - 对 Lync 混合部署的更好支持

  - 凭据选取器的更新

  - 稳定性改进

感谢你的反馈。 请在上<pcdfb@microsoft.com>将所有支持问题或问题发送到[PCD 反馈](mailto:pcdfb@microsoft.com)别名。

本主题包括以下部分：

  - Lync PCD 版本

  - Lync PCD 系统要求

  - Lync PCD 功能

  - 运行 Lync PCD

  - 卸载 Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD 版本

本主题介绍了此工具的以下版本，可免费下载：

  - Windows 桌面应用程序[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)（）

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD 系统要求

<div>


> [!NOTE]  
> PCD 要求将统一通信 Web API （UCWA）安装并配置为在 Lync Server 部署中支持移动客户端。 UCWA 与 Lync Server 一起安装。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 桌面应用程序要求

  - 任何版本的 Windows 7 或 Windows 8 操作系统

  - Microsoft .NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD 功能

Lync PCD 包括以下功能：

  - 按需在默认情况下运行（2分钟猝发）

  - 在 Always On 中运行（最长为24小时，处于已对齐状态的视图中）模式

  - 测试运行的历史视图

  - 诊断登录失败（仅适用于 Windows 8 的 Lync PCD）

![Lync PCD 功能登录进度屏幕截图](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登录进度屏幕截图")

  - 网络指标（网络 MOS、数据包丢失和 Interarrival 抖动以及全屏显示和捕捉视图中的图形视图。

**全屏视图**

![PreCall 诊断工具测试结果关系图](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 诊断工具测试结果关系图")

**快照视图**

![PreCall 诊断工具利用率测试结果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 诊断工具利用率测试结果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>运行 Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>运行 Windows 桌面应用程序

1.  若要在 Windows 7 系统上启动 PCD，请从 "**开始**" 菜单中选择 " **PreCall Diagnostics** "。
    
    若要在 Windows 8 系统上启动 PCD，请在 "开始" 屏幕上选择该图标，或搜索 "PreCall Diagnostics"。
    
    ![PreCall 诊断工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 诊断工具图标")

2.  工具启动后，选择提供凭据的首选方法，并在 " **PreCall 诊断工具选项**" 对话框中选择 "网络操作模式"，然后选择 **"确定"**：

3.  选择 "**开始测试**" 按钮以开始运行诊断。
    
    如果选择 "**使用网络凭据**" 选项，测试将立即开始。
    
    如果选择 "**让我输入我的凭据**" 选项，则将打开 " **Windows 安全性**" 对话框。 输入凭据后，将开始测试。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>卸载 Lync PCD

若要删除 Lync PCD，请按照适用于您的操作系统的过程操作：

  - 在 Windows 7 系统上，打开 "**控制面板**"，选择 "**程序和功能**"，然后双击 " **Lync 2013 PreCall Diagnostics**"。

  - 在 Windows 8 系统上，右键单击 "PCD" 磁贴，然后单击 "开始" 屏幕底部的 "应用程序栏" 中的 "**卸载**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

