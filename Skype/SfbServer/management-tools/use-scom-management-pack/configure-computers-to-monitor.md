---
title: 配置将受视的 Skype for Business Server 计算机
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要： 安装上业务服务器 2015年计算机 Skype 要监视的 Operations Manager 代理文件，并配置计算机充当 System Center 代理。
ms.openlocfilehash: 047f362cc799f46a000fb8aa3a314bb189305e2c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262461"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>配置将受视的 Skype for Business Server 计算机

**摘要：** 安装上业务服务器 2015年计算机 Skype 要监视的 Operations Manager 代理文件和配置计算机充当 System Center 代理。

每个 Skype 要监视的业务服务器 2015年计算机必须能够自报告其存在到管理服务器。 为了启用此过程，必须在每台要受监视的计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为作为 System Center 代理。 确保先安装和 Skype 业务服务器上配置这些计算机在执行这些过程之前。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

System Center Operations Manager 代理运行在外围网络 （如业务 Server 边缘服务器的 Skype) 之外 （如外部综合事务观察程序节点中） 企业或边界，可能需要通过 Active Directory 信任系统中心操作管理器网关服务器的配置。 此服务器角色可使与根管理服务器没有信任关系的代理发出警报。 有关详细信息，请参阅[Operations Manager 2012 中管理网关服务器](https://technet.microsoft.com/en-us/library/hh212823.aspx)。

如果您部署中两个位置之一的代理，还需要请求和配置证书以允许将通知发送给 System Center Operations Manager 的观察程序节点。 若要简化此过程，Operations Manager 团队已创建一组实用程序，您可以请求并在观察程序节点计算机上安装证书的正确的类型。 有关详细信息，以及若要下载这些实用程序，请参阅[为非域加入代理轻松使用证书生成向导获取证书](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在 System Center 安装介质上，双击“Setup.exe****”。

2. 在 System Center Operation Manager 安装向导中，单击**安装 Operations Manager 代理**，请从安装可选安装下的代理

3. 在 System Center 安装向导中，在欢迎使用 ' System Center Operations Manager 安装向导页上单击**下一步**。

4. 在目标文件夹页上，选择的文件夹，其中的 Operations Manager 代理文件将被安装，并单击**下一步**。

5. 在“管理组配置”页面上选择“指定管理组信息”****。然后单击“下一步”****。

6. 在管理组配置页上，在**管理组名称**框中，键入您的操作管理器管理组的名称，然后键入您的 Operations Manager 服务器的主机名 (例如，atl-scom 001)**管理服务器中**框。 如果您已经更改 Operations Manager 所使用的端口号，请在**管理服务器端口**框中输入新的端口号。 否则为将保留在 5723 的默认值的端口，然后单击**下一步**。

7. 在“代理操作帐户”页面上，选择“本地系统”****，然后单击“下一步”****。

8. 在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”****，然后单击“下一步”****。

9. 在“安装准备就绪”页面上，单击“安装”****。

10. 在完成 ' System Center Operations Manager 安装向导页中，单击**完成**。

11. 单击“退出”****。

有关 System Center 2012，您可以验证已通过再依次单击**开始**、**所有程序**、 **System Center Operations Manager 2012**，然后单击**Operations 2012 Manager Shell**创建代理。 在 Operations Manager Shell 中，键入以下 Windows PowerShell 命令，然后按 ENTER:
```
Get-SCOMAgent
```

所有 Operations Manager 代理的列表将出现在屏幕上。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>将 Skype for Business Server 计算机配置为参加 System Center Discovery
<a name="watcher_node_outside"> </a>

若要确保，您的业务服务器代理的新 Skype 参与发现过程的 System Center Operations Manager，您必须完成以下过程在每台已安装 System Center Operations Manager 控制台的计算机上：

1. 在“管理”选项卡上，单击“代理托管”****。

2. 单击“发现向导”****，然后完成向导，以使计算机能被发现。

3. 重新启动健康代理服务。 重新启动该服务将强制发现新计算机。 如果您不重新启动该服务，它可能需要长达 4 小时，才能在新计算机发现的 System Center Operations Manager。

4. 验证 Operations Manager 事件日志中是否未记录任何错误事件。

5. 代理成功推送的计算机将显示在"代理托管"列表下方和代理已手动安装的计算机将显示在"待处理管理"下方，单击计算机名称和批准。

6. 右键单击计算机的名称，然后单击“属性”****。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。


