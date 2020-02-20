---
title: 配置将受监视的 Skype for Business Server 计算机
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：在 Skype for Business Server 2019 计算机上安装 Operations Manager 代理文件以进行监视，并将计算机配置为充当 System Center 代理。
ms.openlocfilehash: ebf859b633a0da047d61a7b0d55c430f81a02401
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150559"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>配置将受监视的 Skype for Business Server 计算机

**摘要：** 在 Skype for Business Server 2019 计算机上安装 Operations Manager 代理文件进行监视，并将计算机配置为充当 System Center 代理。

要监视的每个 Skype for Business Server 2019 计算机必须能够自我报告它是否存在于管理服务器上。 若要启用此过程，必须在要监视的每台计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为充当 System Center 代理。 在执行这些步骤之前，请务必先在这些计算机上安装和配置 Skype for business Server。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

在外围网络中运行的 System Center Operations Manager 代理（如 Skype for Business Server Edge 服务器），企业外部（如外部综合事务观察程序节点）或 Active Directory 信任边界内运行的 System Center Operations Manager 代理可能需要System Center Operations Manager 网关服务器的配置。 此服务器角色使与根管理服务器不具有信任关系的代理能够引发警报。 有关详细信息，请参阅[管理 Operations Manager 2012 中的网关服务器](https://technet.microsoft.com/library/hh212823.aspx)。

如果在其中一个位置中部署代理，则还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。 有关详细信息和下载这些实用程序的详细信息，请参阅[使用证书生成向导轻松获取用于非域加入代理的证书](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在 System Center 安装程序媒体上，双击 " **setup.exe"。**

2. 在 System Center Operation Manager 安装向导中，单击 "可选安装" 下的 "安装代理" 中的 "**安装 Operations Manager 代理**"。

3. 在 "系统中心设置向导" 的 "欢迎使用 System Center Operations Manager 安装向导" 页上，单击 "**下一步**"。

4. 在 "目标文件夹" 页上，选择将安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。

5. 在 "管理组配置" 页上，选择 "**指定管理组信息**"，然后单击 "**下一步**"。

6. 在 "管理组配置" 页上，在 "**管理组名称**" 框中键入 Operations Manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名称（例如，atl-ws-01-001）。 如果更改了 Operations Manager 使用的端口号，请在 "**管理服务器端口**" 框中输入新的端口号。 否则，将端口保留为默认值5723，然后单击 "**下一步**"。

7. 在 "代理操作帐户" 页上，选择 "**本地系统**" 并单击 "**下一步**"。

8. 在 "Microsoft Update" 页上，选择 "**我不想使用 Microsoft 更新**"，然后单击 "**下一步**"。

9. 在"准备安装"页上，单击"安装"。

10. 在 "正在完成 System Center Operations Manager 安装向导" 页上，单击 "**完成**"。

11. 单击“退出”****。

对于 System Center 2012，可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations Manager 2012**"，然后单击 "**操作2012管理器**" 来验证是否已创建代理。 在 Operations Manager 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 ENTER：
```PowerShell
Get-SCOMAgent
```

将显示所有 Operations Manager 代理的列表。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>将 Skype for Business Server 计算机配置为参与 System Center 发现
<a name="watcher_node_outside"> </a>

若要确保新的 Skype for Business Server 代理参与了 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：

1. 在 "管理" 选项卡上，单击 "**代理托管**"。

2. 单击 "**发现向导**" 并完成要发现的计算机的向导。

3. 重新启动运行状况代理服务。 重新启动该服务将强制发现新计算机。 如果不重新启动该服务，则可能需要长达4小时，System Center Operations Manager 会发现新计算机。

4. 验证 Operations Manager 事件日志中未记录任何错误事件。

5. 成功推送代理的计算机将显示在 "代理托管" 列表下，并且手动安装了代理的计算机将显示在 "挂起的管理" 下，单击 "计算机名称" 并按 "批准"。

6. 右键单击计算机的名称，然后单击“属性”****。 在 "属性" 对话框中的 "安全" 选项卡上，选择 "**允许此代理充当代理并在其他计算机上发现托管对象**"，然后单击 **"确定"**。


