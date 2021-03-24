---
title: 配置将受监视的 Skype for Business Server 计算机
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要：在要监视的 Skype for Business Server 2015 计算机上安装 Operations Manager 代理文件，将计算机配置为充当 System Center 代理。
ms.openlocfilehash: bb4dc64a1c04bbef1b6cb0e391fc27568edfef43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111678"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>配置将受监视的 Skype for Business Server 计算机

**摘要：** 在要监视的 Skype for Business Server 2015 计算机上安装 Operations Manager 代理文件，将计算机配置为充当 System Center 代理。

要监视的每台 Skype for Business Server 2015 计算机必须能够自行向管理服务器报告其是否存在。 若要启用此过程，必须在要监视的每台计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为充当 System Center 代理。 在执行这些过程之前，请确保你首先在这些计算机上安装和配置了 Skype for Business Server。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

在外围网络 (如 Skype for Business Server 边缘服务器) 、企业 (外部（如外部综合事务观察程序节点) ）或跨 Active Directory 信任边界运行的 System Center Operations Manager 代理可能需要配置 System Center Operations Manager 网关服务器。 此服务器角色使与根管理服务器没有信任关系的代理能够发出警报。 有关详细信息，请参阅[Managing Gateway Servers in Operations Manager 2012。](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))

如果在这些位置之一部署代理，则还需要请求并配置允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。 有关详细信息，并下载这些实用工具，请参阅获取证书为未加入域的代理轻松使用证书生成 [向导](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在 System Center 设置媒体上，双击 **"Setup.exe"。**

2. 在 System Center Operation Manager 安装向导中，单击"可选安装"下的"安装代理"中的"安装 **Operations Manager** 代理"

3. 在 System Center 安装向导的"欢迎使用 System Center Operations Manager 安装向导"页上，单击"下一步 **"。**

4. 在"目标文件夹"页上，选择将安装 Operations Manager 代理文件的文件夹，然后单击"下一步 **"。**

5. 在"管理组配置"页上，选择"**指定管理组信息"，** 然后单击"下一 **步"。**

6. 在"管理组配置"页上的"管理组名称"框中键入 Operations  Manager 管理组的名称，然后在"管理服务器"框中键入 Operations Manager 服务器的主机名 (例如 atl-scom-001) 。  如果更改了 Operations Manager 使用的端口号，请在"管理服务器端口"框中输入 **新的端口** 号。 否则，将端口保留为默认值 5723，然后单击"下一步 **"。**

7. 在"代理操作帐户"页上，选择"**本地系统"，** 然后单击"下一 **步"。**

8. 在"Microsoft 更新"页上，选择"我不想 **使用 Microsoft 更新**"，然后单击"下一步 **"。**

9. 在"准备安装"页上，单击"安装"。

10. 在"正在完成 System Center Operations Manager 安装向导"页上，单击"完成 **"。**

11. 单击“退出”。

For System Center 2012， you can verify that the agent has been created by clicking **Start**， clicking **All Programs**， clicking System Center Operations **Manager 2012**， and then clicking **Operations 2012 Manager Shell**. 在 Operations Manager Shell 中，键入以下 Windows PowerShell 命令，然后按 Enter：
```PowerShell
Get-SCOMAgent
```

将显示所有 Operations Manager 代理的列表。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>配置 Skype for Business Server 计算机以参与 System Center Discovery
<a name="watcher_node_outside"> </a>

若要确保新的 Skype for Business Server 代理参与 System Center Operations Manager 的发现过程，必须在已安装 System Center Operations Manager 控制台的每台计算机中完成以下过程：

1. 在"管理"选项卡上，单击"**代理托管"。**

2. 单击 **"发现向导** "，然后完成向导以发现计算机。

3. 重新启动运行状况代理服务。 重新启动服务将强制发现新计算机。 如果不重新启动该服务，System Center Operations Manager 可能需要 4 小时才能发现新计算机。

4. 确认在 Operations Manager 事件日志中未记录任何错误事件。

5. 成功推送代理的计算机将显示在"代理托管"列表下，手动安装代理的计算机将显示在"待处理管理"下，单击计算机名称并批准。

6. 右键单击计算机的名称，然后单击“属性”。 在"属性"对话框中的"安全性"选项卡上，选择"允许此代理充当代理并发现其他计算机上的托管对象"，然后单击"确定 **"。**