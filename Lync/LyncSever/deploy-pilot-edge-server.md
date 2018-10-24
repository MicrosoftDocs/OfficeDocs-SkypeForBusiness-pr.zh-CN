---
title: 部署试点边缘服务器
TOCTitle: 部署试点边缘服务器
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205306(v=OCS.15)
ms:contentKeyID: 49314435
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署试点边缘服务器

 

_**上一次修改主题：** 2012-10-19_

本主题着重介绍在部署 Lync Server 2013  边缘服务器之前应了解的配置设置。 Lync Server 2013的部署和配置过程与 Lync Server 2010 类似。本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。有关详细步骤，请参阅部署文档中的 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)，其介绍部署过程并为外部用户访问提供了配置信息。

在“定义新的边缘池”向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”向导的部分页面。

**定义边缘池**

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  导航到 Lync Server 2013 节点。右键单击“边缘池”，然后单击“新建边缘池”。
    
    ![“定义新的边缘池”对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "“定义新的边缘池”对话框")

3.  边缘池可以是“多计算机池”，也可以是“单计算机池”。
    
    ![“定义边缘池 FQDN”对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "“定义边缘池 FQDN”对话框")

4.  在“选择功能”页上，不要启用联盟或 XMPP 联盟。当前通过旧 Lync Server 2010边缘服务器路由联盟和 XMPP 联盟。这些功能将在迁移的稍后阶段中配置。
    
    ![“选择功能”对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "“选择功能”对话框")

5.  接下来，继续完成以下向导页：“外部 FQDN”、“定义内部 IP 地址”和“定义外部 IP 地址”。

6.  在“定义下一跃点”页上，选择 Lync Server 2010边缘池的下一跃点的控制器。
    
    ![“定义下一跃点”对话框](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "“定义下一跃点”对话框")

7.  在“关联前端池或中介池”页上，此时不要将池与此 边缘池关联。当前通过旧 Lync Server 2010边缘服务器路由外部媒体流量。将在迁移的稍后阶段中配置此设置。
    
    ![“关联前端池”对话框](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "“关联前端池”对话框")

8.  单击“完成”，然后 **发布** 拓扑。

9.  按照部署文档中的 [安装适用于 Lync Server 2013 的边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤在新的 边缘服务器上安装文件，配置证书并启动服务。

务必按照部署文档中的主题 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中的指南操作。本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。

您现在应具有与 Lync Server 2013 边缘服务器部署并行部署的旧 Lync Server 2010 边缘服务器。在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。

