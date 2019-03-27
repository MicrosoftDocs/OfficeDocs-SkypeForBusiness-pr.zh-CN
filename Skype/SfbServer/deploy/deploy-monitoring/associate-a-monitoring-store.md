---
title: 将监控存储与 Skype 中的前端池相关联的业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 摘要： 了解如何将前端池与监控存储由 Skype 用于业务服务器相关联。
ms.openlocfilehash: 1156883202218dd536926f44f40e6ba774b17cb7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887142"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>将监控存储与 Skype 中的前端池相关联的业务服务器 
**摘要：** 了解如何将前端池与监控存储由 Skype 用于业务服务器相关联。
  
Skype 业务服务器，在监控数据可以仅收集已与监控存储，在拓扑生成器中定义前端池时通常执行的任务相关联的前端池上。
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>将监控存储与前端池关联

 要将监控存储与新的前端池关联，请确保在“定义新的前端池”向导的“**选择功能**”页上选择“**监控（用户体验质量度量的呼叫详细信息记录）**”选项。请注意，如果选择此选项，还必须指定一个 SQL 存储才能完成向导；但是，在运行向导时该存储不必存在。这意味着可以先将池与监控存储关联，然后再设置和配置该存储。
  
或者，可以通过完成以下过程将现有前端池与新的或不同的监控存储关联：
  
1. 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**Skype 的业务 Server 拓扑生成器**。
    
2. 在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。
    
3. 在“**另存为**”对话框中，为当前拓扑输入一个文件名，然后单击“**保存**”。如果新拓扑出现问题，可以取回并重新发布已保存的拓扑。
    
4. 在拓扑生成器中，依次展开**Skype 业务服务器**和包含前端池的站点的名称，然后单击扩展**Enterprise Edition 前端池**。
    
5. 右键单击要与监控存储关联的池的名称，然后单击“**编辑属性**”。
    
6. 在“**编辑属性**”对话框中的“**常规**”选项卡上，选择选项“**监控（CDR 和 QoE 度量）**”，然后从“**监控 SQL Server 存储**”下拉列表中选择现有 SQL Server 数据库。（或者，单击“**新建**”将池与新的数据库存储关联。）如果选择使用新的数据库存储，则在“**定义新的 SQL 存储**”对话框中输入“**Sql Server FQDN**”框中 SQL Server 计算机的完全限定域名。如果想要将默认 SQL Server 实例用于该存储，请选择“**默认实例**”；否则选择“**命名实例**”并在“**命名实例**”框中输入实例名称。
    
    通过“**编辑属性**”对话框还可以创建监控数据库的 SQL 镜像（通过一个 SQL 镜像可以维护两个监控数据库副本，一个副本存储在监控存储计算机上，另一个存储在 SQL 镜像计算机上）。 若要启用镜像，请选择 T**其 SQL 实例处于镜像关系**，为镜像服务器中**镜像端口号**框中输入的端口号。
    
7. 在“**编辑属性**”对话框中，单击“**确定**”。
    
将监控存储与前端池关联后，必须发布新拓扑才能使更改生效。 若要发布新拓扑，请完成拓扑生成器中的下列步骤：
  
1. 单击“**操作**”，指向“**拓扑**”，然后单击“**发布**”。
    
2. 在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。
    
3. 在“**发布向导完成**”页上，单击“**完成**”。
    
拓扑发布完毕后，可以在将要承载监控存储的计算机上安装监控数据库。 可以使用 Skype 的业务 Server 命令行管理程序和 Windows PowerShell 安装监控数据库。 安装本地数据库 (即，其中的业务 Server 命令行管理程序运行 Skype 同一台计算机上安装数据库)，在相应计算机上，启动命令行管理程序，然后键入以下命令并按 ENTER:
  
```
Install-CsDatabase -LocalDatabases
```

运行上述命令时，Install-csdatabase 将读取当前 Skype 企业服务器拓扑，确定哪些数据库需要在本地计算机上安装，然后自动安装和配置每个这些数据库。
  
要在远程计算机（即，没有运行命令行管理程序的计算机）上安装数据库，必须包含至少两个参数：ConfiguredDatabases 参数和 SqlServerFqdn 参数。 这些参数告知的 Install-csdatabase cmdlet 检索企业服务器拓扑的 Skype 然后安装和 SqlServerFqdn 参数指定的计算机上配置所需的数据库。 SqlServerFqdn 参数使用的参数值必须表示要安装数据库的计算机的完全限定域名。
  
例如，以下命令在计算机 atl-sql-001.litwareinc.com 上安装监控数据库：
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

此外，您可以通过将承载监控存储的计算机上运行 Business Server 部署向导 Skype 安装监控数据库。 为此，请登录到相应的计算机并完成以下过程：
  
1. 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**Skype 的业务 Server 部署向导**。
    
2. 在部署向导中，单击**安装或更新 Skype 业务 Server 系统**。
    
3. 在**部署**页中，在**步骤 2： 安装或删除业务服务器组件的 Skype**，**再次运行**单击。
    
4. 中安装 Skype Business Server 组件向导，在**业务服务器组件的安装程序 Skype**页上，单击**下一步**。
    
5. 在**指定 Msi 的路径**页上，键入文件 Ocscore.msi （包含您的业务 Server 安装介质的 Skype 文件） 的路径，然后单击**下一步**。
    
6. 在“**正在执行命令**”页上，单击“**完成**”。
    
若要确保已启动 Business Server 服务的所有必需的 Skype，单击**运行**标题下的**步骤 4： 启动服务****部署**页上
  

