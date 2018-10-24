---
title: 部署 Lync Server 2013 试点池
TOCTitle: 部署 Lync Server 2013 试点池
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204718(v=OCS.15)
ms:contentKeyID: 49312151
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 Lync Server 2013 试点池

 

_**上一次修改主题：** 2013-11-22_

迁移到 Lync Server 2013 所需的前几步之一是部署试点池。试点池是测试 Lync Server 2013 与 Office Communications Server 2007 R2 部署的共存情况的位置。共存是在将所有用户和池移动到 Lync Server 2013 之前持续的一种临时状态。

在部署试点池时，应使用“定义新的前端池”向导。应在 Lync Server 2013 试点池中部署 Office Communications Server 2007 R2 池中具有的相同功能和工作负荷。如果已部署存档服务器、监控服务器或 System Center Operations Manager 以存档或监控您的 Office Communications Server 2007 R2 环境，并希望在整个迁移过程中继续使用存档或监控功能，则需要在试点环境中也部署这些功能。为存档或监控 Office Communications Server 2007 R2 环境部署的版本将不捕获 Lync Server 2013 环境中的数据。

> [!NOTE]  
> 以下过程将讨论应在整体试点池部署过程中考虑的功能和设置。本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。有关详细步骤，请参阅<a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a> 部署指南。



**部署 Lync Server 2013 试点池**

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  打开拓扑生成器并选择创建新拓扑。

3.  输入主 SIP 域。
    
    ![创建新拓扑 - “定义主域”页](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "创建新拓扑 - “定义主域”页")

4.  继续完成向导，直到出现“定义新前端池”向导。单击“下一步”。

5.  输入池 FQDN。定义试点池时，您可以选择是部署 Enterprise Edition 前端池还是部署 Standard Edition Server。Lync Server 2013 不要求试点池功能与在旧池中部署的内容一致。
    
    > [!WARNING]
    > 您为试点池定义的池或服务器完全限定的域名 (FQDN) 必须是唯一的。它不能匹配当前部署的 Office Communications Server 2007 R2 池或当前部署的任何其他服务器的名称。
    
    ![“定义前端池 FQDN”页](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "“定义前端池 FQDN”页")

6.  定义将添加到池中的计算机。
    
    ![“定义新的前端池”对话框](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "“定义新的前端池”对话框")

7.  在“选择功能”页上，选中希望此前端池具有的功能的复选框。例如，如果您仅部署即时消息 (IM) 和状态功能，可以选中“会议”复选框以允许多方 IM，但不能选中“电话拨入式(PSTN)会议”、“企业语音”或“呼叫允许控制”复选框，因为它们代表语音、视频和协作会议功能。有关选择功能的其他信息，请参阅部署文档中的[在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。
    
    ![前端池 - “选择功能”页](images/JJ205144.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池 - “选择功能”页")

8.  在“选择并置服务器角色”页上，我们建议您在 Lync Server 2013 中并置中介服务器。在合并旧拓扑和 Lync Server 2013 时，我们要求您先并置 Office Communications Server 2007 R2中介服务器。合并拓扑并配置 Lync Server 2013中介服务器后，您可决定是保留并置的中介服务器还是以后在部署过程中将中介服务器角色移动到Lync Server 2013时将其更改为独立服务器。
    
    ![前端池 - “选择并置服务器角色”页](images/JJ205144.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池 - “选择并置服务器角色”页")

9.  在试点池部署过程中，在“将服务器角色与此前端池关联”页上不要选择“启用由此前端池的媒体组件使用的边缘池”选项。这是您将启用并使其在后面的迁移阶段进入联机状态的功能。目前请清除此设置。
    
    ![“将服务器角色与前端池相关联”页](images/JJ205144.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "“将服务器角色与前端池相关联”页")

10. 在“选择 Office Web 应用程序服务器”页上，单击“新建”并指定应用程序服务器的 FQDN。
    
    ![定义新的 Office Web Apps Server FQDN 属性](images/JJ205144.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps Server FQDN 属性")

11. 在“定义存档 SQL Server 存储”页上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。
    
    ![“定义存档 SQL Server 存储”页](images/JJ205144.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "“定义存档 SQL Server 存储”页")

12. 在“定义监视 SQL Server 存储”页上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。单击“完成”。

13. 从拓扑生成器的顶部节点中，右键单击“Lync Server”并单击“编辑属性”。单击“简单 URL”。

14. 更新“管理访问 URL”。
    
    ![编辑属性 -“简单 URL”页](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "编辑属性 -“简单 URL”页")
    
    有关简单 URL 的其他信息，请参阅部署文档中的主题[在 Lync Server 2013 中编辑或配置简单 URL](lync-server-2013-edit-or-configure-simple-urls.md)。

15. 从“编辑属性”中，单击“中央管理服务器”。

16. 从下拉列表中，选择 Lync Server 2013 池。
    
    ![编辑属性 -“中央管理服务器”页](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "编辑属性 -“中央管理服务器”页")

17. 单击“确定”关闭“编辑属性”页。

18. 从“操作”菜单上选择“发布拓扑”。

19. 发布过程完成后，单击“完成”。

20. 返回 Lync Server 2013 部署向导，单击“安装或更新 Lync Server 系统”。
    
    ![Lync Server 2013 部署向导](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署向导")

要安装配置存储的本地副本并启动所需服务，请参阅部署文档中的[为 Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。


