---
title: 为特定站点创建新文件传输筛选器
TOCTitle: 为特定站点创建新文件传输筛选器
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182589(v=OCS.15)
ms:contentKeyID: 49314308
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为特定站点创建新文件传输筛选器

 

_**上一次修改主题：** 2012-10-18_

除了修改全局文件传输筛选器之外，还可以为 Lync Server 2013 部署中的特定站点配置自定义文件传输筛选器。有关文件传输筛选的详细信息，请参阅[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

## 为特定站点创建文件传输筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“IM 和状态”，然后单击“文件筛选器”。

4.  在“文件筛选器”页上，单击“新建”。

5.  在“选择站点”对话框中，单击要为其创建文件传输筛选器的站点，然后单击“确定”。

6.  在“新建文件筛选器”中，单击“启用文件筛选器”复选框。

7.  在“文件传输”下拉列表框中，单击“全部阻止”或“阻止特定文件类型”。

8.  如果单击了“全部阻止”，则跳到步骤 10。

9.  如果单击了“阻止特定文件类型”，则执行下列操作：
    
    1.  单击“选择”以修改要阻止的默认文件类型扩展名列表。
    
    2.  在“选择文件类型”对话框中，通过在“文件类型扩展名”下的类别中添加或删除扩展名来选择要阻止或允许的文件类型。
    
    3.  如果看不到要阻止的文件类型扩展名，请在“将文件类型扩展名添加到列表”下的文本框中键入相应的扩展名，然后单击“添加”。
    
    4.  单击“确定”。

10. 单击“提交”。

## 另请参阅

#### 任务

[为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[创建新 URL 筛选器以处理 IM 对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### 概念

[修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)

