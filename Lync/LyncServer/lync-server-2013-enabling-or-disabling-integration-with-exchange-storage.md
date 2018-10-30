---
title: 启用或禁用与 Exchange 存储的集成
TOCTitle: 启用或禁用与 Exchange 存储的集成
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205228(v=OCS.15)
ms:contentKeyID: 49314141
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用与 Exchange 存储的集成

 

_**上一次修改主题：** 2012-10-09_

在 Lync Server 2013 控制面板中，可以使用存档配置启用和禁用与 Exchange 存储的集成。这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

有关如何实现存档配置（包括可指定的选项和存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

## 启用或禁用与 Microsoft Exchange 存储的集成

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”，再单击“显示详细信息”，然后执行以下操作：
    
      - 要启用与 Exchange 2013 存储的集成，请选中“Microsoft Exchange 集成”复选框。
    
      - 要禁用与 Exchange 2013 存储的集成，请清除“Microsoft Exchange 集成”复选框。

5.  单击“提交”。

## 另请参阅

#### 概念

[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

