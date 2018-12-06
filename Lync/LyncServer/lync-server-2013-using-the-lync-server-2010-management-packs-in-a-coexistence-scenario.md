---
title: 在共存方案中使用 Lync Server 2010 管理包
TOCTitle: 在共存方案中使用 Lync Server 2010 管理包
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205078(v=OCS.15)
ms:contentKeyID: 49313524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在共存方案中使用 Lync Server 2010 管理包

 

_**上一次修改主题：** 2012-10-22_

许多客户的企业内部从 Microsoft Lync Server 2010 迁移到 Lync Server 2013 的用户数日益增多，因此这些客户实施了推出计划。这些公司的管理员将注重于监控这两种版本的 Lync Server，以帮助确保其所有最终用户将获得可能的最佳通信体验。对于此方案，Lync Server 2013 管理包支持 Lync Server 2010 管理包的并行迁移路径。

在 Lync Server 2010 中，Lync Server 计算机是通过随中央管理存储一起存储的拓扑文档发现的。在此配置中，单个计算机将报告所有其他 Lync Server 计算机的存在。

Lync Server 2013 的管理包现在使用计算机级别的发现，而不是 Lync Server 2010 中已使用的中央发现机制。这意味着，每个系统中心代理实际上将发现本身，并将向 System Center Operations Manager 报告其存在。使用计算机级别发现可简化系统中心基础结构的管理，还可以使不同版本的 Lync Server 管理包（例如，Lync Server 2010 的管理包和 Lync Server 2013 的管理包）更轻松地共存。

若要支持此迁移，您需要先升级现有 Lync Server 2010 监控以避免覆盖范围差异。为此，在将中央管理存储升级到 Lync Server 2013 之前，请先选择现有 Lync Server 2010 计算机以便为 Lync Server 2010 的中央发现脚本提供服务。这是一个四步骤过程：

1.  将 Lync Server 2010 管理包升级到累积更新 7。

2.  指示 Lync Server 2010 计算机运行中央发现脚本。

3.  覆盖 Microsoft Lync Server 2010 管理包中的中央发现候选。

4.  确认已发现新的中央发现候选。

## 指示 Lync Server 2010 计算机运行中央发现脚本

若要指定非中央管理存储计算机（例如，Lync Server 前端）服务器来处理中央发现，您需要在非中央管理存储服务器上创建以下注册表项：

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

可通过完成以下过程来创建此注册表项：

1.  单击“开始”，然后单击“运行”。

2.  在“运行”对话框中，键入“regedit”，然后按 Enter。

3.  在注册表编辑器中，依次展开“HKEY\_LOCAL\_MACHINE”、“SOFTWARE”、“Microsoft”和“Real-Time Communications”。

4.  右键单击“Health”，单击“新建”，然后单击“项”。如果“Health”项不存在，请右键单击“Real-Time Communications”，指向“新建”，然后单击“项”。创建新项时，请键入“Health”，然后按 Enter。
    
    创建新项之后，键入“CentralDiscoveryCandidate”，然后按 Enter 以重命名该项。

计算机可能要花费几个小时的时间来采用此更改。若要使更改立即生效，请停止并重新启动健康代理服务。若要重新启动健康代理服务，请在 Lync Server 2010 计算机上完成以下过程：

1.  依次单击“开始”、“所有程序”和“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

2.  在控制台窗口中键入以下命令，然后按 Enter：
    
        Net stop HealthService

3.  这将显示一条消息，此消息指示“系统中心管理服务正在停止”，紧接着会显示另一条消息，告知您该服务已停止。在该服务停止后，您可以通过键入以下命令并按 Enter 来重新启动它：
    
        Net start HealthService

## 覆盖 Lync Server 2010 管理包中的中央发现候选

在指示 Lync Server 2010 计算机报告 Lync Server 2010 计算机之后，您还需要告知 Lync Server 2010 管理包有关此更改的信息。为此，您需要在管理包中创建覆盖。可以通过完成以下过程执行此操作：

1.  在 Operations Manager 控制台中，单击“创作”。

2.  在“创作”选项卡上，展开“管理包对象”，单击“对象发现”，然后单击“范围”。

3.  在“划分管理包对象的范围”对话框中，选择带目标“LS 发现候选”的项目，然后单击“确定”。请注意，LS 发现候选仅在您安装 Lync Server 2010 管理包后显示。

4.  在 Operations Manager 控制台中，右键单击“LS 发现候选”，依次指向“替代”和“替代对象发现”，然后单击“对于类为 LS 发现候选的所有对象”。

5.  在“替代属性”对话框中，选中参数“Central Discovery WatcherNode Fqdn”旁边的“替代”复选框。在“替代值”和“有效值”框中键入 Lync Server 2010 计算机的完全限定域名。选中“强制”复选框并单击“确定”。

创建覆盖之后，您需要在根管理服务器上重新启动运行状况服务。若要重新启动运行状况服务，请在根管理服务器上完成以下过程：

1.  依次单击“开始”、“所有程序”和“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

2.  在控制台窗口中键入以下命令，然后按 Enter：
    
        Net stop HealthService

3.  这将显示一条消息，此消息指示“系统中心管理服务正在停止”，紧接着会显示另一条消息，告知您该服务已停止。在该服务停止后，您可通过键入以下命令并按 Enter 来重新启动它：
    
        Net start HealthService

## 确认已发现新的中央发现候选

升级中央管理存储之前的最后一步是，确保 Lync Server 2010 管理包发现了新的中央发现候选。为此，请打开 Operations Manager 控制台，然后单击“监控”。在“监控”选项卡上，展开“Microsoft Lync Server 2010 运行状况”，再展开“拓扑发现”，然后单击“发现状态视图”。确认显示中的行具有列出中央发现候选的完全限定域名的“路径”。您还应确认计算机状态已报告为“正常”。

