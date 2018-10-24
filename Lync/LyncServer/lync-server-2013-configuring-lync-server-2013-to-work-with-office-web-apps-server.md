---
title: 将 Lync Server 2013 配置为使用 Office Web Apps 服务器
TOCTitle: 将 Lync Server 2013 配置为使用 Office Web Apps 服务器
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204944(v=OCS.15)
ms:contentKeyID: 49313031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 2013 配置为使用 Office Web Apps 服务器

 

_**上一次修改主题：** 2013-04-22_

必须先部署和配置 Office Web Apps 服务器，您才能将 Lync Server 2013 配置为使用 Office Web Apps 服务器。有关如何安装和配置单台 Office Web Apps 服务器的详细信息以及为了高可用性如何安装和配置 Office Web Apps 服务器场的信息，请参阅文档“Office Web Apps 服务器和 Office Web Apps 部署指南”。

成功安装 Office Web Apps 服务器并正确配置 Web 服务器场之后，您必须配置 Lync Server 才能与新服务器进行通信；此操作是通过向 Lync Server 拓扑中添加 Office Web Apps 服务器搜索 URL 来完成的。若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：

1.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 拓扑生成器”。

2.  在“拓扑生成器”对话框中，选择“从现有部署下载拓扑”，然后单击“确定”。

3.  在“将拓扑另存为”对话框的“文件名”框中为拓扑文档键入一个名称（例如，**PreWebAppsServerTopology**），然后单击“保存”。如果之后您的新拓扑遇到问题，则可检索和重新发布此拓扑。

4.  在拓扑生成器中，依次展开“Lync Server 2013”、站点的名称和“Enterprise Edition 前端池”，右键单击某个池的名称，然后单击“编辑属性”。

5.  在“编辑属性”对话框的“常规”选项卡上，查找标题“关联 Office Web Apps 服务器”，然后单击“新建”（或从下拉列表中选择现有 Office Web Apps 服务器）。

6.  在“定义新的 Office Web Apps 服务器”对话框的“Office Web Apps 服务器 FQDN”框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”框中。
    
    如果 Office Web Apps 服务器安装在本地并且与 Lync Server 2013 位于同一网络区域，则不应选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”。
    
    如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”。

7.  在“定义新的 Office Web Apps 服务器”对话框中，单击“确定”，然后在“编辑属性”对话框中单击“确定”。Office Web Apps 搜索 URL 将作为池的关联之一列出。

您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。

向拓扑添加搜索 URL 后，您必须发布此更新的拓扑。请在拓扑生成器中执行此操作：

1.  单击“操作”，然后单击“发布拓扑”。

2.  在发布拓扑向导的“发布拓扑”页上，单击“下一步”。

3.  在“发布向导已完成”页上，单击“完成”。

4.  关闭拓扑生成器。

