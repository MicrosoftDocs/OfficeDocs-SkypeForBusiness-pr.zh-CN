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
ms.openlocfilehash: e9a2bc53d306b51bd6aa681ccb4aa6747f38eac7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="91bbb-102">使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="91bbb-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bbb-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="91bbb-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="91bbb-104">如果您希望外部用户（即从您的组织的防火墙外部登录的用户）能够访问 Office Web Apps 服务器 PowerPoint 演示文稿，则您需要使用 Office Web Apps 服务器和一个反向代理服务器（如 Microsoft Forefront Threat Management Gateway）。</span><span class="sxs-lookup"><span data-stu-id="91bbb-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="91bbb-105">这也意味着您将需要创建和配置网站发布规则;该规则将帮助确保用户能够连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="91bbb-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="91bbb-106">如果您不需要为外部用户提供访问权，则不需要配置网站发布规则。</span><span class="sxs-lookup"><span data-stu-id="91bbb-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="91bbb-107">若要在 Forefront Threat Management Gateway 中配置网站发布规则，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="91bbb-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="91bbb-108">单击“开始”\*\*\*\*，单击“所有程序”\*\*\*\*，单击“Microsoft Forefront TMG”\*\*\*\*，然后单击“Forefront TMG Management”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="91bbb-109">在 Forefront TMG 中，右键单击“防火墙策略”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“网站发布规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="91bbb-110">在“新建 Web 发布规则向导”中的“欢迎使用新建 Web 发布规则向导”\*\*\*\* 页面上，在“Web 发布规则名称”\*\*\*\* 框中键入新规则的名称（例如，“Office Web Apps 服务器规则”\*\*\*\*），然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="91bbb-111">在“指定规则操作”\*\*\*\* 页面上，选择“允许”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="91bbb-112">在“发布类型”\*\*\*\* 页面上，选择“发布单个网站或负载平衡器”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="91bbb-113">在“服务器连接安全”\*\*\*\* 页面上，选择“使用 SSL 连接到发布的 Web 服务器或服务器场”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="91bbb-p102">在“内部发布详细信息”\*\*\*\* 页面上，在“内部站点名称”\*\*\*\* 框中，键入您的 Office Web Apps 服务器的 FQDN（例如，“officewebapps01.contoso.com”\*\*\*\*），然后单击“下一步”\*\*\*\*。在“内部站点名称”\*\*\*\* 框中输入的名称必须出现在分配给 Office Web Apps 服务器的证书的“使用者”字段或“使用者替代名称”字段中。</span><span class="sxs-lookup"><span data-stu-id="91bbb-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="91bbb-116">在 "**内部发布详细信息**" 页\*\* / **上的 "**路径（可选）\*\* " 框中键入，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="91bbb-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="91bbb-117">/\*语法可帮助确保发布网站的所有文件夹和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="91bbb-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="91bbb-118">在“公共名称细节”\*\*\*\* 页面上，从“接受请求”\*\*\*\* 下拉列表中选择“此域名(在以下输入)”\*\*\*\*，然后在“公共名称”框中键入您的 Office Web Apps 服务器的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="91bbb-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="91bbb-119">此名称应是用来访问您的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="91bbb-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="91bbb-120">例如，如果使用 URL http://officewebapps01.contoso.com访问网站，则应在 "**公共名称**" 框中输入**officewebapps01.contoso.com** 。</span><span class="sxs-lookup"><span data-stu-id="91bbb-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="91bbb-121">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-121">Click **Next**.</span></span>

11. <span data-ttu-id="91bbb-122">在“选择 Web 侦听器”\*\*\*\* 页面上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="91bbb-123">在“新建 Web 侦听器定义向导”中，在“Web 侦听器名称”\*\*\*\* 框中键入新的 Web 侦听器的名称（例如，“SSL”\*\*\*\*），然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="91bbb-124">在“客户端连接安全性”\*\*\*\* 页面上，选择“需要与客户端建立 SSL 安全连接”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="91bbb-125">在“Web 侦听器 IP 地址”\*\*\*\* 页面上，选择“外部”\*\*\*\*，选择“内部”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="91bbb-126">在“侦听器 SSL 证书”\*\*\*\* 页面上，选择“对此 Web 侦听器使用单一证书”\*\*\*\*，然后单击“选择证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="91bbb-127">在“选择证书”\*\*\*\* 对话框中，选择要用于此 Web 侦听器的证书，然后单击“选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="91bbb-128">在“侦听器 SSL 证书”\*\*\*\* 页面上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="91bbb-129">在“身份验证设置”\*\*\*\* 页面上，从“选择客户端为 Forefront TMG 提供凭据的方式”\*\*\*\* 下拉列表中选择“无身份验证”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="91bbb-130">在“单一登录设置”\*\*\*\* 页面上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="91bbb-p105">在“正在完成新建 Web 侦听器向导”\*\*\*\* 页面上，检查所做的配置选择的摘要。就绪后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="91bbb-133">在“选择 Web 侦听器”\*\*\*\* 页面上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="91bbb-134">在“身份验证委派”\*\*\*\* 页面上，从“选择 Forefront TMG 使用的方法以对发布的 Web 服务器进行身份验证”\*\*\*\* 下拉列表选择“无委派，但是客户端可以直接进行身份验证”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="91bbb-p106">在“用户集”\*\*\*\* 页面上，确认列出了适当的用户集。默认情况下，为“所有用户”\*\*\*\* 用户集。单击“添加”\*\*\*\* 以添加其他您可能已定义的用户集。完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="91bbb-139">在“正在完成新建 Web 发布规则向导”\*\*\*\* 页面上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="91bbb-p107">注意，单击“完成”\*\*\*\* 并不意味着完成了这一过程，即它不会自动应用并启用新规则。相反，您需要单击 Forefront TMG 用户界面中显示的“应用”\*\*\*\* 按钮。当单击“应用”\*\*\*\* 时，将出现“配置更改说明”\*\*\*\* 对话框。单击该对话框中的“应用”\*\*\*\* 来启用新的发布规则。</span><span class="sxs-lookup"><span data-stu-id="91bbb-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="91bbb-144">应用新规则后，您需要对规则进行一些细微的修改，以确保用户可以使用新的 PowerPoint 演示文稿功能。</span><span class="sxs-lookup"><span data-stu-id="91bbb-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="91bbb-145">为此，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="91bbb-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="91bbb-146">在 Forefront TMG 中，右键单击新发布规则的名称，然后单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="91bbb-147">在“属性”\*\*\*\* 对话框的“目标”\*\*\*\* 选项卡上，选择选项“转发原始主机头而不是实际主机头”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="91bbb-148">在“流量”\*\*\*\* 选项卡上，单击“筛选”\*\*\*\*，然后单击“配置 HTTP”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="91bbb-149">在“配置规则的 HTTP 策略”\*\*\*\* 对话框中，清除“验证正则化”\*\*\*\* 复选框，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="91bbb-150">在“属性”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="91bbb-p109">在 Forefront TMG 中，单击“应用”\*\*\*\* 启用更改。当出现“配置更改说明”\*\*\*\* 对话框时，单击“应用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="91bbb-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="91bbb-153">完成安装后，可以使用在[Lync Server 2013 中验证 Office Web Apps server 配置](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)主题中的过程来测试 Office Web apps server。</span><span class="sxs-lookup"><span data-stu-id="91bbb-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

