---
title: 部署 Lync Server 2013 试验池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>部署 Lync Server 2013 试验池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-22_

迁移到 Lync Server 2013 所需的第一步是部署试验池。 在 "试验" 池中，你可以通过 Office 通信服务器 2007 R2 部署来测试 Lync Server 2013 的共存。 共存是指在将所有用户和池移到 Lync Server 2013 之前一直持续的临时状态。

部署试验池时，请使用 "定义新的前端池" 向导。 你应该在你的 Office 通信服务器 2007 R2 池中的 Lync Server 2013 试验池中部署相同的功能和工作负荷。 如果你部署了存档服务器、监视服务器或 System Center Operations Manager 以进行存档或监视你的 Office 通信服务器 2007 R2 环境，并且希望在整个迁移过程中继续存档或监视，你需要还可以在您的试点环境中部署这些功能。 你部署用于存档或监视你的 Office 通信服务器 2007 R2 环境的版本将不会在 Lync Server 2013 环境中捕获数据。

<div>


> [!NOTE]  
> 以下过程讨论了在整个试点池部署过程中应考虑的功能和设置。 本部分仅重点介绍您在试验池部署中应考虑的要点。 有关详细步骤，请参阅<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。



</div>

**部署 Lync Server 2013 试验池**

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  打开拓扑生成器并选择 "创建新拓扑"。

3.  输入主要 SIP 域。
    
    ![创建新拓扑，定义主域页面](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "创建新拓扑，定义主域页面")

4.  继续完成向导，直到到达 "**定义新的前端池**" 向导。 单击" 下一步"。

5.  输入池 FQDN。 定义试验池时，可以选择部署企业版前端池或标准版服务器。 Lync Server 2013 不要求引导池功能与您的旧版池中部署的功能相匹配。
    
    <div>
    

    > [!WARNING]  
    > 为试点池定义的池或服务器完全限定的域名（FQDN）必须是唯一的。 它不能与当前部署的 Office 通信服务器 2007 R2 池或任何其他当前部署的服务器的名称相匹配。

    
    </div>
    
    ![定义前端池 FQDN 页面](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "定义前端池 FQDN 页面")

6.  定义将添加到池中的计算机。
    
    !["定义新的前端池" 对话框](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg ""定义新的前端池" 对话框")

7.  在 "**选择功能**" 页面上，选中您希望在此前端池上的功能所对应的复选框。 例如，如果您仅部署即时消息（IM）和状态功能，则可以选择 "会议" 复选框以允许多方 IM，但不会选择 "拨入（PSTN）会议"、"企业语音" 或 "呼叫许可控制" 复选框，因为它们代表语音、视频和协作式会议功能。 有关选择功能的其他信息，请参阅部署文档中的[Lync server 2013 中的 "定义和配置前端池" 或 "标准版服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)"。
    
    ![前端池选择功能页面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池选择功能页面")

8.  在 "**选择 collocated 服务器角色**" 页面上，建议在 Lync server 2013 中 Collocate 中介服务器。 将旧版拓扑与 Lync Server 2013 合并时，我们需要首先 collocate Office 通信服务器 2007 R2 中介服务器。 合并拓扑并配置 Lync Server 2013 中介服务器之后，你可以决定在部署中将中介服务器角色移动到 Lync Server 2013 时是否保留 collocated 中介服务器或将其更改为独立服务器工艺.
    
    ![前端池选择 "collocated 服务器角色" 页面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池选择 "collocated 服务器角色" 页面")

9.  在试验池部署期间，在 "**关联服务器角色与此前端池**" 页面上，不要选择 "**启用要由此前端池的媒体组件使用的边缘池**" 选项。 这是你将在迁移的后续阶段启用并联机的功能。 立即清除此设置。
    
    ![将服务器角色与前端池页面关联](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "将服务器角色与前端池页面关联")

10. 在 "**选择 Office Web Apps 服务器**" 页面上，单击 "**新建**"，然后指定应用程序服务器的 FQDN。
    
    ![定义新的 Office Web Apps 服务器 FQDN 属性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps 服务器 FQDN 属性")

11. 在 "**定义存档 SQL Server 存储**" 页面上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。
    
    ![定义 "存档 SQL Server 存储" 页面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定义 "存档 SQL Server 存储" 页面")

12. 在 "**定义监视 SQL Server 存储**" 页面上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。 单击“**完成**”。

13. 从拓扑生成器的顶部节点，右键单击 " **Lync 服务器**"，然后单击 "**编辑属性"。** 单击 "**简单 url**"。

14. 更新**管理访问 URL**。
    
    !["编辑属性"、"简单 Url" 页面](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg ""编辑属性"、"简单 Url" 页面")
    
    有关简单 Url 的其他信息，请参阅部署文档中的在[Lync Server 2013 中编辑或配置简单 url](lync-server-2013-edit-or-configure-simple-urls.md)的主题。

15. 从 "**编辑属性**" 中，单击 "**中央管理服务器**"。

16. 从下拉列表中，选择 "Lync Server 2013" 池。
    
    !["编辑属性"-"中央管理服务器" 页面](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg ""编辑属性"-"中央管理服务器" 页面")

17. 单击 "确定" 以关闭 **"编辑属性"** 页面。

18. 从 "**操作**" 菜单中，选择 "**发布拓扑**"。

19. 发布过程完成后，单击 "**完成**"。

20. 返回到 Lync Server 2013 部署向导，单击 "**安装或更新 Lync Server 系统**"。
    
    ![Lync Server 2013 部署向导](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署向导")

若要安装配置存储的本地副本并启动所需的服务，请参阅部署文档中的[Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。


</div>

<span> </span>

</div>

</div>

</div>

