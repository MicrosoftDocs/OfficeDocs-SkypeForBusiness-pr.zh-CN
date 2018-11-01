---
title: 将试点池连接到旧边缘服务器
TOCTitle: 将试点池连接到旧边缘服务器
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49888598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将试点池连接到旧边缘服务器

 

_**上一次修改主题：** 2012-09-29_

部署 Lync Server 2013 之后，您需要为您的站点配置联盟路由。要使用 Lync Server 2010 所使用的联盟路由，必须将 Lync Server 2013 配置为使用此路由。

要允许 Lync Server 2013 站点使用 Lync Server 2010 部署的 Director 和边缘服务器，请使用拓扑生成器来关联旧的边缘池。

## 使用拓扑生成器关联旧的边缘池

1.  打开“拓扑生成器”。

2.  选择位于 **Lync Server** 节点正下方的站点。

3.  在“操作”菜单上，单击“编辑属性”。

4.  在左侧窗格中，选择“联盟路由”。

5.  在“站点联盟路由分配”下，选择“启用 SIP 联盟”，然后选择 Lync Server 2010 Director 或 Lync Server 2010 边缘服务器（如果未列出 Director）。
    
    ![编辑属性 -“联盟路由”页](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "编辑属性 -“联盟路由”页")  

6.  单击“确定”关闭“编辑属性”页。

7.  在拓扑生成器中，在 Lync Server 2013 节点下，导航到“Standard Edition 服务器”或“Enterprise Edition 前端池”，右键单击该池，然后单击“编辑属性”。

8.  在“关联”下，选中“关联边缘池(用于媒体组件)”旁边的复选框。

9.  从列表中选择旧的边缘服务器。
    
    ![“编辑属性”对话框 - 选择旧边缘](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "“编辑属性”对话框 - 选择旧边缘")  

10. 单击“确定”关闭“编辑属性”页。

11. 在“拓扑生成器”中，选择最顶层节点 **Lync Server**。

12. 从“操作”菜单中，单击“发布拓扑”，然后单击“下一步”。

13. “发布向导”完成时，单击“完成”。

