---
title: 部署试点边缘服务器
TOCTitle: 部署试点边缘服务器
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204682(v=OCS.15)
ms:contentKeyID: 49312045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署试点边缘服务器

 

_**上一次修改主题：** 2012-10-19_

本主题着重介绍在部署 Lync Server 2013边缘服务器之前应注意的配置设置。本节只着重介绍在部署试点边缘池的过程中应考虑的关键点。有关详细步骤，请参阅部署文档中的 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)，其中介绍了部署过程，并且还提供了有关外部用户访问的配置信息。

在“定义新的边缘池”向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”向导的部分页面。

**定义边缘池**

1.  使用拓扑生成器打开试点池拓扑。

2.  导航到 Lync Server 2013 节点。右键单击“边缘池”，然后单击“新建边缘池”。
    
    ![“定义新的边缘池”对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "“定义新的边缘池”对话框")

3.  边缘池可以是“多计算机池”，也可以是“单计算机池”。
    
    ![“定义边缘池 FQDN”对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "“定义边缘池 FQDN”对话框")

4.  在“选择功能”页上，不要启用联盟或 XMPP 联盟。联盟和 XMPP 联盟当前通过旧 Office Communications Server 2007 R2边缘服务器路由。将在迁移的稍后阶段中配置这些功能。
    
    ![“选择功能”对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "“选择功能”对话框")

5.  接下来，继续完成以下向导页：“选择 IP 选项”、“外部 FQDN”、“定义内部 IP 地址”和“定义外部 IP 地址”。

6.  在“定义下一跃点”页上，选择 Lync Server 2013 边缘池 的下一跃点的 控制器。
    
    ![“定义新边缘池”对话框 - 下一个跃点池列表](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "“定义新边缘池”对话框 - 下一个跃点池列表")

7.  在“关联前端池”页上，此时不要将池与此边缘池关联。当前通过旧 Office Communications Server 2007 R2边缘服务器路由外部媒体流量。将在迁移的稍后阶段中配置此设置。
    
    ![“定义新边缘池”对话框](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "“定义新边缘池”对话框")

8.  单击“完成”，然后单击“发布”以发布拓扑。

9.  按照部署文档中[安装适用于 Lync Server 2013 的边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤在新的边缘服务器上安装文件，配置证书并启动服务。

务必按照部署文档中的主题 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中的指南操作。本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。

现在应该与 Lync Server 2013 边缘服务器部署并行部署了 BackCompatSite 所指示的旧 Office Communications Server 2007 R2 边缘服务器。联盟配置为使用 Office Communications Server 2007 R2 Director。在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。

![显示 OCS 边缘服务器的拓扑生成器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "显示 OCS 边缘服务器的拓扑生成器")

