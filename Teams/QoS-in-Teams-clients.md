---
title: 在 Microsoft Teams 客户端中实施服务质量
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 为 Microsoft 团队客户端实施服务质量（QoS）。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3447f86be825099b7fada63fecd1b106f94cd80a
ms.sourcegitcommit: 2b76e6a9a6ba0eb391e4adba5402eb572d1dc61f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2019
ms.locfileid: "40303864"
---
# <a name="set-qos-on-windows-clients"></a>在 Windows 客户端上设置 QoS

可以在组策略中使用基于策略的 QoS 设置团队客户端中预定义 DSCP 值的源端口范围。 下表中指定的端口范围是为每个工作负荷创建策略的起始点。

*表1。推荐的初始端口范围*

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50000-50019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|有保证的转发（AF21）|
| | | | | |

只要有可能，就会在组策略对象中配置基于策略的 QoS 设置。 以下步骤与[在 Skype for Business 服务器上配置客户端的端口范围和服务质量策略](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常相似，这种情况下可能不需要其他一些详细信息。

若要为加入域的 Windows 10 计算机创建 QoS 音频策略，请首先登录到已安装了组策略管理的计算机。 打开组策略管理（单击 "开始"，指向 "管理工具"，然后单击 "组策略管理"），然后完成以下步骤：

1. 在 "组策略管理" 中，找到应在其中创建新策略的容器。 例如，如果所有客户端计算机都位于一个名为 "**客户端**" 的 OU 中，则应在客户端 OU 中创建新策略。

1. 右键单击相应的容器，然后单击 "**在此域中创建 GPO"，然后在此处链接**。

1. 在 "**新建 GPO** " 对话框中，在 "**名称**" 框中键入新组策略对象的名称，然后单击 **"确定"**。

1. 右键单击新创建的策略，然后单击 "**编辑**"。

1. 在组策略管理编辑器中，展开 "**计算机配置**"，展开 " **Windows 设置**"，右键单击 "**基于策略的 QoS**"，然后单击 "**创建新策略**"。

1. 在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上，在 "**名称**" 框中键入新策略的名称。 选择 "**指定 DSCP 值**" 并将值设置为**46**。 "退出"**指定出站阻止率**未选中，然后单击 "**下一步**"。

1. 在下一页上，选择 "**仅限具有此可执行名称的应用程序**" 并输入名称 "**团队 .exe**"，然后单击 "**下一步**"。 此设置指示策略仅优先考虑团队客户端的匹配流量。

1. 在第三页上，确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**"，然后单击 "**下一步**"。 这两个设置确保数据包将被管理，无论哪台计算机（IP 地址）发送数据包以及哪台计算机（IP 地址）将接收这些数据包。

1. 在第4页上，从 "**选择此 QoS 策略应用**于的协议" 下拉列表中选择 " **TCP 和 UDP** "。 TCP （传输控制协议）和 UDP （用户数据报协议）是最常使用的两种网络协议。

1. 在 "标题" 下，**指定源端口号**，选择 "**从此源端口或范围**"。 在 "随附文本" 框中，键入为音频传输保留的端口范围。 例如，如果您通过端口50019为音频流量保留了端口50000，请使用以下格式输入端口范围： **50000:50019**。 单击“**完成**”。

1. 重复步骤5-10 以创建视频和应用程序/桌面共享的策略，在步骤6和10中替换相应的值。

在客户端计算机上刷新组策略之前，你创建的新策略不会生效。 虽然组策略定期定期刷新，但你可以通过执行以下步骤强制立即刷新：

1. 在要刷新组策略的每台计算机上，以管理员身份打开命令提示符（以*管理员身份运行*）。

1. 在命令提示符处，输入

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>验证组策略对象中的 DSCP 标记

若要验证是否已设置组策略对象中的值，请执行以下步骤：

1. 以管理员身份打开命令提示符（以*管理员身份运行*）。

1. 在命令提示符处，输入

   ```console
   gpresult /R > gp.txt
   ```

   这将生成已应用 Gpo 的报表，并将其发送到名为*gp*的文本文件。

   对于名为*gp*的更易读的 html 报表，请输入以下命令：

   ```console
   gpresult /H gp.html
   ```

1. 在生成的文件中，查找标题**应用的组策略对象**，并验证之前创建的组策略对象的名称是否在已应用的策略列表中。

1. 打开注册表编辑器，然后转到

   Microsoft\_\\Windows\\QoS\\HKEY\\本地\\\_计算机软件策略

   验证表2中列出的注册表项的值。

   *表2。QoS 的 Windows 注册表项的值*

   |          名称          |  类型  |    数据     |
   |         :---:          | :---:  |    :---:    |
   |    应用程序名称    | REG_SZ |  Teams.exe  |
   |       DSCP 值       | REG_SZ |     46      |
   |        本地 IP        | REG_SZ |     \*      |
   | 本地 IP 前缀长度 | REG_SZ |     \*      |
   |       本地端口       | REG_SZ | 50000-50019 |
   |        协议        | REG_SZ |     \*      |
   |       远程 IP        | REG_SZ |     \*      |
   |    远程 IP 前缀    | REG_SZ |     \*      |
   |      远程端口       | REG_SZ |     \*      |
   |     限制率      | REG_SZ |     -1      |
   | | | |

1. 验证应用程序名称条目的值对于你正在使用的客户端是否正确，并验证 DSCP 值和本地端口条目是否反映了组策略对象中的设置。
