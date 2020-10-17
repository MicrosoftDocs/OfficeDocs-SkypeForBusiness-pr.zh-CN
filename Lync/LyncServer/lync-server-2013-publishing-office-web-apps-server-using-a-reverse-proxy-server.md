---
title: 使用反向代理服务器发布 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb200204cc96d40d66d0546c86687fb0e1c48de5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512229"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

如果您希望外部用户（即从您的组织的防火墙外部登录的用户）能够访问 Office Web Apps 服务器 PowerPoint 演示文稿，则您需要使用 Office Web Apps 服务器和一个反向代理服务器（如 Microsoft Forefront Threat Management Gateway）。 这也意味着您将需要创建和配置网站发布规则;该规则将帮助确保用户能够连接到服务器。 如果您不需要为外部用户提供访问权，则不需要配置网站发布规则。

若要在 Forefront Threat Management Gateway 中配置网站发布规则，请完成以下步骤：

1.  单击“开始”****，单击“所有程序”****，单击“Microsoft Forefront TMG”****，然后单击“Forefront TMG Management”****。

2.  在 Forefront TMG 中，右键单击“防火墙策略”****，指向“新建”****，然后单击“网站发布规则”****。

3.  在“新建 Web 发布规则向导”中的“欢迎使用新建 Web 发布规则向导”**** 页面上，在“Web 发布规则名称”**** 框中键入新规则的名称（例如，“Office Web Apps 服务器规则”****），然后单击“下一步”****。

4.  在“指定规则操作”**** 页面上，选择“允许”****，然后单击“下一步”****。

5.  在“发布类型”**** 页面上，选择“发布单个网站或负载平衡器”****，然后单击“下一步”****。

6.  在“服务器连接安全”**** 页面上，选择“使用 SSL 连接到发布的 Web 服务器或服务器场”****，然后单击“下一步”****。

7.  在“内部发布详细信息”**** 页面上，在“内部站点名称”**** 框中，键入您的 Office Web Apps 服务器的 FQDN（例如，“officewebapps01.contoso.com”****），然后单击“下一步”****。在“内部站点名称”**** 框中输入的名称必须出现在分配给 Office Web Apps 服务器的证书的“使用者”字段或“使用者替代名称”字段中。

8.  在 " **内部发布详细信息** " 页上的 **/\*** " ** (可选) ** " 框中键入路径，然后单击 " **下一步**"。 / \* 语法可帮助确保发布网站的所有文件夹和子文件夹。

9.  在“公共名称细节”**** 页面上，从“接受请求”**** 下拉列表中选择“此域名(在以下输入)”****，然后在“公共名称”框中键入您的 Office Web Apps 服务器的完全限定名称。 此名称应是用来访问您的网站的名称。 例如，如果使用 URL 访问网站，则 http://officewebapps01.contoso.com 应在 "**公共名称**" 框中输入**officewebapps01.contoso.com** 。

10. 单击“下一步”****。

11. 在“选择 Web 侦听器”**** 页面上，单击“新建”****。

12. 在“新建 Web 侦听器定义向导”中，在“Web 侦听器名称”**** 框中键入新的 Web 侦听器的名称（例如，“SSL”****），然后单击“下一步”****。

13. 在“客户端连接安全性”**** 页面上，选择“需要与客户端建立 SSL 安全连接”****，然后单击“下一步”****。

14. 在“Web 侦听器 IP 地址”**** 页面上，选择“外部”****，选择“内部”****，然后单击“下一步”****。

15. 在“侦听器 SSL 证书”**** 页面上，选择“对此 Web 侦听器使用单一证书”****，然后单击“选择证书”****。

16. 在“选择证书”**** 对话框中，选择要用于此 Web 侦听器的证书，然后单击“选择”****。

17. 在“侦听器 SSL 证书”**** 页面上，单击“下一步”****。

18. 在“身份验证设置”**** 页面上，从“选择客户端为 Forefront TMG 提供凭据的方式”**** 下拉列表中选择“无身份验证”****，然后单击“下一步”****。

19. 在“单一登录设置”**** 页面上，单击“下一步”****。

20. 在“正在完成新建 Web 侦听器向导”**** 页面上，检查所做的配置选择的摘要。就绪后，单击“完成”****。

21. 在“选择 Web 侦听器”**** 页面上，单击“下一步”****。

22. 在“身份验证委派”**** 页面上，从“选择 Forefront TMG 使用的方法以对发布的 Web 服务器进行身份验证”**** 下拉列表选择“无委派，但是客户端可以直接进行身份验证”****，然后单击“下一步”****。

23. 在“用户集”**** 页面上，确认列出了适当的用户集。默认情况下，为“所有用户”**** 用户集。单击“添加”**** 以添加其他您可能已定义的用户集。完成后，单击“下一步”****。

24. 在“正在完成新建 Web 发布规则向导”**** 页面上，单击“完成”****。

注意，单击“完成”**** 并不意味着完成了这一过程，即它不会自动应用并启用新规则。相反，您需要单击 Forefront TMG 用户界面中显示的“应用”**** 按钮。当单击“应用”**** 时，将出现“配置更改说明”**** 对话框。单击该对话框中的“应用”**** 来启用新的发布规则。

应用新规则后，您需要对规则进行一些细微的修改，以确保用户可以使用新的 PowerPoint 演示文稿功能。 为此，请完成以下步骤：

1.  在 Forefront TMG 中，右键单击新发布规则的名称，然后单击“属性”****。

2.  在“属性”**** 对话框的“目标”**** 选项卡上，选择选项“转发原始主机头而不是实际主机头”****。

3.  在“流量”**** 选项卡上，单击“筛选”****，然后单击“配置 HTTP”****。

4.  在“配置规则的 HTTP 策略”**** 对话框中，清除“验证正则化”**** 复选框，然后单击“确定”****。

5.  在“属性”**** 对话框中，单击“确定”****。

6.  在 Forefront TMG 中，单击“应用”**** 启用更改。当出现“配置更改说明”**** 对话框时，单击“应用”****。

完成安装后，可以使用在 [Lync Server 2013 中验证 Office Web Apps server 配置](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)主题中的过程来测试 Office Web apps server。

</div>

<span> </span>

</div>

</div>

</div>

