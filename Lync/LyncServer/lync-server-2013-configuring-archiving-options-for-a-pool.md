---
title: 配置池的存档选项
TOCTitle: 配置池的存档选项
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205200(v=OCS.15)
ms:contentKeyID: 49314055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置池的存档选项

 

_**上一次修改主题：** 2012-10-10_

可以通过在每个特定池的存档配置中创建并配置选项来指定要应用于这些池的存档选项。池配置可重写全局配置和站点配置，但它仅适用于池配置中指定的池。

有关存档配置的工作方式的详细信息（包括全局配置、站点配置和池配置的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 在启用存档之前，应在存档配置中指定所有适当选项。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 在池级别配置存档选项

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。有关可以用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  在“存档配置”页上，单击“新建”，然后单击“池配置”。

5.  在“选择服务”中，选择要为存档配置的池。

6.  在“新建存档设置”的“存档设置”下拉列表中，选择下列存档选项之一：
    
      - **禁用存档**
    
      - **存档 IM 会话**
    
      - **存档 IM 和 Web 会议会话**

7.  另请在“新建存档设置”页中，执行下列操作：
    
      - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。
    
      - 要使用 Microsoft Exchange Server 存储存档数据，请单击“Microsoft Exchange 集成”复选框。
    
      - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
        
          - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
        
          - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。

8.  单击“提交”。

