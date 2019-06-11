---
title: 使用反向代理服务器发布 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68ae51dba366282d7d3a5668b1358042a29917
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-25_

如果你希望外部用户 (即从组织防火墙外部登录的用户) 有权访问 Office Web Apps Server PowerPoint 演示文稿, 则你需要使用 Office Web Apps 服务器和反向代理服务器 (如 Microsoft Forefront)威胁管理网关。 这还意味着你将需要创建和配置网站发布规则;该规则将帮助确保用户能够连接到服务器。 如果不需要提供对外部用户的访问权限, 则无需配置网站发布规则。

若要在 "Forefront 威胁管理" 网关配置网站发布规则, 请完成以下过程:

1.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。

2.  在 Forefront TMG 中, 右键单击 "**防火墙策略**", 指向 "**新建**", 然后单击 "网站**发布规则**"。

3.  在 "新建 Web 发布规则" 向导的 "**欢迎使用新 Web 发布规则向导**" 页面上, 在 " **Web 发布规则名称**" 框 (例如, " **Office Web Apps 服务器规则**") 中键入新规则的名称, 然后单击 "**下一步**"。

4.  在 "**指定规则操作**" 页面上, 选择 "**允许**", 然后单击 "**下一步**"。

5.  在 "**发布类型**" 页面上, 选择 "**发布单个网站或负载平衡器**", 然后单击 "**下一步**"。

6.  在 "**服务器连接安全**" 页面上, 选择 "**使用 SSL 连接到已发布的 Web 服务器或服务器场"** , 然后单击 "**下一步**"。

7.  在 "**内部发布详细信息**" 页面上, 在 "**内部网站名称**" 框中键入 Office WEB Apps 服务器的 FQDN (例如, **officewebapps01.contoso.com**), 然后单击 "**下一步**"。 在 "**内部网站名称**" 框中输入的名称必须出现在已分配给 Office Web Apps 服务器的证书的 "主题" 字段或 "主题备用名称" 字段中。

8.  在 "**内部发布详细信息**" 页面** / **上, 键入 "**路径 (可选)** " 框, 然后单击 "**下一步**"。 /\*语法将帮助确保发布网站的所有文件夹和子文件夹。

9.  在 "**公共名详细信息**" 页面上, 从 "**接受请求**" 下拉列表中选择**此域名 (如下所示)** , 然后在 "公共名称" 框中键入适用于你的 Office Web Apps 服务器的完全限定。 此名称应该是用于访问您的网站的名称。 例如, 如果您的网站是使用 URL http://officewebapps01.contoso.com访问的, 则应在 "**公共名称**" 框中输入 " **officewebapps01.contoso.com** "。

10. 单击" **下一步**"。

11. 在 "**选择 Web 侦听器**" 页面上, 单击 "**新建**"。

12. 在 "新建 Web 侦听器定义向导" 中, 在 " **web 侦听器名称**" 框中键入新的 web 侦听器 (例如, **SSL**) 的名称, 然后单击 "**下一步**"。

13. 在 "**客户端连接安全**" 页面上, 选择 "**需要与客户端的 SSL 安全连接**", 然后单击 "**下一步**

14. 在 " **Web 侦听器 IP 地址**" 页面上, 选择 "**外部**", 选择 "**内部**", 然后单击 "**下一步**"。

15. 在 "**侦听器 SSL 证书**" 页面上, 选择 "**使用此 Web 侦听器的单个证书**", 然后单击 "**选择证书**"。

16. 在 "**选择证书**" 对话框中, 选择要用于此 Web 侦听器的证书, 然后单击 "**选择**"。

17. 在 "**侦听器 SSL 证书**" 页面上, 单击 "**下一步**"。

18. 在 "**身份验证设置**" 页面上, 从 "**选择客户端将向 Forefront TMG 的凭据提供凭据**" 下拉列表中选择 "**无身份验证**", 然后单击 "**下一步**"。

19. 在 "**单一登录设置**" 页面上, 单击 "**下一步**"。

20. 在 "**完成新建 Web 侦听器向导**" 页面上, 查看您所做的配置选择的摘要。 准备就绪后, 单击 "**完成**"。

21. 在 "**选择 Web 侦听器**" 页面上, 单击 "**下一步**"。

22. 在 "**身份验证委派**" 页面上, 选择 "**无委派", 但客户端可以直接**从**选择 Forefront TMG 使用的方法验证到 "已发布的 Web 服务器**" 下拉列表, 然后单击 "**下一步"**.

23. 在 "**用户集**" 页面上, 确认列出了相应的用户集。 默认情况下, 这是 "**所有用户**" 设置。 单击 "**添加**" 以添加你可能已定义的其他用户集。 完成后, 单击 "**下一步**"。

24. 在 "**正在完成新建 Web 发布规则向导**" 页面上, 单击 "**完成**"。

请注意, 单击 "**完成**" 并不意味着你已完成该过程;也就是说, 这不会自动应用和启用新规则。 而是需要单击将在 Forefront TMG 用户界面中显示的 "**应用**" 按钮。 单击 "应用配置更改说明" 对话框时, 将显示 "**应用****配置更改说明**" 对话框。 单击 "在该对话框中**应用**" 以启用新的发布规则。

应用新规则后, 你将需要对规则进行一些细微的修改, 以确保用户可以使用新的 PowerPoint 演示文稿功能。 为此，请完成以下过程：

1.  在 Forefront TMG 中, 右键单击新发布规则的名称, 然后单击 "**属性**"。

2.  在 "**属性**" 对话框中的 "**收件人**" 选项卡上, 选择 "**转发原始主机标题而不是实际主机标题**" 选项。

3.  在 "**流量**" 选项卡上, 单击 "**筛选**", 然后单击 "**配置 HTTP**"。

4.  在 "**配置规则的 HTTP 策略**" 对话框中, 清除 "**验证规范化**" 复选框, 然后单击 **"确定"**。

5.  在 "**属性**" 对话框中, 单击 **"确定"**。

6.  在 Forefront TMG 中, 单击 "**应用**" 以启用更改。 出现 "**配置更改说明**" 对话框时, 单击 "**应用**"。

完成安装后, 你可以使用在[Lync server 2013 中验证 Office Web apps 配置的](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)主题中的过程测试 Office Web apps 服务器。

</div>

<span> </span>

</div>

</div>

</div>

