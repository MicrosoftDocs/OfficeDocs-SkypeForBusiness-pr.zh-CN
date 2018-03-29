---
title: 在 Skype for Business Server 2015 中配置与 Office Web Apps Server 的集成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要： 请阅读本主题，以了解如何配置以启用 web 会议的 PowerPoint 演示文稿的 Office Web 应用程序服务器和业务服务器 2015年的 Skype 之间的集成。
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置与 Office Web Apps Server 的集成
 
**摘要：**阅读本主题，以了解如何配置以启用 web 会议的 PowerPoint 演示文稿的 Office Web 应用程序服务器和业务服务器 2015年的 Skype 之间的集成。
  
Skype 业务服务器使用 Office Web 应用程序服务器，以处理 web 会议的 PowerPoint 演示文稿。 有关此方法的优点的信息，请参阅[规划业务服务器 2015年的 Skype 在会议](../../plan-your-deployment/conferencing/conferencing.md)。
  
可以配置 Skype 业务服务器使用 Office Web 应用程序服务器之前，必须确保已部署和配置 Office Web 应用程序服务器。 Office Web 应用程序服务器的信息，请参阅文章[部署基础结构： Office 联机服务器](https://go.microsoft.com/fwlink/p/?linkid=257525)。 
  
Office Web 应用程序服务器已成功安装并正确配置您的 Web 服务器场，必须再配置业务服务器与新服务器通信的将 Office Web 应用程序服务器搜索 URL 添加到您的业务的 Skype 的 Skype 后服务器拓扑结构。 
  
> [!NOTE]
> Office Web 应用程序服务器的最新小版本名为 Office 联机服务器，它受业务服务器 2015 Skype。 有关详细信息，请参阅[Office 联机服务器的文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Skype 与 Office Web 应用程序服务器进行通信的业务服务器的配置

若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：
  
1.  打开 Skype 业务服务器拓扑生成器。
    
2. 在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。
    
3. 在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。
    
4. 在拓扑生成器中，依次展开“**Skype for Business Server**”、站点的名称和“**Enterprise Edition 前端池**”，右键单击某个池的名称，然后单击“**编辑属性**”。
    
5. 在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。
    
6. 在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。
    
  - 如果 Office Web 应用程序服务器是内部部署安装和 Skype 业务服务器然后选择相同的网络分区**Office Web 应用程序服务器被部署在外部网络 (也就是说，外围/Internet)**应该不会选择。
    
  - 如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。
    
7. 在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。Office Online 发现 URL 将作为池的关联之一列出。
    
您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。
  
向拓扑添加搜索 URL 后，必须发布更新的拓扑。若要在拓扑生成器中执行此操作：
  
1. 单击“**操作**”，然后单击“**发布拓扑**”。
    
2. 在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。
    
3. 在“**发布向导完成**”页上，单击“**完成**”。
    
4. 关闭拓扑生成器。
    
## <a name="configure-access-for-external-users"></a>配置外部用户访问

如果您希望为外部用户 （即，从登录您所在组织的防火墙之外） 有权访问 Office Web 应用程序服务器 PowerPoint 演示文稿，则需要使用 Office Web 应用程序服务器和反向代理服务器。 你还需要创建和配置网站发布规则，这有助于确保用户能连接到服务器。 
  
## <a name="validate-the-configuration"></a>验证配置

Office Web 应用程序服务器添加到拓扑结构中之后和在发布该拓扑结构之后，您应该看到两个新 Skype 业务服务器事件日志中的事件日志事件。 首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：
  
 **已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**
  
例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：
  
 **已成功发现 Web 会议服务器 Office Web Apps Server。**
  
 **Office 应用程序的 Web 服务器内部演示者网页： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;嵌入 =**
  
 **Office 应用程序的 Web 服务器内部与会者网页： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;嵌入 = true&amp;=**
  
如果配置了外部用户访问，你还将看到类似下面的内容：
  
 **Office Web 应用程序服务器外部演示者网页： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;嵌入**
  
 **Office 应用程序的 Web 服务器内部与会者网页： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;嵌入 = true&amp;**
  
如果出现事件 id 为 41033，则意味着该 Office Web 应用程序服务器发现 LS 数据 MCU 事件失败。 在这种情况下，Skype 业务服务器将尝试发现新配置 Office Web 应用程序服务器所需的次数。 如果发现过程反复失败应从拓扑文档中删除 Office Web 应用程序服务器、 发布更新的拓扑，然后尝试连接问题都已解决之后返回到拓扑结构中添加 Office Web 应用程序服务器。
  
如果 Office Web 应用程序服务器看起来正确配置并且已经识别了发现过程可以验证 Office Web 应用程序服务器工作所需的共享一对 Skype 业务客户端之间的 PowerPoint 演示文稿。 如果用户 A 可以加载并显示 PowerPoint 演示文稿，并且用户 B 可以加入会议并观看该演示文稿时使用 Office Web 应用程序服务器。
  
即使 Office Web 应用程序服务器看起来正确配置，您可能有可能收到错误消息"一些共享功能是由于服务器连接问题而不可用"当您尝试共享的 PowerPoint 演示文稿。 如果您收到此错误消息，您应该重新启动与新的 Office Web 应用程序服务器前端服务器 （或服务器）。
  

