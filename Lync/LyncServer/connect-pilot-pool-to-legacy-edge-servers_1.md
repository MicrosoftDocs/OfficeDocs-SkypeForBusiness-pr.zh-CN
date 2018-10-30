---
title: 将试点池连接到旧边缘服务器
TOCTitle: 将试点池连接到旧边缘服务器
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205136(v=OCS.15)
ms:contentKeyID: 49313763
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将试点池连接到旧边缘服务器

 

_**上一次修改主题：** 2012-10-02_

部署 Lync Server 2013 后，没有配置此站点的联盟路由。为了使用 Office Communications Server 2007 R2 所用的联盟路由，必须将 Lync Server 2013 配置为使用此路由。

若要使 Lync Server 2013 站点能够使用 BackCompatSite 的控制器和边缘服务器，请使用拓扑生成器来关联旧式边缘池。

## 使用拓扑生成器关联旧的边缘池

1.  在拓扑生成器中打开试点池拓扑。

2.  选择 Lync Server 2013 站点。

3.  在“操作”菜单上，单击“编辑属性”。

4.  在“站点联盟路由分配”下，选择“启用 SIP 联盟”，然后选择 Office Communications Server 2007 R2 Director 或 Office Communications Server 2007 R2 边缘服务器（如果未列出 Director）。
    
    ![“编辑属性”对话框 -“联盟路由”页](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "“编辑属性”对话框 -“联盟路由”页")  

5.  单击“确定”关闭“编辑属性”页。

6.  在拓扑生成器中，在 Lync Server 2013 节点下，导航到“Standard Edition 服务器”或“Enterprise Edition 前端池”，右键单击该池，然后单击“编辑属性”。

7.  在“关联”下，选中“关联边缘池(用于媒体组件)”旁边的复选框。

8.  从列表中选择用于 BackCompatSite 的边缘服务器接口。
    
    ![“编辑属性”对话框 -“常规”页](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "“编辑属性”对话框 -“常规”页")  

9.  单击“确定”关闭“编辑属性”页。

10. 在“拓扑生成器”中，选择最顶层节点 **Lync Server**。

11. 从“操作”菜单中，单击“发布拓扑”，然后单击“下一步”。

12. “发布向导”完成时，单击“完成”。

