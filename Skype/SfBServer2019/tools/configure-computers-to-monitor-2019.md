---
title: 配置Skype for Business Server的计算机
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 摘要：在要监视的 Skype for Business Server 2019 计算机上安装 Operations Manager 代理文件，将计算机配置为充当 System Center 代理。
---

# <a name="configure-the-skype-for-business-server-computers-to-monitore"></a>配置要Skype for Business Server的计算机

**摘要：** 在要监视的 Skype for Business Server 2019 计算机上安装 Operations Manager 代理文件，将计算机配置为充当 System Center 代理。

要Skype for Business Server的每台 2019 计算机必须能够自行向管理服务器报告其是否存在。 若要启用此过程，必须在要监视的每台计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为充当代理System Center代理。 在执行这些过程之前，请确保首先在这些Skype for Business Server安装和配置这些计算机。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

System Center 在外围网络 (如 Skype for Business Server 边缘服务器) 、企业 (外部（如外部综合事务观察程序节点) ）或跨 Active Directory 信任边界运行的 Operations Manager 代理可能需要配置 System Center Operations Manager 网关服务器。 此服务器角色使与根管理服务器没有信任关系的代理能够发出警报。 有关详细信息，请参阅 [Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))。

如果您在这些位置之一部署代理，则还需要请求并配置证书，使观察程序节点能够向 Operations Manager System Center警报。 为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。 有关详细信息和下载这些实用工具，请参阅使用证书生成向导轻松获取未加入域的代理 [的证书](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467)。

### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在设置System Center媒体上，双击"Setup.exe **"**。

2. 在"System Center管理器安装向导"中，单击"可选安装"下的"安装代理"中的"安装 **Operations Manager** 代理"

3. 在System Center安装向导的"欢迎使用 System Center Operations Manager 安装向导"页上，单击"下一步 **"**。

4. 在"目标文件夹"页上，选择将安装 Operations Manager 代理文件的文件夹，然后单击"下一步 **"**。

5. 在"管理组配置"页上，选择 **"指定管理组信息"，** 然后单击"下一步 **"**。

6. 在"管理组配置"页上的"管理组名称"框中键入 Operations Manager 管理组的名称，然后在"管理服务器"框中键入 Operations Manager 服务器的主机名 (例如 atl-scom-001) 。 如果更改了 Operations Manager 使用的端口号，请在"管理服务器端口"框中输入 **新的端口** 号。 否则，将端口保留为默认值 5723，然后单击"下一步 **"**。

7. 在"代理操作帐户"页上，选择" **本地系统"** ，然后单击"下一步 **"**。

8. 在"Microsoft 更新"页上，选择"我不想 **使用 Microsoft 更新"** ，然后单击"下一步 **"**。

9. 在"准备安装"页上，单击"安装"。

10. 在"正在完成 operations Manager System Center向导"页上，单击"完成 **"**。

11. 单击“退出”。

对于 System Center 2012，可以单击"开始"，单击"所有程序"，再单击 **"System Center Operations Manager 2012**"，然后单击"**Operations 2012 Manager Shell**"，来验证该代理已创建。 在Operations Manager 外壳中，键入以下 Windows PowerShell 命令，然后按 Enter：
```PowerShell
Get-SCOMAgent
```

将显示所有 Operations Manager 代理的列表。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>配置Skype for Business Server计算机以参与System Center发现
<a name="watcher_node_outside"> </a>

要确保新的 Skype for Business Server 代理参与 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机中完成以下过程：

1. 在"管理"选项卡上，单击" **代理托管"**。

2. 单击 **"发现向导** "，然后完成向导以发现计算机。

3. 重新启动运行状况代理服务。 重新启动服务将强制发现新计算机。 如果未重新启动该服务，则 Operations Manager 可能需要 4 小时System Center计算机。

4. 确认在 Operations Manager 事件日志中未记录任何错误事件。

5. 成功推送代理的计算机将显示在"代理托管"列表下，手动安装代理的计算机将显示在"待处理管理"下，单击计算机名称并批准。

6. 右键单击计算机的名称，然后单击“属性”。 在"属性"对话框中的"安全性"选项卡上，选择"允许此代理充当代理并发现其他计算机上的托管对象"，然后单击"确定 **"**。