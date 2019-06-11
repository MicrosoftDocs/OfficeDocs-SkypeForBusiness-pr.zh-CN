---
title: 'Lync Server 2013: 配置自动发现的反向代理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5445a9ce81835863b610ef32ecc51ccac5331c3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="460f0-102">在 Lync Server 2013 中配置自动发现的反向代理</span><span class="sxs-lookup"><span data-stu-id="460f0-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460f0-103">_**主题上次修改时间:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="460f0-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="460f0-104">使用自动发现的客户端的自动发现和支持需要修改现有 web 发布规则或为反向代理创建新的 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="460f0-105">新发布规则的修改或创建不依赖于在反向代理证书上更新或不更新主题备用名称列表的决定。</span><span class="sxs-lookup"><span data-stu-id="460f0-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="460f0-106">如果你决定为初始 Lync Server 2013 自动发现服务请求使用 HTTPS, 并更新反向代理证书上的 "主题备用名称" 列表, 你需要将更新的公共证书分配给安全套接字层 (SSL) 侦听器的安全套接字层 (SSL) 侦听器您的反向代理。</span><span class="sxs-lookup"><span data-stu-id="460f0-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="460f0-107">对外部 (公共) 证书所需的更新将包括 lyncdiscover 的主题备用名称 (SAN) 条目。\<域名\>。</span><span class="sxs-lookup"><span data-stu-id="460f0-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="460f0-108">然后, 你需要修改外部 web 服务的现有侦听器或为外部自动发现服务 URL 创建新的 web 发布规则, 例如**lyncdiscover.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="460f0-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="460f0-109">如果你的前端池和控制器池的外部 Lync Server 2013 Web 服务 URL 尚无 web 发布规则 (如果已部署控制器), 你还需要为其发布规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="460f0-110">反向代理发布规则和 "自动发现" 服务可以同时为外部 web 服务和自动发现服务提供服务, 前提是分配给侦听器的证书包含两者所需的主题名称和使用者备用名称。</span><span class="sxs-lookup"><span data-stu-id="460f0-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="460f0-111">有关 web 侦听器和发布规则的默认配置的详细信息, 请参阅<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">设置 Lync Server 2013 的反向代理服务器</A>了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="460f0-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="460f0-112">如果你决定将 HTTP 用于初始自动发现服务请求, 以便你无需更新反向代理的使用者备用名称, 你需要为端口80创建或修改 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="460f0-113">本节中的过程介绍了如何在 Microsoft Forefront 威胁管理网关2010中创建或修改 web 发布规则以进行自动发现。</span><span class="sxs-lookup"><span data-stu-id="460f0-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="460f0-114">这些过程假设你已安装了标准版 Forefront 威胁管理网关 (TMG) 2010。</span><span class="sxs-lookup"><span data-stu-id="460f0-114">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="460f0-115">如果您使用的是其他反向代理, 则过程与此类似, 但需要将其映射到第三方产品的文档。</span><span class="sxs-lookup"><span data-stu-id="460f0-115">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="460f0-116">为外部自动发现 URL 创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="460f0-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="460f0-117">单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="460f0-118">在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 指向 "**新建**", 然后单击 "网站**发布规则**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="460f0-119">在 "**欢迎使用新 Web 发布规则**" 页面上, 键入新发布规则的显示名称 (例如, LyncDiscoveryURL)。</span><span class="sxs-lookup"><span data-stu-id="460f0-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="460f0-120">在 "**选择规则操作**" 页面上, 选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="460f0-121">在 "**发布类型**" 页面上, 选择 "**发布单个网站" 或 "负载平衡器**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="460f0-122">在 "**服务器连接安全**" 页面上, 选择 **"使用 SSL 连接到发布的 Web 服务器或服务器场"**。</span><span class="sxs-lookup"><span data-stu-id="460f0-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="460f0-123">在 "**内部发布详细信息**" 页面上的 "**内部网站名称**" 中, 键入你的控制器池的完全限定的域名 (FQDN) (例如, lyncdir01)。</span><span class="sxs-lookup"><span data-stu-id="460f0-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="460f0-124">如果要为前端池上的外部 Web 服务 URL 创建规则, 请键入前端池的 FQDN (例如, lyncpool01)。</span><span class="sxs-lookup"><span data-stu-id="460f0-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="460f0-125">在 "**内部发布详细信息**" 页面上的 "**路径 (可选)**" 中, 键入\*\* / \*\*作为要发布的文件夹的路径, 然后选择 **"转发原始主机头**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="460f0-126">在 "**公共名称详细信息**" 页面上, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="460f0-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="460f0-127">在 "**接受请求**" 下, 选择 "**此域名**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="460f0-128">在 "**公共名称**" 中, 键入**lyncdiscover。**\<sipdomain\> (外部自动发现服务 URL)。</span><span class="sxs-lookup"><span data-stu-id="460f0-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="460f0-129">如果要为前端池上的外部 Web 服务 URL 创建规则, 请在前端池上键入外部 Web 服务的 FQDN (例如, lyncwebextpool01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="460f0-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="460f0-130">在 "**路径**" \*\* /\*\* 中, 键入。</span><span class="sxs-lookup"><span data-stu-id="460f0-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="460f0-131">在 "**选择 Web 侦听器**" 页面上的 " **web 侦听器**" 中, 选择包含已更新的公共证书的现有 SSL 侦听器。</span><span class="sxs-lookup"><span data-stu-id="460f0-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="460f0-132">在 "**身份验证委派**" 页面上, 选择 "**无委派", 但客户端可以直接进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="460f0-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="460f0-133">在 "**用户设置**" 页面上, 选择 "**所有用户**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="460f0-134">在 "**正在完成新建 Web 发布规则向导**" 页面上, 验证 Web 发布规则设置是否正确, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="460f0-135">在 web 发布规则的 Forefront TMG 列表中, 双击刚刚添加到打开的 "**属性**" 的新规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="460f0-136">在 "**收件人**" 选项卡上, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="460f0-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="460f0-137">选择 **"转发原始主机标头, 而不是实际主机标头"**。</span><span class="sxs-lookup"><span data-stu-id="460f0-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="460f0-138">选择**请求似乎来自 FOREFRONT TMG 计算机**。</span><span class="sxs-lookup"><span data-stu-id="460f0-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="460f0-139">在 "**桥接**" 选项卡上, 配置以下内容:</span><span class="sxs-lookup"><span data-stu-id="460f0-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="460f0-140">选择 " **Web 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="460f0-141">选择 "**将请求重定向到 HTTP 端口**", 然后键入**8080**作为端口号。</span><span class="sxs-lookup"><span data-stu-id="460f0-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="460f0-142">选择 "**将请求重定向到 SSL 端口**", 然后键入**4443**作为端口号。</span><span class="sxs-lookup"><span data-stu-id="460f0-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="460f0-143">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="460f0-143">Click **OK**.</span></span>

