---
title: Skype for Business Server 2015 的 CLS 日志记录程序
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 摘要：了解如何在 2015 年 10 月 (CLS) 日志记录Skype for Business Server日志记录服务。
ms.openlocfilehash: 38cc7007476fbdfa6a02cf4d244fa0173e958d6bfe055d042be8ba4cf2d049e4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317487"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的 CLS 日志记录程序
 
**摘要：** 了解如何在 2015 年 (集中日志记录服务) CLS Skype for Business Server记录器。
  
CLS 日志记录器是一种可帮助您管理由集中日志记录服务生成的日志的工具。
  
## <a name="prerequisites"></a>先决条件

若要成功使用 CLS 记录器，需要确保以下各项为真：
  
- 在作为运行集中日志记录服务 (CLS) 的成员的计算机上使用此工具。 远程 PowerShell 会话中当前不支持该工具。
    
- 跟踪文件夹中的 Default.tmx 文件 (捕获 CLS) 和 Snooper 的跟踪数据的文件夹必须复制到安装 CLS 记录器工具的同一文件夹中。
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>检查一组池/计算机的日志记录状态

使用以下命令检查日志记录状态：
  
1. 在"开始/停止方案"选项卡中，选择拓扑树视图中的池和/或计算机的分组。
    
2. 单击"日志记录状态"按钮。
    
3. 查看 PowerShell 命令输出区域中的命令输出，了解有关所选池和/或计算机的日志记录状态的具体信息。
    
## <a name="start-an-existing-scenario"></a>启动现有方案

启动现有方案：
  
1. 在"开始/停止方案"选项卡中，从"方案"下拉菜单中选择现有方案。
    
2. 在拓扑树视图中选择池和/或计算机的分组。
    
3. 单击"开始方案"按钮。 用户界面将被禁用，直到操作完成。 在大型部署中，这可能会很慢。
    
4. 成功启动方案后，用户界面将再次启用，操作的详细信息还将显示在 PowerShell 命令输出区域中。
    
5. 此任务可能需要一些时间，CLS 才能在此方案中的任何新数据之前选取日志记录。
    
## <a name="stop-an-existing-scenario"></a>停止现有方案

若要停止现有方案：：
  
1. 在"开始/停止方案"选项卡中，从"方案"下拉菜单中选择现有方案。
    
2. 在拓扑树视图中选择池和/或计算机的分组。
    
3. 单击"停止方案"按钮。 用户界面将被禁用，直到操作完成。 在大型部署中，这可能会很慢。
    
4. 一旦方案停止，用户界面将再次启用，操作的详细信息还将显示在 PowerShell 命令输出区域中。
    
![CLS 日志记录器启动和停止](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>搜索日志

若要搜索日志，请选择"搜索 CLS 日志"选项卡，在填写显示字段后单击"搜索日志"按钮，如下所述：
  
> **日志文件文件夹** 用于保存日志搜索结果的文件夹。  (必需) 
> 
> **日志级别** 这将确定将在结果中显示的最低级别。 例如，如果选择了"警告"，则只显示"警告"、"错误"和"严重"。 默认为"调试"。
> 
> **池** 要执行日志搜索的计算机池，这些是树视图的父节点。  (必需) 
> 
> **计算机** 要执行日志搜索的单个计算机，这些节点都是树视图中的子节点。  (必需) 
> 
> **开始时间** CLS 查询日志的时间段。  (必需) 
> 
> **结束时间** CLS 停止查询日志的时间段。  (必需) 
> 
> **组件** 用于选择要添加到查询的组件。 （可选）
> 
> **呼叫 ID** 要筛选的任何 SIP 对话框的呼叫 ID。 请注意，此字段使用精确匹配。 （可选）
> 
> **会议 ID** 要作为筛选条件的任何会议的会议 ID。 请注意，此字段使用精确匹配。 （可选）
> 
> **IP 地址** 要筛选的 IP 地址。 请注意，此字段使用精确匹配。 （可选）
> 
> **相关 ID** 通过此 ID 在逻辑上链接在一起的跟踪语句。 （可选）
> 
> **电话 Number** 按电话号码筛选。 （可选）
> 
> **SIP URI** 按 SIP URI 进行筛选。 （可选）
> 
> **SIP 消息内容包含** 按 SIP 消息内容进行筛选，这将在此字段中对搜索进行子字符串处理。 （可选）
> 
> **匹配任意** 使用逻辑 OR 进行搜索（如果选中）。 默认为完全匹配所有参数。
> 
> **跳过网络日志** 如果选中，则跳过搜索任何网络日志。
    
![CLS 记录器搜索日志](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>创建方案

1. 在" **编辑方案"** 选项卡中，单击" **创建方案"** 按钮。
    
    > [!NOTE]
    > 创建新方案将克隆当前所选方案的配置。 如果在创建新方案 **设置** 之前单击"清除项目"，它将在未选择组件和标志的情况下开始。
  
2. 输入要创建的方案的名称，然后按 Enter 键或单击"确定"按钮。
    
3. 现在将创建新方案。 成功创建方案后，将对新创建的方案选择"方案"下拉列表。
    
## <a name="modify-a-scenario"></a>修改方案

![CLS 记录器屏幕截图、编辑方案](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. 在 **"编辑方案"** 选项卡中，找到要修改的所需方案。
    
2. 对组件、级别和标志进行所需的更改。
    
3. 单击" **保存方案"** 按钮。
    
4. 成功保存方案后，它将使用更新的配置刷新方案信息窗格。
    
## <a name="delete-a-scenario"></a>删除方案

1. 在" **编辑方案"** 选项卡中，从"方案"下拉菜单中选择现有方案。
    
2. 单击 **"删除** 方案"以删除方案。
    
3. 确认操作后，方案将被删除。
    

