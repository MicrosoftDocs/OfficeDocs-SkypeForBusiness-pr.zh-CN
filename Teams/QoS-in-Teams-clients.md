---
title: '在 Microsoft Teams 客户端中实现服务质量 (QoS) '
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何使用服务质量 (QoS) 优化 Microsoft Teams 桌面客户端的网络流量。
ms.localizationpriority: medium
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
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563920"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>在 Microsoft Teams 客户端中实现服务质量 (QoS) 

可以在组策略中使用基于策略的服务质量 (QoS) 为 Teams 客户端中的预定义 DSCP 值设置源端口范围。 下表中指定的端口范围是为每个工作负荷创建策略的起点。

*表 1.建议的初始端口范围*

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50,000–50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|保证转发 (AF21)|
| | | | | |

尽可能在组策略对象中配置基于策略的 QoS 设置。 以下步骤非常类似于[在 Skype for Business Server 上为客户端配置端口范围和服务质量策略](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)，其中包含一些可能不需要的其他详细信息。

若要为已加入域的Windows 10计算机创建 QoS 音频策略，请先登录到已安装组策略管理的计算机。 打开组策略管理 (单击“开始”，指向“管理工具”，然后单击组策略管理) ，然后完成以下步骤：

1. 在组策略管理中，找到应在其中创建新策略的容器。 例如，如果所有客户端计算机都位于名为 **“客户** 端”的 OU 中，则应在客户端 OU 中创建新策略。

1. 右键单击相应的容器，然后单击 **此域中的“创建 GPO”，并将其链接到此处**。

1. 在 **“新建 GPO**”对话框中，在 **“名称**”框中键入新组策略对象的名称，然后单击 **“确定**”。

1. 右键单击新创建的策略，然后单击 **“编辑**”。

1. 在组策略管理编辑器中，展开 **“计算机配置**”，展开 **Windows 设置**，右键单击 **基于策略的 QoS**，然后单击 **“创建新策略**”。

1. 在 **“基于策略的 QoS** ”对话框的开页上，在 **“名称”** 框中键入新策略的名称。 选择 **“指定 DSCP 值** ”并将值设置为 **46**。 保留 **未选择“指定出站限制速率** ”，然后单击 **“下一步**”。

1. 在下一页上，选择 **“仅限具有此可执行文件名称的应用程序”** ，然后 **输入名称Teams.exe**，然后单击“ **下一步**”。 此设置指示策略仅确定来自 Teams 客户端的匹配流量的优先级。

1. 在第三页上，确保同时选择 **“任何源 IP 地址** ”和 **“任何目标 IP 地址** ”，然后单击“ **下一步**”。 这两个设置可确保无论发送数据包) 哪个计算机 (IP 地址，以及哪些计算机 (IP 地址) 将接收数据包，数据包都将得到管理。

1. 在第四页上，从 **“选择此 QoS 策略适用于** 下拉列表的协议”中选择 **TCP 和 UDP**。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是最常用的两种网络协议。

1. 在“ **指定源端口号**”标题下， **选择“从此源端口或范围**”。 在随附的文本框中，键入为音频传输保留的端口范围。 例如，如果为音频流量保留端口 50000 到端口 50019，请使用以下格式输入端口范围： **50000：50019**。 单击“**完成**”。

1. 重复步骤 5-10，为视频和应用程序/桌面共享创建策略，在步骤 6 和 10 中替换相应的值。

创建的新策略在客户端计算机上刷新组策略后才会生效。 尽管组策略会自行定期刷新，但可以通过执行以下步骤来强制立即刷新：

1. 在要刷新组策略的每台计算机上，以管理员身份打开命令提示符 (*以管理员身份运行*) 。

1. 在命令提示符处输入

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>验证组策略对象中的 DSCP 标记

若要验证是否已设置组策略对象中的值，请执行以下步骤：

1. 以管理员身份打开命令提示符 (*以管理员身份运行*) 。

1. 在命令提示符处输入

   ```console
   gpresult /R > gp.txt
   ```

   这将生成已应用 GPO 的报表，并将其发送到名为 *gp.txt* 的文本文件。

   对于名为 *gp.html* 的更易读的 HTML 报表，请输入以下命令：

   ```console
   gpresult /H gp.html
   ```

1. 在生成的文件中，查找 **“应用组策略对象**”标题，并验证前面创建的组策略对象的名称是否在应用策略列表中。

1. 打开注册表编辑器，然后转到

   HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS

   验证表 2 中列出的注册表项的值。

   *表 2.适用于 QoS 的 Windows 注册表项的值*

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

1. 验证所用客户端的应用程序名称条目的值是否正确，并验证 DSCP 值和本地端口条目是否都反映了组策略对象中的设置。


## <a name="related-topics"></a>相关主题

[在 Teams 中实现服务质量 (QoS) ](QoS-in-Teams.md)