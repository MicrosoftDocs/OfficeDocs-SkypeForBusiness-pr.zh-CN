---
title: 将监控存储与池中的前端池Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 摘要：了解如何将前端池与前端池使用的监控Skype for Business Server。
ms.openlocfilehash: 92713d8b6940011c97507a7138e05e80e1d119b302f9f58843b90bb9861005e9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307793"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>将监控存储与池中的前端池Skype for Business Server 
**摘要：** 了解如何将前端池与前端池使用的监控Skype for Business Server。
  
在Skype for Business Server中，只能在与监控存储关联的前端池上收集监控数据，此任务通常在拓扑生成器中定义前端池时执行。
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>将监控存储与前端池关联

 要将监控存储与新的前端池关联，请确保在“定义新的前端池”向导的“选择功能”页上选择“监控（用户体验质量度量的呼叫详细信息记录）”选项。 请注意，如果选择此选项，还必须指定一个 SQL 存储才能完成向导；但是，在运行向导时该存储不必存在。 这意味着可以先将池与监控存储关联，然后再设置和配置该存储。
  
或者，可以通过完成以下过程将现有前端池与新的或不同的监控存储关联：
  
1. 单击 **"开始**"，单击"所有程序"，Skype for Business Server **2015"，** 然后单击"Skype for Business Server **拓扑生成器"。** 
    
2. 在“拓扑生成器”对话框中，选择“从现有部署下载拓扑”，然后单击“确定”。
    
3. 在“另存为”对话框中，为当前拓扑输入一个文件名，然后单击“保存”。如果新拓扑出现问题，可以取回并重新发布已保存的拓扑。
    
4. 在拓扑生成器中，**展开**"Skype for Business Server"，展开包含前端池的站点的名称，然后单击"Enterprise Edition **前端池"。**
    
5. 右键单击要与监控存储关联的池的名称，然后单击“编辑属性”。
    
6. 在“编辑属性”对话框中的“常规”选项卡上，选择选项“监控（CDR 和 QoE 度量）”，然后从“监控 SQL Server 存储”下拉列表中选择现有 SQL Server 数据库。（或者，单击“新建”将池与新的数据库存储关联。）如果选择使用新的数据库存储，则在“定义新的 SQL 存储”对话框中输入“Sql Server FQDN”框中 SQL Server 计算机的完全限定域名。如果想要将默认 SQL Server 实例用于该存储，请选择“默认实例”；否则选择“命名实例”并在“命名实例”框中输入实例名称。
    
    通过“编辑属性”对话框还可以创建监控数据库的 SQL 镜像（通过一个 SQL 镜像可以维护两个监控数据库副本，一个副本存储在监控存储计算机上，另一个存储在 SQL 镜像计算机上）。 若要启用镜像，**请选择其SQL** 实例为镜像关系，在"镜像端口号"框中输入 **镜像服务器的端口** 号。
    
7. 在“编辑属性”对话框中，单击“确定”。
    
将监控存储与前端池关联后，必须发布新拓扑才能使更改生效。要发布新拓扑，请在拓扑生成器中完成以下步骤：
  
1. 单击“操作”，指向“拓扑”，然后单击“发布”。
    
2. 在发布拓扑向导的“发布拓扑”页上，单击“下一步”。
    
3. 在“发布向导完成”页上，单击“完成”。
    
拓扑发布完毕后，可以在将要承载监控存储的计算机上安装监控数据库。 可以使用命令行管理程序和命令行管理程序Skype for Business Server监控Windows PowerShell。 若要在本地安装数据库 (即，若要在运行 Skype for Business Server 命令行管理程序) 的同一计算机上安装数据库，请在相应的计算机上启动命令行管理程序，然后键入以下命令并按 Enter：
  
```powershell
Install-CsDatabase -LocalDatabases
```

运行上述命令时，Install-CsDatabase将读取当前的 Skype for Business Server 拓扑，确定哪些数据库需要安装在本地计算机上，然后自动安装和配置其中每个数据库。
  
要在远程计算机（即，没有运行命令行管理程序的计算机）上安装数据库，必须包含至少两个参数：ConfiguredDatabases 参数和 SqlServerFqdn 参数。 这些参数Install-CsDatabase cmdlet 检索 Skype for Business Server 拓扑，然后在 SqlServerFqdn 参数指定的计算机上安装和配置所需的数据库。 SqlServerFqdn 参数使用的参数值必须表示要安装数据库的计算机的完全限定域名。
  
例如，以下命令在计算机 atl-sql-001.litwareinc.com 上安装监控数据库：
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

或者，您可以通过在将承载监控存储的计算机上运行 Skype for Business Server 部署向导来安装监控数据库。 为此，请登录到相应的计算机并完成以下过程：
  
1. 单击 **"开始**"，单击 **"所有程序**"，Skype for Business Server **2015"，** 然后单击"Skype for Business Server **部署向导"。**
    
2. 在部署向导中，单击 **"安装或更新Skype for Business Server系统"。**
    
3. 在"**部署"** 页上的"**步骤 2： 安装或删除Skype for Business Server组件"下**，单击"**再次运行"。**
    
4. 在"安装程序Skype for Business Server组件"向导的"安装程序 **Skype for Business Server组件"** 页上，单击"下一 **步"。**
    
5. 在"**指定 MSIs** 的路径"页上，键入文件的路径Ocscore.msi (Skype for Business Server安装媒体中包含的文件) 然后单击"下一步 **"。**
    
6. 在“正在执行命令”页上，单击“完成”。
    
若要确保所有必需的服务Skype for Business Server，请单击"部署"页上标题"步骤 **4： 启动** 服务"下的"**运行**"
  

