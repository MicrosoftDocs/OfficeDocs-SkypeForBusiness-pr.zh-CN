---
title: 配置将受视的 Skype for Business Server 计算机
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要：在要监视的 Skype for business Server 2015 计算机上安装 Operations Manager 代理文件，并将计算机配置为充当 System Center proxy。
ms.openlocfilehash: 5279924c29e8dba11882ca7d172c06894a7808b8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992469"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>配置将受视的 Skype for Business Server 计算机

**摘要：** 在要监视的 Skype for business Server 2015 计算机上安装 Operations Manager 代理文件，并将计算机配置为充当 System Center proxy。

要监视的每个 Skype for Business 服务器2015计算机必须能够自我报告它是否存在于管理服务器。 为了启用此过程，必须在每台要受监视的计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为作为 System Center 代理。 在执行这些过程之前，请确保首先在这些计算机上安装和配置 Skype for Business 服务器。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

在外围网络（如 Skype for Business 服务器 Edge 服务器）之外、企业外部（如外部合成事务观察程序节点）或跨 Active Directory 信任边界运行的 System Center Operations Manager 代理可能需要System Center Operations Manager 网关服务器的配置。 此服务器角色可使与根管理服务器没有信任关系的代理发出警报。 有关详细信息，请参阅[管理 Operations Manager 中的网关服务器 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx)。

如果在其中一个位置中部署代理，你还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为简化此过程，Operations Manager 团队已创建一组实用工具，可让你在观察程序节点计算机上请求和安装正确的证书类型。 有关详细信息和下载这些实用程序的信息，请参阅[通过证书生成向导轻松获取用于非域加入代理的证书](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在 System Center 安装介质上，双击“Setup.exe****”。

2. 在 System Center Operation Manager 安装程序向导中，单击 "**安装 Operations Manager 代理**"，从 "可选安装" 下的 "安装代理"

3. 在 System Center 设置向导中的 "欢迎使用 System Center Operations Manager 安装程序向导" 页面上，单击 "**下一步**"。

4. 在 "目标文件夹" 页面上，选择将安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。

5. 在“管理组配置”页面上选择“指定管理组信息”****。然后单击“下一步”****。

6. 在 "管理组配置" 页面上，在 "**管理组名称**" 框中键入 Operations Manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名（如 "atl-scom-001"）。 如果更改了 Operations Manager 使用的端口号，请在 "**管理服务器端口**" 框中输入新的端口号。 否则，将该端口保留为默认值5723，然后单击 "**下一步**"。

7. 在“代理操作帐户”页面上，选择“本地系统”****，然后单击“下一步”****。

8. 在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”****，然后单击“下一步”****。

9. 在“安装准备就绪”页面上，单击“安装”****。

10. 在 "正在完成 System Center Operations Manager 安装向导" 页面上，单击 "**完成**"。

11. 单击“退出”****。

对于 System Center 2012，你可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations manager 2012**"，然后单击 "**操作2012管理器**" 来验证是否已创建代理。 In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

所有 Operations Manager 代理的列表将出现在屏幕上。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>将 Skype for Business Server 计算机配置为参加 System Center Discovery
<a name="watcher_node_outside"> </a>

若要确保新的 Skype for Business 服务器代理参与 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：

1. 在“管理”选项卡上，单击“代理托管”****。

2. 单击“发现向导”****，然后完成向导，以使计算机能被发现。

3. 重新启动健康代理服务。 重新启动该服务将强制发现新计算机。 如果您不重新启动该服务，则系统中心运营经理可能需要长达4小时才能发现新计算机。

4. 验证 Operations Manager 事件日志中是否未记录任何错误事件。

5. 成功推送代理的计算机将显示在 "代理托管" 列表下，并且手动安装了代理的计算机将显示在 "挂起的管理" 下，单击计算机名称并批准。

6. 右键单击计算机的名称，然后单击“属性”****。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。


