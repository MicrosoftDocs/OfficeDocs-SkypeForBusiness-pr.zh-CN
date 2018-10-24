---
title: 配置站点的存档选项
TOCTitle: 配置站点的存档选项
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204930(v=OCS.15)
ms:contentKeyID: 49312946
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置站点的存档选项

 

_**上一次修改主题：** 2012-10-09_

通过在每个特定站点的存档配置中创建和配置选项可以指定要应用于这些站点的存档选项。站点配置会覆盖全局配置，但仅适用于站点配置中指定的站点。池配置会覆盖站点配置

有关存档配置的工作方式的详细信息（包括全局、站点和池配置的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 您应在存档配置中指定所有适当的选项，然后再启用存档。



> [!IMPORTANT]
> 若要启用存档，您必须指定存档策略以控制全局级别（适当情况下还包括站点和用户级别）的内部和外部通信的存档。如果配置用户级别策略，还必须向特定用户分配用户策略。有关创建和配置存档策略的详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">在 Lync Server 2013 中管理内部通信和外部通信的存档</a>。


## 在站点级别配置存档选项

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  在“存档配置”页上，单击“新建”，然后单击“站点配置”。

5.  在“选择站点”中，选择要为存档配置的站点。

6.  在“存档设置”下拉列表框的“新建存档设置”中，执行以下操作之一：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
      - 若要为 IM 会话和会议启用存档，请单击“存档 IM 和 Web 会议会话”。
    
      - 若要为策略禁用存档，请单击“禁用存档”。

7.  还是在“新建存档设置”中，执行以下操作：
    
      - 若要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。
    
      - 若要使用 Microsoft Exchange Server 存储存档数据，请单击“Microsoft Exchange 集成”复选框。
    
      - 若要启用数据清除，请选中“启用清除存档数据功能”复选框，然后执行以下操作之一：
        
          - 若要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
        
          - 若要将清除仅限于已导出的存档数据，请单击“仅清除已导出的存档数据”。

8.  单击“提交”。

