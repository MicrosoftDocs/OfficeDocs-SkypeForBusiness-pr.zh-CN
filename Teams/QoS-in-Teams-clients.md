---
title: 在客户端中实现服务质量 (QoS) Microsoft Teams服务
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何使用服务质量 (QoS) 优化桌面客户端Microsoft Teams网络流量。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094780"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>在客户端中实现服务质量 (QoS) Microsoft Teams服务

可以在组策略内使用基于策略的服务质量 (QoS) ，为 Teams 客户端中的预定义 DSCP 值设置源端口范围。 下表中指定的端口范围是为每个工作负荷创建策略的起点。

*表 1.建议的初始端口范围*

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50,000–50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|保证转发 (AF21)|
| | | | | |

尽可能在组策略对象中配置基于策略的 QoS 设置。 以下步骤非常类似于在 Skype for Business Server[](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上为客户端配置端口范围和服务质量策略，该策略具有一些可能不需要的其他详细信息。

若要为已加入域的计算机Windows 10 QoS 音频策略，请首先登录到已安装组策略管理的计算机。 打开"组策略管理 (单击"开始"，指向"管理工具"，并单击"组策略管理") ，然后完成以下步骤：

1. 在"组策略管理"中，找到应创建新策略的容器。 例如，如果所有客户端计算机都位于名为 **"** 客户端"的 OU 中，应在"客户端 OU"中创建新策略。

1. 右键单击相应的容器，并单击"在此域中创建 **GPO"，并在此处链接它**。

1. 在"**新建 GPO"** 对话框中的"名称"框中键入新组策略 **对象的名称，** 然后单击"确定 **"。**

1. 右键单击新建的策略，然后单击"编辑 **"。**

1. 在组策略管理编辑器中，展开"**计算机** 配置"，展开Windows 设置，右键单击"基于策略的 **QoS"，** 然后单击"**创建新策略"。** 

1. 在" **基于策略的 QoS"** 对话框的打开页上，在"名称"框中键入新 **策略** 的名称。 选择 **"指定 DSCP 值**"，将值设置为 **46。** 将 **"指定出站限制速率"** 保留未选择，然后单击"下一 **步"。**

1. 下一页上，选择"**仅具有此可执行文件** 名称的应用程序"，Teams.exe **名称，** 然后单击"下一 **步"。** 此设置指示策略仅优先处理来自客户端的Teams流量。

1. 第三页上，确保同时选中"任何 **源 IP** 地址"和"任何 **目标 IP** 地址"，并单击"下一步 **"。** 这两个设置可确保无论哪个计算机 (IP 地址) 数据包，以及哪个计算机 (IP 地址) 数据包都将进行管理。

1. 在"第 4 页"的"**选择此 QoS** 策略应用于的协议"下拉列表中选择"TCP 和 **UDP"。** TCP (传输控制协议) UDP (用户数据报协议) 是最常用的两种网络协议。

1. 在标题"**指定源端口号"下**，选择 **"从此源端口或范围"。** 在随附的文本框中，键入为音频传输保留的端口范围。 例如，如果通过音频流量的端口 50019 保留端口 50000，则使用此格式输入端口范围 **：50000：50019。** 单击“**完成**”。

1. 重复步骤 5-10，为视频和应用程序/桌面共享创建策略，用步骤 6 和 10 中的相应值进行表示。

在客户端计算机上刷新组策略之前，已创建的新策略不会生效。 尽管组策略会定期自行刷新，但可以通过执行以下步骤来强制立即刷新：

1. 在要刷新组策略的每台计算机中，以管理员角色打开命令提示符 (以管理员) 。 

1. 在命令提示符下，输入

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>验证组策略对象中的 DSCP 标记

若要验证组策略对象中的值是否已设置，请执行以下步骤：

1. 以管理员角色打开命令提示符 (*以管理员角色运行) 。*

1. 在命令提示符下，输入

   ```console
   gpresult /R > gp.txt
   ```

   这会生成应用 GPO 的报告，并将其发送到名为gp.txt *的文本文件*。

   对于名为gp.htm *l 的* 更具可读性的 HTML 报表，请输入以下命令：

   ```console
   gpresult /H gp.html
   ```

1. 在生成的文件中，查找标题"已应用组 **策略** 对象"，并验证之前创建的组策略对象的名称是否在应用的策略列表中。

1. 打开注册表编辑器，然后转到

   HKEY \_ 本地 \_ 计算机 \\ 软件策略 Microsoft Windows \\ \\ \\ \\ QoS

   验证表 2 中列出的注册表项的值。

   *表 2.QoS Windows注册表项的值*

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

1. 验证"应用程序名称"条目的值是否适用于使用的客户端，并验证 DSCP 值和本地端口条目是否反映组策略对象中的设置。


## <a name="related-topics"></a>相关主题

[在 Teams 中 (QoS) 服务质量Teams](QoS-in-Teams.md)