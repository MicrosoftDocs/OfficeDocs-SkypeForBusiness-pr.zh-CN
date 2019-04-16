---
title: 在 Microsoft Teams 客户端中实施服务质量
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 实现 Microsoft 团队客户端服务质量 (QoS)。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869843"
---
# <a name="set-qos-on-windows-clients"></a>在 Windows 客户端上设置 QoS

您可以使用基于策略的 QoS 组策略中设置团队客户端中的预定义的 DSCP 值的源端口范围。 下表中指定的端口范围是要创建的每个工作负荷策略的起始点。

_建议初始端口范围_

媒体通信类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50000 – 50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020 – 50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040 – 50,059|TCP/UDP|18|保证转发 (AF21)|
| | | | |

只要有可能，配置组策略对象中基于策略的 QoS 设置。 以下步骤是非常类似于[配置端口范围和客户端 Skype 业务服务器上的服务质量策略](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)，上面有可能不需要某些其他详细信息。

若要创建的加入域的 Windows 10 计算机音频 QoS 策略，首次登录到计算机上安装的组策略管理。 打开组策略管理 （单击开始、 管理工具，，然后单击组策略管理），然后完成以下步骤：

1. 在组策略管理中，找到应在其中创建新策略的容器。 例如，如果您的所有客户端计算机位于名为**客户端**OU，应客户端 OU 中创建新策略。

2. 右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。

3. **新建 GPO**对话框中，在**名称**框中，键入新的组策略对象的名称，然后单击**确定**。

4. 右键单击新建的策略，，然后单击**编辑**。

5. 在组策略管理编辑器中，展开**计算机配置**，展开**Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**新建策略**。

6. 在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略的名称。 选择**指定 DSCP 值**并将值设置为**46**。 保留未选择，**指定出站调节率**，然后单击**下一步**。

7. 在下一页上，选择**仅使用此可执行文件名称的应用程序**和输入**Teams.exe**的名称，然后单击**下一步**。 此设置指示要仅设置优先级团队客户端的匹配流量的策略。

8. 在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。 这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送数据包和哪台计算机 （IP 地址） 将接收数据包。

9. 在四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。 TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的两个网络协议。

10. 在标题下**指定源端口号**，**从此源端口或范围**中进行选择。 在相应的文本框中，键入供音频传输的端口范围。 例如，如果预留端口 50000 到音频流量的端口 50019，输入使用以下格式的端口范围： **50000:50019**。 单击“**完成**”。

11. 重复步骤 5-10，以创建策略的视频和应用程序/桌面共享，替换步骤 6 和 10 中的相应值。

已在客户端计算机上刷新组策略之前，您已创建的新策略不会生效。 虽然自己定期刷新组策略，您可以通过执行以下步骤来强制立即刷新：

1. 在您要刷新组策略的每台计算机上打开命令控制台。 确保命令控制台设置以管理员身份运行。

2. 在命令提示符处，输入

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>验证 DSCP 标记中的组策略对象

若要验证已设置的组策略对象的值，请执行以下步骤。

1. 打开一个命令控制台。 确保命令控制台设置以管理员身份运行。

2. 在命令提示符处，输入：

   ``` powershell
   gpresult /R > gp.txt
   ```

   这将生成一个报告，并将其发送到一个名为 gp.txt 文本文件。 或者，您可以输入以下命令以生成更容易阅读 HTML 报表名为 gp.html 中相同的数据：

   ``` powershell
   gpresult /H >gp.html
   ```

   ![运行 gpresult 命令控制台窗口的屏幕截图。](media/Qos-in-Teams-Image3.png "运行 gpresult 命令控制台窗口的屏幕截图。")

3. 在生成的文件中，查找的标题**应用组策略对象**和验证前面创建的组策略对象的名称位于应用策略的列表。

4. 打开注册表编辑器中，并转到：

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   验证表 4 中列出的注册表项的值。

   _表 4。QoS 程序的 Windows 注册表项的值_

   |          名称          |  类型  |    数据     |
   |         :---:          |:---:   |    :---:    |
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

5. 验证应用程序名称条目的值正确客户端使用，并确认的 DSCP 值和本地端口条目反映中的组策略对象的设置。
