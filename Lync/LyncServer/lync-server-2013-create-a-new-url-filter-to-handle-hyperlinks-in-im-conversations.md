---
title: 创建新 URL 筛选器以处理 IM 对话中的超链接
TOCTitle: 创建新 URL 筛选器以处理 IM 对话中的超链接
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182590(v=OCS.15)
ms:contentKeyID: 49314314
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建新 URL 筛选器以处理 IM 对话中的超链接

 

_**上一次修改主题：** 2012-09-26_

除了修改全局 URL 筛选器之外，还可以为 Lync Server 2013 部署中的各个站点配置自定义 URL 筛选器。有关 URL 筛选的详细信息，请参阅[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

## 创建新的 URL 筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“IM 和状态”，然后单击“URL 筛选器”。

4.  在“URL 筛选器”页上，单击“新建”。

5.  在“选择站点”中，单击要为其创建 URL 筛选器的站点，然后单击“确定”。

6.  在“新建 URL 筛选器”对话框中，选中“启用 URL 筛选器”复选框以启用站点的 URL 筛选。

7.  要阻止包含具有“编辑文件筛选器”中“要阻止的文件类型扩展名”下所列扩展名的文件的任何活动 URL，请选中“阻止带文件扩展名的 URL”复选框。

8.  在“超链接前缀”下拉列表框中，单击与希望的即时消息对话中的 URL 处理方式对应的选项。
    
    当用户发送允许发送的超链接时，将通过“允许消息”框向其发送警告消息。

9.  单击“提交”。

## 另请参阅

#### 任务

[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[为特定站点创建新文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### 概念

[修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)

