---
title: 修改默认文件传输筛选器
TOCTitle: 修改默认文件传输筛选器
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521017(v=OCS.15)
ms:contentKeyID: 49313338
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改默认文件传输筛选器

 

_**上一次修改主题：** 2012-11-01_

Lync Server 2013 提供了一个全局文件传输筛选器，可用于在 Lync Server 2013 部署中的以下与文件相关的活动中阻止特定类型的文件：

  - 即时消息 (IM) 对话期间的文件传输请求

  - 使用 Office Live Meeting 2007 客户端中的讲义功能时的文件上载和下载

  - 会议期间的多媒体播放

根据要阻止或允许的文件类型，可以使用 Lync Server 控制面板修改全局筛选器。有关文件传输筛选的详细信息，请参阅[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

## 修改默认文件传输筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“IM 和状态”，然后单击“文件筛选器”。

4.  在“文件筛选器”页上，双击“全局”筛选器。

5.  在“编辑文件筛选器”中，选中“启用文件筛选器”复选框。

6.  在“文件传输”下拉列表框中，单击“全部阻止”或“阻止特定文件类型”。

7.  如果单击了“全部阻止”，则跳到步骤 9。

8.  如果单击了“阻止特定文件类型”，则执行下列操作：
    
    1.  单击“选择”以修改要阻止的默认文件类型扩展名列表。
    
    2.  在“选择文件类型”中，通过在“文件类型扩展名”下的类别中添加或删除扩展名来选择要阻止或允许的文件类型。
    
    3.  如果看不到要阻止的文件类型扩展名，请在“将文件类型扩展名添加到列表”下的文本框中键入相应的扩展名，然后单击“添加”。
    
    4.  单击“确定”。

9.  单击“提交”。

## 另请参阅

#### 任务

[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[为特定站点创建新文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[创建新 URL 筛选器以处理 IM 对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  

#### 概念

[修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)

