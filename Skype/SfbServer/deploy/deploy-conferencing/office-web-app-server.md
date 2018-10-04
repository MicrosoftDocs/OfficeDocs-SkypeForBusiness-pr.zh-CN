---
title: 配置与 Skype 中的 Office Web Apps Server 的集成的企业服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要： 阅读本主题可了解如何配置 Office Web Apps Server 和 Skype 业务服务器启用 web 会议的 PowerPoint 演示文稿之间的集成。
ms.openlocfilehash: 6c7c19f7634c7b0266364d372b573d3d060d5a97
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375242"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>配置与 Skype 中的 Office Web Apps Server 的集成的企业服务器
 
**摘要：** 阅读本主题可了解如何配置 Office Web Apps Server 和 Skype 业务服务器启用 web 会议的 PowerPoint 演示文稿之间的集成。
  
Skype 业务服务器使用 Office Web Apps Server 处理的 web 会议的 PowerPoint 演示文稿。 有关此方法的优点的信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)。
  
您可以配置供业务服务器使用 Office Web Apps Server 的 Skype 之前，必须确保已部署和配置 Office Web Apps Server。 Office Web Apps Server 的信息，请参阅文章[部署基础结构： Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525)。 
  
已成功安装 Office Web Apps Server 和正确配置您的 Web 服务器场，必须然后配置业务服务器通过将 Office Web Apps 服务器发现 URL 添加到您的业务 Skype 与新的服务器进行通信的 Skype 后服务器拓扑。 
  
> [!NOTE]
> Office Web Apps Server 的最新小名为 Office Online Server，业务服务器支持的 Skype。 有关详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>配置业务服务器与 Office Web Apps Server 通信的 Skype

若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：
  
1. 业务 Server 拓扑生成器打开 Skype。
    
2. 在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。
    
3. 在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。
    
4. 在拓扑生成器中，依次展开“**Skype for Business Server**”、站点的名称和“**Enterprise Edition 前端池**”，右键单击某个池的名称，然后单击“**编辑属性**”。
    
5. 在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。
    
6. 在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。
    
   - 如果 Office Web Apps Server 内部安装并作为 Business Server 然后选项的 Skype 的同一个网络区域中**的外部网络 (即，外围 /internet) 中部署 Office Web Apps Server**没有被选中。
    
   - 如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。
    
7. 在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。Office Online 发现 URL 将作为池的关联之一列出。
    
您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。
  
向拓扑添加搜索 URL 后，必须发布更新的拓扑。若要在拓扑生成器中执行此操作：
  
1. 单击“**操作**”，然后单击“**发布拓扑**”。
    
2. 在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。
    
3. 在“**发布向导完成**”页上，单击“**完成**”。
    
4. 关闭拓扑生成器。
    
## <a name="configure-access-for-external-users"></a>配置外部用户访问

如果您希望外部用户 （即从组织防火墙外部登录的用户） 有权访问 Office Web Apps 服务器 PowerPoint 演示文稿，则需要使用 Office Web Apps Server 和反向代理服务器。 你还需要创建和配置网站发布规则，这有助于确保用户能连接到服务器。 
  
## <a name="validate-the-configuration"></a>验证配置

Office Web Apps Server 已添加到拓扑之后，发布该拓扑后，您应看到两个新的事件日志事件中为 Business Server 事件日志 Skype。 首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：
  
 **已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**
  
例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：
  
 **已成功发现 Web 会议服务器 Office Web Apps Server。**
  
 **Office Web Apps Server 内部演示者页面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; 嵌入 =**
  
 **Office Web Apps Server 内部与会者页面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; 嵌入 = true&amp;=**
  
如果已配置外部用户访问，您将看到类似于：
  
 **Office Web Apps Server 外部演示者页面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; 嵌入**
  
 **Office Web Apps Server 内部与会者页面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
如果您看到的 41033 事件 id，则意味着的 Office Web Apps Server 发现 LS Data MCU 事件已失败。 在这种情况下，Skype 业务服务器将发现新配置 Office Web Apps Server 所需的多次重试。 如果发现过程失败重复您应从拓扑文档中删除 Office Web Apps Server、 发布更新的拓扑，然后再尝试后已解决连接问题后向拓扑添加 Office Web Apps Server。
  
如果 Office Web Apps Server 出现正确配置，并且已被识别由发现过程，您可以验证 Office Web Apps Server 可以正常工作的共享 PowerPoint 演示文稿的 Skype 一对业务的客户端之间。 如果用户 A 可以加载和显示 PowerPoint 演示文稿并且用户 B 然后可以加入会议并查看演示文稿使用 Office Web Apps Server。
  
即使 Office Web Apps Server 出现正确配置，您无法可能收到错误消息"一些共享功能将因服务器连接问题而无法使用"当您尝试进行共享 PowerPoint 演示文稿。 如果您收到此错误消息应重新启动新的 Office Web Apps Server 相关联的前端服务器 （或服务器）。
  

