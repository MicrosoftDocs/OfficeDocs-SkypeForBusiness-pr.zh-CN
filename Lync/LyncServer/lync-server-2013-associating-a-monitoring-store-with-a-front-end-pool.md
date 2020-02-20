---
title: Lync Server 2013：将监控存储与前端池关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889179c5302a0ff8d59b5cf438c7ba0ab3c489f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>在 Lync Server 2013 中将监视存储与前端池关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-04-22_

在 Microsoft Lync Server 2013 中，只能在已与监控存储关联的前端池上收集监视数据，通常执行的任务是在拓扑生成器中定义一个前端池。 要将监控存储与新的前端池关联，请确保在“定义新的前端池”向导的“选择功能”**** 页上选择“监控（用户体验质量度量的呼叫详细信息记录）”**** 选项。 请注意，如果选择此选项，还必须指定一个 SQL 存储才能完成向导；但是，在运行向导时该存储不必存在。 这意味着可以先将池与监控存储关联，然后再设置和配置该存储。

或者，可以通过完成以下过程将现有前端池与新的或不同的监控存储关联：

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在“拓扑生成器”**** 对话框中，选择“从现有部署下载拓扑”****，然后单击“确定”****。

3.  在“另存为”**** 对话框中，为当前拓扑输入一个文件名，然后单击“保存”****。如果新拓扑出现问题，可以取回并重新发布已保存的拓扑。

4.  在拓扑生成器中，展开 " **Lync Server 2013**"，展开包含前端池的网站的名称，然后单击 "展开**Enterprise Edition 前端池**"。

5.  右键单击要与监控存储关联的池的名称，然后单击“编辑属性”****。

6.  在“编辑属性”**** 对话框中的“常规”**** 选项卡上，选择选项“监控（CDR 和 QoE 度量）”****，然后从“监控 SQL Server 存储”**** 下拉列表中选择现有 SQL Server 数据库。（或者，单击“新建”**** 将池与新的数据库存储关联。）如果选择使用新的数据库存储，则在“定义新的 SQL 存储”**** 对话框中输入“Sql Server FQDN”**** 框中 SQL Server 计算机的完全限定域名。如果想要将默认 SQL Server 实例用于该存储，请选择“默认实例”****；否则选择“命名实例”**** 并在“命名实例”**** 框中输入实例名称。
    
    通过“编辑属性”**** 对话框还可以创建监控数据库的 SQL 镜像（通过一个 SQL 镜像可以维护两个监控数据库副本，一个副本存储在监控存储计算机上，另一个存储在 SQL 镜像计算机上）。要启用镜像，请选择“此 SQL 实例处于镜像关系中”****，然后在“镜像端口号”**** 框中输入镜像服务器的端口号。

7.  在“编辑属性”**** 对话框中，单击“确定”****。

将监控存储与前端池关联后，必须发布新拓扑才能使更改生效。要发布新拓扑，请在拓扑生成器中完成以下步骤：

1.  单击“操作”****，指向“拓扑”****，然后单击“发布”****。

2.  在发布拓扑向导的“发布拓扑”**** 页上，单击“下一步”****。

3.  在“发布向导完成”**** 页上，单击“完成”****。

拓扑发布完毕后，可以在将要承载监控存储的计算机上安装监控数据库。 可以使用 Lync Server 命令行管理程序和 Windows PowerShell 安装监控数据库。 若要在本地安装数据库（即，在运行 Lync Server 命令行管理程序的同一台计算机上安装数据库），请在相应的计算机上启动命令行管理程序，然后键入以下命令，然后按 ENTER：

    Install-CsDatabase -LocalDatabases

运行上述命令时，CsDatabase 将读取当前的 Lync Server 拓扑，确定哪些数据库需要安装在本地计算机上，然后自动安装并配置每个数据库。

要在远程计算机（即，没有运行命令行管理程序的计算机）上安装数据库，必须包含至少两个参数：ConfiguredDatabases 参数和 SqlServerFqdn 参数。 这些参数告诉 CsDatabase cmdlet 检索 Lync Server 拓扑，然后在 SqlServerFqdn 参数所指定的计算机上安装和配置所需的数据库。 SqlServerFqdn 参数使用的参数值必须表示要安装数据库的计算机的完全限定域名。

例如，以下命令在计算机 atl-sql-001.litwareinc.com 上安装监控数据库：

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

或者，也可以通过在将承载监控存储的计算机上运行 Lync Server 部署向导来安装监控数据库。 为此，请登录到相应的计算机并完成以下过程：

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 部署向导**"。

2.  在部署向导中，单击“安装或更新 Lync Server 系统”****。

3.  在“部署”**** 页上的“步骤 2: 安装或删除 Lync Server 组件”**** 下，单击“再次运行”****。

4.  在安装 Lync Server 组件向导中的“设置 Lync Server 组件”**** 页上，单击“下一步”****。

5.  在 "**指定指向 MSIs 的路径**" 页上，键入文件 Ocscore 的路径（一个包含在 Lync Server 安装媒体中的文件），然后单击 "**下一步**"。

6.  在“正在执行命令”**** 页上，单击“完成”****。

若要确保已启动所有必需的 Lync Server 服务，请单击标题下的 "**步骤4：启动服务**" 下的 "**部署**" 页上的 "**运行**"

</div>

<span> </span>

</div>

</div>

</div>