18. <span data-ttu-id="460f0-144">单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="460f0-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="460f0-145">单击 "**测试规则**" 以验证您的新规则是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="460f0-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="460f0-146">修改现有 web 发布规则以添加外部自动发现 SAN 和 URL</span><span class="sxs-lookup"><span data-stu-id="460f0-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="460f0-147">单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="460f0-148">你将对你拥有的每个发布规则和侦听器重复进行修改。</span><span class="sxs-lookup"><span data-stu-id="460f0-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="460f0-149">通常, 这将是一个规则和一个用于前端池的侦听器, 另一个是可选控制器或控制器池 (如果已部署)。</span><span class="sxs-lookup"><span data-stu-id="460f0-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="460f0-150">在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 然后单击相应的规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-150">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="460f0-151">在 "**任务**" 选项卡上, 单击 "**编辑所选规则**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-151">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="460f0-152">在 "**公共名称**" 选项卡上的 "**此规则适用**于" 中, 选择**以下网站的请求**。</span><span class="sxs-lookup"><span data-stu-id="460f0-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="460f0-153">单击 "**添加**", 键入新的自动发现网站的名称 (例如, "lyncdiscover.contoso.com"), 然后单击 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="460f0-154">在 "**侦听器**" 选项卡上, 单击 "**选择证书**", 然后将新证书分配给已添加的自动发现 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="460f0-154">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="460f0-155">关闭 "侦听器" 和 "Web 发布" 属性。</span><span class="sxs-lookup"><span data-stu-id="460f0-155">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="460f0-156">单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="460f0-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="460f0-157">单击 "**测试规则**" 以验证您的新规则是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="460f0-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="460f0-158">为端口80创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="460f0-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="460f0-159">单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="460f0-160">在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 指向 "**新建**", 然后单击 "网站**发布规则**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="460f0-161">在 "**欢迎使用新 Web 发布规则**" 页面上, 键入新发布规则的显示名称 (例如, Lync 自动发现 (HTTP))。</span><span class="sxs-lookup"><span data-stu-id="460f0-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="460f0-162">在 "**选择规则操作**" 页面上, 选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="460f0-163">在 "**发布类型**" 页面上, 选择 "**发布单个网站" 或 "负载平衡器**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="460f0-164">在 "**服务器连接安全**" 页面上, 选择 **"使用非安全连接" 连接到已发布的 Web 服务器或服务器场**。</span><span class="sxs-lookup"><span data-stu-id="460f0-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="460f0-165">在 "**内部发布详细信息**" 页面上的 "**内部网站名称**" 中, 键入你的前端池的内部 Web 服务 FQDN (例如, lyncpool01)。</span><span class="sxs-lookup"><span data-stu-id="460f0-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="460f0-166">在 "**内部发布详细信息**" 页上的 "**路径 (可选)**" 中, 键入\*\* / \*\*作为要发布的文件夹的路径, 然后选择 **"转发原始主机头", 而不是 "内部网站名称" 字段中指定的主机头**.</span><span class="sxs-lookup"><span data-stu-id="460f0-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="460f0-167">在 "**公共名称详细信息**" 页面上, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="460f0-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="460f0-168">在 "**接受请求**" 下, 选择 "**此域名**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="460f0-169">在 "**公共名称**" 中, 键入**lyncdiscover。**\<sipdomain\> (外部自动发现服务 URL)。</span><span class="sxs-lookup"><span data-stu-id="460f0-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="460f0-170">在 "**路径**" \*\* /\*\* 中, 键入。</span><span class="sxs-lookup"><span data-stu-id="460f0-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="460f0-171">在 "**选择 Web 侦听器**" 页面上的 " **web 侦听器**" 中, 选择 web 侦听器或使用 "新建 Web 侦听器定义" 向导创建新的 web 侦听器。</span><span class="sxs-lookup"><span data-stu-id="460f0-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="460f0-172">在 "**身份验证委派**" 页面上, 选择 "**无委派", 并且客户端无法直接进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="460f0-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="460f0-173">在 "**用户设置**" 页面上, 选择 "**所有用户**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="460f0-174">在 "**正在完成新建 Web 发布规则向导**" 页面上, 验证 Web 发布规则设置是否正确, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="460f0-175">在 web 发布规则的 Forefront TMG 列表中, 双击刚刚添加到打开的 "**属性**" 的新规则。</span><span class="sxs-lookup"><span data-stu-id="460f0-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="460f0-176">在 "**桥接**" 选项卡上, 配置以下内容:</span><span class="sxs-lookup"><span data-stu-id="460f0-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="460f0-177">选择 " **Web 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="460f0-178">选择 "**将请求重定向到 HTTP 端口**", 然后键入**8080**作为端口号。</span><span class="sxs-lookup"><span data-stu-id="460f0-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="460f0-179">验证是否未选中 "**将请求重定向到 SSL 端口**"。</span><span class="sxs-lookup"><span data-stu-id="460f0-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="460f0-180">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="460f0-180">Click **OK**.</span></span>

17. <span data-ttu-id="460f0-181">单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="460f0-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="460f0-182">单击 "**测试规则**" 以验证您的新规则是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="460f0-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="460f0-183">验证外部自动发现服务 URL 是否未在任何其他 web 发布规则上定义。</span><span class="sxs-lookup"><span data-stu-id="460f0-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="460f0-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="460f0-184">See Also</span></span>


[<span data-ttu-id="460f0-185">为 Lync Server 2013 设置反向代理服务器</span><span class="sxs-lookup"><span data-stu-id="460f0-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

