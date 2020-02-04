---
title: Lync Server 2013：所需任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013 中的 "需要" 任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-08-18_

根据需要执行以下任务。 标准过程中也经常包含它们：

  - **完整的安全审核   **你可以定期执行此审核，以响应邮件系统的升级或重新设计，或者响应已尝试（或成功）的安全漏洞。 该过程可能涉及服务器和防火墙上的端口扫描、安全修补程序审核以及第三方渗透测试。

  - **将证书替换为过期**   检查 Lync Server 证书是一种常规的周任务，并且作为管理员应记录所有证书到期日期的过程的一部分。 此记录使管理员能够在特定证书即将到期并根据需要替换时创建通知。

  - **更新性能基线**   会在升级或配置更改后更新性能基线。 你的组织可以使用比较基准衡量性能更改并检测影响系统性能的问题。

  - **管理**   企业版池初始配置企业版池、标准版服务器以及组织环境中的任何其他服务器在部署各个服务器的过程中完成。 适用于标准版服务器和企业版池的服务器和池的部署后管理包括以下任务：
    
      - 管理前端服务器
    
      - 管理 Web 会议
    
      - 管理会议
    
      - 更改服务帐户凭据
    
      - 管理数据库
    
      - 启动和停止服务并停用服务器角色
    
      - 删除服务器和服务器角色、删除池以及解除服务器和池的授权

  - **管理使用情况**   你可以配置 Lync Server 2013 以提供最适合你的组织的功能和功能。 这包括以下内容：
    
      - 管理对本地 Web 会议会议的支持
    
      - 管理通讯组的使用以发送即时消息
    
      - 管理联系人、状态和查询
    
      - 配置客户端版本筛选
    
      - 配置智能 IM 筛选
    
      - 配置存档、呼叫详细记录和满足合规性

  - **管理边缘服务器连接**   对提供外部连接所需的服务器和设置的持续管理包括以下几项：
    
      - 管理内部服务器和边缘服务器之间的连接
    
      - 为边缘服务器配置内部和外部接口和证书
    
      - 管理联盟伙伴访问

  - **管理通讯簿**   管理通讯簿服务器包括以下内容：
    
      - 配置通讯簿服务器电话规范化
    
      - 从命令行管理通讯簿服务器

  - **管理**   用户帐户的用户帐户管理包括以下内容：
    
      - 为 Lync Server 启用用户帐户
    
      - 使用向导配置 Lync Server 用户
    
      - 配置单个 Lync Server 用户帐户属性
    
      - 正在搜索 Lync Server 用户
    
      - 移动 Lync Server 用户
    
      - 删除 Lync Server 用户

  - **分析 Lync server 2013 日志文件**   一种非常有用的工具，通常用于疑难解答，是在[使用 lync server 2013 日志记录工具](http://technet.microsoft.com/en-us/library/gg558599.aspx)时详细介绍的 Lync server 2013 日志记录工具。

由于日志记录工具生成日志文件（基于每台服务器），如果计算机上安装了 Microsoft Office Server 12 资源工具包工具，则可以使用 Snooper 工具查看和分析这些日志文件。 否则，还可以通过使用文本编辑器来分析日志，该编辑器比使用 Snooper 实用工具更透明且更复杂。

查看和分析协议消息

在日志记录工具中，当你结束调试会话时，单击 "分析日志文件" 以使用 Snooper 工具查看日志文件。 你可以分析以下组件的协议日志：

  - Lync Server SipStack （SIP）

  - Lync Server S4 （SIP）

  - Lync Server 会议信号流量（C3P），包括 MCU 基础 C3P 和重点 C3P

  - Lync Server Web 会议流量（PSOM）

  - Lync Server 统一通信客户端平台客户端（UCCP）

  - 存档数据库中的错误报告

若要帮助组织按需任务的性能，请参阅所需操作清单。

<div>


> [!IMPORTANT]  
> 有关详细的管理和管理过程，请参阅 Microsoft Lync Server 2013 管理指南。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>备份（和还原）策略或配置设置

Lync Server 2013 允许您备份和还原整个系统。 要备份的 Iif （也可能是天还原）单个策略或单个配置设置集合，检索相应的策略，然后将该对象管道到 Clixml cmdlet，该 cmdlet 将策略信息另存为 XML 文件：

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

您现在可以试用 RedmondClientPolicy 并更改许多设置。 如果您决定改为还原旧策略，请输入：

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

请注意，此方法适用于大多数策略和设置，但不能处理某些较复杂的项目：包含多个子对象的项目（如路由配置设置，其中包含许多单独的语音路由）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

