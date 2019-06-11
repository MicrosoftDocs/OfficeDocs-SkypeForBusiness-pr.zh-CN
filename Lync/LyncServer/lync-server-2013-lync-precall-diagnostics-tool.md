---
title: 'Lync Server 2013: Lync PreCall 诊断工具'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013 中的 lync PreCall 诊断工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-11-04_

Lync PreCall 诊断工具 (PCD) 是基于客户端的应用程序, 可让你查看网络的当前状态如何影响未来的企业语音通话中的音频质量。

在网络的最后一个跃点可能是最弱的情况下 (例如, 在公共 WiFi 网络或家庭用户上使用膝上型电脑), PCD 非常有用。 PCD 创建一个小型数据包流, 该流遍历网络的这最后一条路。 然后, 该工具将分析数据包流, 以估计沿此段腿的抖动和损失可能会影响呼叫质量, 然后提供报告。 你可以在客户端上持续运行 PCD, 即使在通话时也是如此。 数据包流对带宽没有显著影响。

**PCD 版本1.1 的最新版本包括以下增强功能:**

  - 支持较长的密码, 该密码现在最多可达127个字符

  - 针对身份验证登录问题的其他诊断

  - 更好地支持 Lync 混合部署

  - 对凭据选取器的更新

  - 稳定性改进

我们非常感谢您的反馈。 请将所有支持问题或问题发送到[PCD 反馈](mailto:pcdfb@microsoft.com)别名<pcdfb@microsoft.com>。

本主题包括以下部分：

  - Lync PCD 版本

  - Lync PCD 系统要求

  - Lync PCD 功能

  - 运行 Lync PCD

  - 卸载 Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD 版本

本主题介绍以下版本的工具, 可供免费下载:

  - Windows 桌面应用 ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD 系统要求

<div>


> [!NOTE]  
> PCD 要求在 Lync Server 部署中安装和配置统一通信 Web API (UCWA) 以支持移动客户端。 UCWA 与 Lync Server 一起安装。



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 桌面应用要求

  - Windows 7 或 Windows 8 操作系统的任何版本

  - Microsoft .NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD 功能

Lync PCD 包括以下功能:

  - 默认按需运行 (2 分钟爆发)

  - 在始终打开的情况下运行 (最多24小时, 在贴靠视图中) 模式

  - 测试运行的历史视图

  - 诊断登录失败 (仅适用于 Windows 8 的 Lync PCD)

![LYNC PCD 功能登录进度屏幕截图](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "LYNC PCD 功能登录进度屏幕截图")

  - 网络指标的图形化视图-以全屏和贴靠视图显示网络 MOS、数据包丢失和 Interarrival 抖动。

**全屏视图**

![PreCall 诊断工具测试结果图形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 诊断工具测试结果图形")

**贴靠视图**

![PreCall 诊断工具利用率测试结果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 诊断工具利用率测试结果")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>运行 Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>运行 Windows 桌面应用

1.  若要在 Windows 7 系统上启动 PCD, 请从 "**开始**" 菜单中选择 " **PreCall 诊断**"。
    
    若要在 Windows 8 系统上启动 PCD, 请在 "开始" 屏幕上选择该图标, 或搜索 "PreCall Diagnostics"。
    
    ![PreCall 诊断工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 诊断工具图标")

2.  当工具启动时, 选择提供凭据的首选方法, 然后在 " **PreCall 诊断工具选项**" 对话框中选择 "网络操作模式", 然后选择 **"确定"**:

3.  选择 "**开始测试**" 按钮以开始运行诊断。
    
    如果选择 "**使用网络凭据**" 选项, 测试将立即开始。
    
    如果选择 "**让我输入我的凭据**" 选项, 则会打开 " **Windows 安全**" 对话框。 输入凭据后, 测试开始。

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>卸载 Lync PCD

若要删除 Lync PCD, 请按照操作系统的步骤进行操作:

  - 在 Windows 7 系统上, 打开 "**控制面板**", 选择 "**程序和功能**", 然后双击 " **Lync 2013 PreCall 诊断**"。

  - 在 Windows 8 系统上, 右键单击 "PCD" 磁贴, 然后单击 "开始" 屏幕底部的应用栏中的 "**卸载**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

