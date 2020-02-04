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
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="d329f-102">使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps 服务器</span><span class="sxs-lookup"><span data-stu-id="d329f-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d329f-103">_**主题上次修改时间：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d329f-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d329f-104">如果你希望外部用户（即从组织防火墙外部登录的用户）有权访问 Office Web Apps Server PowerPoint 演示文稿，则你需要使用 Office Web Apps 服务器和反向代理服务器（如 Microsoft Forefront）威胁管理网关。</span><span class="sxs-lookup"><span data-stu-id="d329f-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="d329f-105">这还意味着你将需要创建和配置网站发布规则;该规则将帮助确保用户能够连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="d329f-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="d329f-106">如果不需要提供对外部用户的访问权限，则无需配置网站发布规则。</span><span class="sxs-lookup"><span data-stu-id="d329f-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="d329f-107">若要在 "Forefront 威胁管理" 网关配置网站发布规则，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="d329f-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="d329f-108">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Forefront tmg**"，然后单击 " **Forefront tmg 管理**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d329f-109">在 Forefront TMG 中，右键单击 "**防火墙策略**"，指向 "**新建**"，然后单击 "网站**发布规则**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d329f-110">在 "新建 Web 发布规则" 向导的 "**欢迎使用新 Web 发布规则向导**" 页面上，在 " **Web 发布规则名称**" 框（例如，" **Office Web Apps 服务器规则**"）中键入新规则的名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="d329f-111">在 "**指定规则操作**" 页面上，选择 "**允许**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="d329f-112">在 "**发布类型**" 页面上，选择 "**发布单个网站或负载平衡器**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="d329f-113">在 "**服务器连接安全**" 页面上，选择 "**使用 SSL 连接到已发布的 Web 服务器或服务器场"** ，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="d329f-114">在 "**内部发布详细信息**" 页面上，在 "**内部网站名称**" 框中键入 Office WEB Apps 服务器的 FQDN （例如， **officewebapps01.contoso.com**），然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="d329f-115">在 "**内部网站名称**" 框中输入的名称必须出现在已分配给 Office Web Apps 服务器的证书的 "主题" 字段或 "主题备用名称" 字段中。</span><span class="sxs-lookup"><span data-stu-id="d329f-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="d329f-116">在 "**内部发布详细信息**" 页面\*\* / **上，键入 "**路径（可选）\*\* " 框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="d329f-117">/\*语法将帮助确保发布网站的所有文件夹和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="d329f-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="d329f-118">在 "**公共名详细信息**" 页面上，从 "**接受请求**" 下拉列表中选择**此域名（如下所示）** ，然后在 "公共名称" 框中键入适用于你的 Office Web Apps 服务器的完全限定。</span><span class="sxs-lookup"><span data-stu-id="d329f-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="d329f-119">此名称应该是用于访问您的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="d329f-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="d329f-120">例如，如果您的网站是使用 URL http://officewebapps01.contoso.com访问的，则应在 "**公共名称**" 框中输入 " **officewebapps01.contoso.com** "。</span><span class="sxs-lookup"><span data-stu-id="d329f-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="d329f-121">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-121">Click **Next**.</span></span>

11. <span data-ttu-id="d329f-122">在 "**选择 Web 侦听器**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="d329f-123">在 "新建 Web 侦听器定义向导" 中，在 " **web 侦听器名称**" 框中键入新的 web 侦听器（例如， **SSL**）的名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="d329f-124">在 "**客户端连接安全**" 页面上，选择 "**需要与客户端的 SSL 安全连接**"，然后单击 "**下一步**</span><span class="sxs-lookup"><span data-stu-id="d329f-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="d329f-125">在 " **Web 侦听器 IP 地址**" 页面上，选择 "**外部**"，选择 "**内部**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="d329f-126">在 "**侦听器 SSL 证书**" 页面上，选择 "**使用此 Web 侦听器的单个证书**"，然后单击 "**选择证书**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="d329f-127">在 "**选择证书**" 对话框中，选择要用于此 Web 侦听器的证书，然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="d329f-128">在 "**侦听器 SSL 证书**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="d329f-129">在 "**身份验证设置**" 页面上，从 "**选择客户端将向 Forefront TMG 的凭据提供凭据**" 下拉列表中选择 "**无身份验证**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="d329f-130">在 "**单一登录设置**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="d329f-131">在 "**完成新建 Web 侦听器向导**" 页面上，查看您所做的配置选择的摘要。</span><span class="sxs-lookup"><span data-stu-id="d329f-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="d329f-132">准备就绪后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="d329f-133">在 "**选择 Web 侦听器**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="d329f-134">在 "**身份验证委派**" 页面上，选择 "**无委派"，但客户端可以直接**从**选择 Forefront TMG 使用的方法验证到 "已发布的 Web 服务器**" 下拉列表，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="d329f-135">在 "**用户集**" 页面上，确认列出了相应的用户集。</span><span class="sxs-lookup"><span data-stu-id="d329f-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="d329f-136">默认情况下，这是 "**所有用户**" 设置。</span><span class="sxs-lookup"><span data-stu-id="d329f-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="d329f-137">单击 "**添加**" 以添加你可能已定义的其他用户集。</span><span class="sxs-lookup"><span data-stu-id="d329f-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="d329f-138">完成后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="d329f-139">在 "**正在完成新建 Web 发布规则向导**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="d329f-140">请注意，单击 "**完成**" 并不意味着你已完成该过程;也就是说，这不会自动应用和启用新规则。</span><span class="sxs-lookup"><span data-stu-id="d329f-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="d329f-141">而是需要单击将在 Forefront TMG 用户界面中显示的 "**应用**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d329f-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="d329f-142">单击 "应用配置更改说明" 对话框时，将显示 "**应用\*\*\*\*配置更改说明**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d329f-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="d329f-143">单击 "在该对话框中**应用**" 以启用新的发布规则。</span><span class="sxs-lookup"><span data-stu-id="d329f-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="d329f-144">应用新规则后，你将需要对规则进行一些细微的修改，以确保用户可以使用新的 PowerPoint 演示文稿功能。</span><span class="sxs-lookup"><span data-stu-id="d329f-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="d329f-145">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="d329f-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="d329f-146">在 Forefront TMG 中，右键单击新发布规则的名称，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="d329f-147">在 "**属性**" 对话框中的 "**收件人**" 选项卡上，选择 "**转发原始主机标题而不是实际主机标题**" 选项。</span><span class="sxs-lookup"><span data-stu-id="d329f-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="d329f-148">在 "**流量**" 选项卡上，单击 "**筛选**"，然后单击 "**配置 HTTP**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="d329f-149">在 "**配置规则的 HTTP 策略**" 对话框中，清除 "**验证规范化**" 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d329f-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="d329f-150">在 "**属性**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d329f-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="d329f-151">在 Forefront TMG 中，单击 "**应用**" 以启用更改。</span><span class="sxs-lookup"><span data-stu-id="d329f-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="d329f-152">出现 "**配置更改说明**" 对话框时，单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d329f-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="d329f-153">完成安装后，你可以使用在[Lync server 2013 中验证 Office Web apps 配置的](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)主题中的过程测试 Office Web apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="d329f-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

