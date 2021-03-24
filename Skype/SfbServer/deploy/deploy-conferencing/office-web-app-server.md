---
title: 在 Skype for Business Server 中配置与 Office Web Apps Server 的集成
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
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要：阅读本主题，了解如何配置 Office Web Apps Server 和 Skype for Business Server 之间的集成，以启用用于 Web 会议的 PowerPoint 演示文稿。
ms.openlocfilehash: 24332154efacd0dac889bcad5b95379b28faf7a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103648"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>在 Skype for Business Server 中配置与 Office Web Apps Server 的集成
 
**摘要：** 阅读本主题，了解如何配置 Office Web Apps Server 和 Skype for Business Server 之间的集成，以启用用于 Web 会议的 PowerPoint 演示文稿。
  
Skype for Business Server 使用 Office Web Apps Server 处理用于 Web 会议的 PowerPoint 演示文稿。 有关此方法的优点的信息，请参阅在 Skype [for Business Server 中规划会议](../../plan-your-deployment/conferencing/conferencing.md)。
  
在将 Skype for Business Server 配置为使用 Office Web Apps Server 之前，必须确保已部署和配置 Office Web Apps Server。 有关 Office Web Apps Server 的信息，请参阅文章[部署基础结构：Office Online Server。](/webappsserver/deploy-the-infrastructure-office-web-apps-server) 
  
成功安装 Office Web Apps Server 并正确配置 Web 场后，必须通过将 Office Web Apps Server 发现 URL 添加到 Skype for Business Server 拓扑，将 Skype for Business Server 配置为与新服务器进行通信。 
  
> [!NOTE]
> Office Web Apps Server 的最新迭代名为 Office Online Server，受 Skype for Business Server 支持。 有关详细信息，请参阅 [Office Online Server 文档](/officeonlineserver/office-online-server)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>配置 Skype for Business Server 以与 Office Web Apps Server 通信

若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：
  
1. 打开 Skype for Business Server 拓扑生成器。
    
2. 在“拓扑生成器”对话框中，选择“从现有部署下载拓扑”，然后单击“确定”。
    
3. 在“将拓扑另存为”对话框的“文件名”框中为拓扑文档键入一个名称（例如，**PreWebAppsServerTopology**），然后单击“保存”。如果之后您的新拓扑遇到问题，则可检索和重新发布此拓扑。
    
4. 在拓扑生成器中，展开 **Skype for Business Server，** 展开站点名称，展开 Enterprise Edition **前端** 池，右键单击其中一个池的名称，然后单击编辑 **属性**。
    
5. 在“编辑属性”对话框的“常规”选项卡上，查找标题“关联 Office Web Apps 服务器”，然后单击“新建”（或从下拉列表中选择现有 Office Web Apps 服务器）。
    
6. 在“定义新的 Office Web Apps 服务器”对话框的“Office Web Apps 服务器 FQDN”框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”框中。
    
   - 如果 Office Web Apps 服务器是本地安装的，并且与 Skype for Business Server 位于同一网络区域中，则不应选择选项 Office Web Apps Server 部署在外部网络 (即，不应选择外围 **/Internet) 。**
    
   - 如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”。
    
7. 在“定义新的 Office Web Apps 服务器”对话框中，单击“确定”，然后在“编辑属性”对话框中单击“确定”。 然后，发现 URL 将列为池的关联之一。
    
您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。
  
将发现 URL 添加到拓扑后，必须发布更新的拓扑。 请在拓扑生成器中执行此操作：
  
1. 单击“操作”，然后单击“发布拓扑”。
    
2. 在发布拓扑向导的“发布拓扑”页上，单击“下一步”。
    
3. 在“发布向导已完成”页上，单击“完成”。
    
4. 关闭拓扑生成器。
    
## <a name="configure-access-for-external-users"></a>配置外部用户的访问权限

如果您希望外部用户 (即从组织防火墙) 外部登录的用户能够访问 Office Web Apps Server PowerPoint 演示文稿，则需要使用 Office Web Apps Server 和反向代理服务器。 您还需要创建和配置网站发布规则，这有助于确保用户能够连接到服务器。 
  
## <a name="validate-the-configuration"></a>验证配置

将 Office Web Apps Server 添加到拓扑中后，发布该拓扑后，您应该在 Skype for Business Server 事件日志中看到两个新的事件日志事件。 首先，应 (LS 数据 MCU 事件) ID 41034;此事件将报告已发现 Office Web Apps Server：
  
 **发现 Web 会议服务器 Office Web Apps Server，启用 PowerPoint 内容。**
  
例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：
  
 **已成功发现 Web 会议服务器 Office Web Apps Server。**
  
 **Office Web Apps Server 内部演示者页面 https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ：;embed=**
  
 **Office Web Apps Server 内部与会者页面 https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ：;embed=true&amp;=**
  
如果已配置外部用户的访问权限，还将看到类似以下内容：
  
 **Office Web Apps Server 外部演示者页面 https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ：;embed**
  
 **Office Web Apps Server 内部与会者页面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
如果您看到 LS Data MCU 事件，事件 ID 为 41033，则意味着 Office Web Apps Server 发现已失败。 在这种情况下，Skype for Business Server 将根据需要多次尝试发现新配置的 Office Web Apps Server。 如果发现过程反复失败，则应该从拓扑文档删除 Office Web Apps Server，发布更新的拓扑，然后在已解决连接性问题后尝试将 Office Web Apps Server 添加回到该拓扑。
  
如果 Office Web Apps Server 似乎配置正确并且已由发现过程识别，则可以通过在一对 Skype for Business 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps Server 是否按预期工作。 如果用户 A 可加载并显示 PowerPoint 演示文稿，然后如果用户 B 可以加入会议，并看到该演示文稿，则 Office Web Apps Server 正在工作。
  
即使 Office Web Apps Server 显示为配置正确，当您尝试共享 PowerPoint 演示文稿时，您也可能会收到错误消息"由于服务器连接问题，某些共享功能不可用"。 如果收到该错误消息，您应该重新启动与新 Office Web Apps Server 关联的前面服务器（或服务器）。
