---
title: 在 Skype for Business Server 中配置与 Office Web Apps Server 的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要：阅读本主题，了解如何配置 Office Web Apps Server 和 Skype for Business Server 之间的集成，以启用适用于 Web 会议的 PowerPoint 演示文稿。
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983917"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>在 Skype for Business Server 中配置与 Office Web Apps Server 的集成
 
**摘要：** 阅读本主题，了解如何配置 Office Web Apps Server 和 Skype for Business Server 之间的集成，以启用适用于 Web 会议的 PowerPoint 演示文稿。
  
Skype for Business Server 使用 Office Web Apps Server 来处理适用于 Web 会议的 PowerPoint 演示文稿。 有关此方法的优势的信息，请参阅[在 Skype For Business Server 中规划会议](../../plan-your-deployment/conferencing/conferencing.md)。
  
在将 Skype for Business Server 配置为使用 Office Web Apps Server 之前，必须确保已部署并配置 Office Web Apps server。 有关 Office Web Apps Server 的信息，请参阅[部署基础结构： Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525)一文。 
  
在成功安装 Office Web Apps Server 并正确配置 Web 场之后，必须将 Office Web Apps Server 发现 URL 添加到 Skype for Business，然后再将 Skype for Business Server 配置为与新服务器通信服务器拓扑。 
  
> [!NOTE]
> Office Web Apps Server 的最新小版本命名为 Office Online Server，这是由 Skype for Business Server 支持的。 有关更多详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>将 Skype for Business Server 配置为与 Office Web Apps Server 进行通信

若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：
  
1. 打开 Skype for Business Server 拓扑生成器。
    
2. 在“拓扑生成器”**** 对话框中，选择“从现有部署下载拓扑”****，然后单击“确定”****。
    
3. 在“将拓扑另存为”**** 对话框的“文件名”**** 框中为拓扑文档键入一个名称（例如，**PreWebAppsServerTopology**），然后单击“保存”****。如果之后您的新拓扑遇到问题，则可检索和重新发布此拓扑。
    
4. 在拓扑生成器中，展开 " **Skype For Business Server**"，展开您的网站的名称，再展开 " **Enterprise Edition 前端池**"，右键单击其中一个池的名称，然后单击 "**编辑属性**"。
    
5. 在“编辑属性”**** 对话框的“常规”**** 选项卡上，查找标题“关联 Office Web Apps 服务器”****，然后单击“新建”****（或从下拉列表中选择现有 Office Web Apps 服务器）。
    
6. 在“定义新的 Office Web Apps 服务器”**** 对话框的“Office Web Apps 服务器 FQDN”**** 框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”**** 框中。
    
   - 如果 Office Web Apps Server 在本地和 Skype for business Server 所在的网络区域中安装，则不应选择在**外部网络（即外围/Internet）中部署 "Office Web Apps 服务器**" 选项。
    
   - 如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”****。
    
7. 在“定义新的 Office Web Apps 服务器”**** 对话框中，单击“确定”****，然后在“编辑属性”**** 对话框中单击“确定”****。 然后，发现 URL 将作为池的关联之一列出。
    
您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。
  
将发现 URL 添加到拓扑之后，必须发布更新后的拓扑。 请在拓扑生成器中执行此操作：
  
1. 单击“操作”****，然后单击“发布拓扑”****。
    
2. 在发布拓扑向导的“发布拓扑”**** 页上，单击“下一步”****。
    
3. 在“发布向导已完成”**** 页上，单击“完成”****。
    
4. 关闭拓扑生成器。
    
## <a name="configure-access-for-external-users"></a>为外部用户配置访问权限

如果您希望外部用户（即从组织防火墙外部登录的用户）能够访问 Office Web Apps Server PowerPoint 演示文稿，则需要使用 Office Web Apps Server 和反向代理服务器。 您还需要创建和配置网站发布规则，这将有助于确保用户能够连接到服务器。 
  
## <a name="validate-the-configuration"></a>验证配置

将 Office Web Apps Server 添加到拓扑，并在该拓扑发布之后，您应该会在 Skype for Business Server 事件日志中看到两个新的事件日志事件。 首先，应添加 LS 数据 MCU 事件（事件 ID 41034）;此事件将报告已发现 Office Web Apps Server：
  
 **已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**
  
例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：
  
 **Web 会议服务器 Office Web Apps Server 发现已成功。**
  
 **Office Web Apps Server 内部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp：; 嵌入 =**
  
 **Office Web Apps Server 内部与会者页面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**
  
如果已为外部用户配置访问权限，则还会看到类似于以下内容的内容：
  
 **Office Web Apps Server 外部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp：; 嵌入**
  
 **Office Web Apps Server 内部与会者页面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
如果您看到 LS Data MCU 事件，事件 ID 为 41033，则意味着 Office Web Apps Server 发现已失败。 在这种情况下，Skype for Business Server 会根据需要尝试多次，以发现新配置的 Office Web Apps 服务器。 如果发现过程反复失败，则应该从拓扑文档删除 Office Web Apps Server，发布更新的拓扑，然后在已解决连接性问题后尝试将 Office Web Apps Server 添加回到该拓扑。
  
如果 Office Web Apps Server 看起来已正确配置且已被发现过程识别，则可以通过在一对 Skype for Business 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps Server 是否按预期方式工作。 如果用户 A 可加载并显示 PowerPoint 演示文稿，然后如果用户 B 可以加入会议，并看到该演示文稿，则 Office Web Apps Server 正在工作。
  
即使 Office Web Apps Server 显示正确配置，在尝试共享 PowerPoint 演示文稿时，也可能会收到错误消息 "某些共享功能因服务器连接问题而不可用"。 如果收到该错误消息，您应该重新启动与新 Office Web Apps Server 关联的前面服务器（或服务器）。
  

