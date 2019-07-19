---
title: 在 Skype for Business Server 中配置与 Office Web Apps 服务器的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '摘要: 阅读本主题, 了解如何配置 Office Web Apps 服务器与 Skype for business 服务器之间的集成, 以启用适用于 Web 会议的 PowerPoint 演示文稿。'
ms.openlocfilehash: 7be69b24b2ae64763b1f9b0d324b812b60f69434
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793287"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>在 Skype for Business Server 中配置与 Office Web Apps 服务器的集成
 
**摘要:** 阅读本主题, 了解如何配置 Office Web Apps 服务器与 Skype for business 服务器之间的集成, 以启用适用于 Web 会议的 PowerPoint 演示文稿。
  
Skype for business 服务器使用 Office Web Apps 服务器处理适用于 Web 会议的 PowerPoint 演示文稿。 有关此方法的优势的信息, 请参阅[在 Skype For Business 服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)。
  
在将 Skype for business 服务器配置为使用 Office Web Apps 服务器之前, 必须确保已部署和配置 Office Web Apps 服务器。 有关 Office Web Apps 服务器的信息, 请参阅[部署基础结构的文章: Office Online server](https://go.microsoft.com/fwlink/p/?linkid=257525)。 
  
在成功安装 Office Web Apps 服务器并正确配置 Web 场后, 必须随后将 Office Web Apps 服务器发现 URL 添加到 Skype for business, 将 Skype for Business 服务器配置为与新服务器通信服务器拓扑。 
  
> [!NOTE]
> Office Web Apps 服务器的最新小版本称为 "Office Online Server", 该服务器受 Skype for Business 服务器支持。 有关更多详细信息, 请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>配置 Skype for Business 服务器以与 Office Web Apps 服务器通信

若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：
  
1. 打开 Skype for Business 服务器拓扑生成器。
    
2. 在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。
    
3. 在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。
    
4. 在拓扑生成器中，依次展开“**Skype for Business Server**”、站点的名称和“**Enterprise Edition 前端池**”，右键单击某个池的名称，然后单击“**编辑属性**”。
    
5. 在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。
    
6. 在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。
    
   - 如果 Office Web Apps 服务器在本地安装, 并且在与 Skype for Business 服务器相同的网络区域中安装, 则不应选择 " **Office Web apps" 服务器在外部网络 (即, 周边/Internet) 中部署**。
    
   - 如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。
    
7. 在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。 然后, 发现 URL 将列出为池的关联之一。
    
您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。
  
向拓扑添加搜索 URL 后，必须发布更新的拓扑。若要在拓扑生成器中执行此操作：
  
1. 单击“**操作**”，然后单击“**发布拓扑**”。
    
2. 在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。
    
3. 在“**发布向导完成**”页上，单击“**完成**”。
    
4. 关闭拓扑生成器。
    
## <a name="configure-access-for-external-users"></a>配置外部用户访问

如果你希望外部用户 (即从组织防火墙外部登录的用户) 有权访问 Office Web Apps Server PowerPoint 演示文稿, 则需要使用 Office Web Apps 服务器和反向代理服务器。 你还需要创建和配置网站发布规则，这有助于确保用户能连接到服务器。 
  
## <a name="validate-the-configuration"></a>验证配置

在将 Office Web Apps 服务器添加到拓扑后, 在该拓扑发布后, 你应该会在 Skype for Business 服务器事件日志中看到两个新的事件日志事件。 首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：
  
 **已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**
  
例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：
  
 **已成功发现 Web 会议服务器 Office Web Apps Server。**
  
 **Office Web Apps 服务器内部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; 嵌入 =**
  
 **Office Web Apps 服务器内部与会者页面: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; 嵌入 = true&amp;=**
  
如果你已为外部用户配置访问权限, 你还会看到类似于以下内容的内容:
  
 **Office Web Apps 服务器外部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; 嵌入**
  
 **Office Web Apps 服务器内部与会者页面: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
如果看到的 LS 数据 MCU 事件的事件 ID 为 41033, 表示 Office Web Apps 服务器发现失败。 在这种情况下, Skype for Business 服务器将根据需要尝试多次, 以发现新配置的 Office Web Apps 服务器。 如果发现过程重复失败, 则应从拓扑文档中删除 Office Web Apps 服务器, 发布更新后的拓扑, 然后尝试在连接问题解决后将 Office Web App 服务器重新添加到拓扑。
  
如果 Office Web Apps 服务器似乎配置正确且已被发现过程识别, 则可以通过在一对 Skype for Business 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps 服务器是否按预期工作。 如果用户 A 可以加载和显示 PowerPoint 演示文稿, 并且如果用户 B 可以加入会议并查看该演示文稿, 则 Office Web Apps 服务器正在工作。
  
即使 Office Web Apps 服务器显示正确配置, 您也可能会收到错误消息 "当你尝试共享 PowerPoint 演示文稿时, 由于服务器连接问题, 某些共享功能不可用"。 如果您收到该错误消息, 则应重新启动与新的 Office Web Apps 服务器相关联的前端服务器 (或服务器)。
  

