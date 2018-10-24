---
title: 创建或修改网络区域路由
TOCTitle: 创建或修改网络区域路由
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521016(v=OCS.15)
ms:contentKeyID: 49313286
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改网络区域路由

 

_**上一次修改主题：** 2012-10-08_

呼叫允许控制 (CAC) 配置中的每个区域必须具有访问其他每个区域的方式。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。您可以使用 Lync Server 控制面板配置网络区域路由。在 Lync Server 控制面板中，可以创建、修改或删除网络区域路由。使用本主题创建或修改网络区域路由。有关删除现有网络区域路由的详细信息，请参阅[删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)。

## 创建网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域路由”。

4.  在“区域路由”页上，单击“新建”。

5.  在“新建区域路由”的“名称”字段中键入值。
    
    > [!NOTE]  
    > 该值必须在 Microsoft Lync Server 2013 部署中是唯一的。
    


6.  从“网络区域 \#1”下拉列表中，选择要通过此路由进行连接的两个区域之一。

7.  从“网络区域 \#2”下拉列表中，选择此路由对应的另一个区域。此区域必须不同于为“网络区域 \#1”所选的区域。

8.  使用“网络区域链接”列表框向路由添加区域链接。单击“添加”按钮以显示“区域链接”页面。单击某个区域链接将其添加到此路由，然后单击“确定”。
    
    > [!NOTE]  
    > 继续单击“添加”按钮添加更多链接，还可选择某个链接，然后单击“删除”删除该链接。
    


9.  单击“提交”。

## 修改网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域路由”。

4.  在“区域路由”页上，单击要修改的区域路由。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑区域路由”中，可以修改此路由连接的区域以及与此路由关联的区域链接。

7.  单击“提交”。

## 另请参阅

#### 任务

[删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)

