---
title: Lync Server 2013：为自动发现配置反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0fb05667ea6ebcb8176353d42fda5cf2eaadfd7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515579"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d67f2-102">在 Lync Server 2013 中为自动发现配置反向代理</span><span class="sxs-lookup"><span data-stu-id="d67f2-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67f2-103">_**上次修改的主题：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d67f2-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d67f2-104">使用自动发现的客户端的自动发现和支持需要修改现有的 web 发布规则或为反向代理创建新的 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="d67f2-105">修改或创建新的发布规则并不依赖于更新或不更新反向代理证书上的主题备用名称列表的决定。</span><span class="sxs-lookup"><span data-stu-id="d67f2-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="d67f2-106">如果您决定对初始 Lync Server 2013 自动发现服务请求使用 HTTPS，并在反向代理证书上更新 "主题备用名称" 列表，则需要将更新的公共证书分配给反向代理上的安全套接字层 (SSL) 侦听器。</span><span class="sxs-lookup"><span data-stu-id="d67f2-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="d67f2-107">对外部 (公用) 证书所需的更新将包含 lyncdiscover. 的主题备用名称 (SAN) 条目。 \<domain name\> 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="d67f2-108">然后，您需要修改外部 web 服务的现有侦听器或为外部自动发现服务 URL 创建新的 web 发布规则，例如 **lyncdiscover.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="d67f2-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="d67f2-109">如果你的前端池和控制器池的外部 Lync Server 2013 Web 服务 URL 尚无 web 发布规则 (如果已部署了控制器) ，还需要为此发布一个规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d67f2-110">只要分配给侦听器的证书同时包含针对外部 Web 服务和自动发现服务的必要的使用者名称和使用者替代名称，反向代理发布规则和侦听器就可以为这两种服务提供服务。</span><span class="sxs-lookup"><span data-stu-id="d67f2-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="d67f2-111">有关 web 侦听器和发布规则的默认配置的详细信息，请参阅为 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 设置反向代理服务器</A> ，了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d67f2-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="d67f2-112">如果您决定对初始自动发现服务请求使用 HTTP 以便无需更新反向代理的使用者替代名称，则需要为端口 80 创建或修改一条 Web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="d67f2-113">本节中的过程介绍如何使用 Microsoft Forefront Threat Management Gateway 2010 创建或修改一条 Web 发布规则以实现自动发现。</span><span class="sxs-lookup"><span data-stu-id="d67f2-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d67f2-p104">这些过程假定您已安装 Forefront Threat Management Gateway (TMG) 2010 Standard Edition。如果您使用另一个反向代理，则这些过程是类似的，只不过需要将其映射到第三方产品的文档。</span><span class="sxs-lookup"><span data-stu-id="d67f2-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="d67f2-116">为外部自动发现 URL 创建 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="d67f2-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="d67f2-117">单击“开始”\*\*\*\*，依次指向“程序”\*\*\*\*、“Microsoft Forefront TMG”\*\*\*\*，然后单击“Forefront TMG 管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d67f2-118">在左窗格中，展开“服务器名称”\*\*\*\*，右键单击“防火墙策略”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“网站发布规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d67f2-119">在“欢迎使用新建 Web 发布规则向导”\*\*\*\* 页上，为新的发布规则键入一个显示名称（例如，LyncDiscoveryURL）。</span><span class="sxs-lookup"><span data-stu-id="d67f2-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="d67f2-120">在“选择规则操作”\*\*\*\* 页上，选择“允许”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d67f2-121">在“发布类型”\*\*\*\* 页上，选择“发布单个网站或负载平衡器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d67f2-122">在“服务器连接安全性”\*\*\*\* 页上，选择“使用 SSL 连接到发布的 Web 服务器或服务器场”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d67f2-123">在 " **内部发布详细信息** " 页上的 " **内部站点名称**" 中，键入控制器池的完全限定的域名 (FQDN)  (例如，lyncdir01) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="d67f2-124">如果要为前端池上的外部 Web 服务 URL 创建规则，请键入前端池的 FQDN (例如，lyncpool01) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d67f2-125">在 " **内部发布详细信息** " 页上的 " \*\*路径 (可选) \*\*中，键入 **/\*** 作为要发布的文件夹的路径，然后选择 **" 转发原始主机标头 "**。</span><span class="sxs-lookup"><span data-stu-id="d67f2-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="d67f2-126">在“公共名称细节”\*\*\*\* 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d67f2-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d67f2-127">在“接受请求”\*\*\*\* 下，选择“此域名”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d67f2-128">在 " **公用名称**" 中，键入 **lyncdiscover.。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="d67f2-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="d67f2-129"> (外部自动发现服务 URL) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-129">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="d67f2-130">如果要为前端池上的外部 Web 服务 URL 创建规则，请在前端池上键入外部 Web 服务的 FQDN (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-130">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="d67f2-131">在 " **路径**" 中，键入 **/\*** 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-131">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d67f2-132">在“选择 Web 侦听器”\*\*\*\* 页上的“Web 侦听器”\*\*\*\* 中，选择具有已更新的公共证书的现有 SSL 侦听器。</span><span class="sxs-lookup"><span data-stu-id="d67f2-132">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="d67f2-133">在“身份验证委派”\*\*\*\* 页上，选择“无委派，但是客户端可以直接进行身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-133">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="d67f2-134">在“用户集”\*\*\*\* 页上，选择“所有用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-134">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d67f2-135">在“正在完成新建 Web 发布规则向导”\*\*\*\* 页上，确认 Web 发布规则设置正确，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-135">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d67f2-136">在 Web 发布规则的 Forefront TMG 列表中，双击您刚添加的新规则以打开“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-136">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d67f2-137">在“收件人”\*\*\*\* 选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d67f2-137">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="d67f2-138">选择“转发原始主机头而不是实际主机头”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-138">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="d67f2-139">选择“使请求显示为来自 Forefront TMG 计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-139">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="d67f2-140">在“桥接”\*\*\*\* 选项卡上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="d67f2-140">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d67f2-141">选择“Web 服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-141">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d67f2-142">选择“将请求重定向到 HTTP 端口”\*\*\*\*，并键入 **8080** 作为端口号。</span><span class="sxs-lookup"><span data-stu-id="d67f2-142">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d67f2-143">选择“将请求重定向到 SSL 端口”\*\*\*\*，然后键入端口号 **4443**。</span><span class="sxs-lookup"><span data-stu-id="d67f2-143">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="d67f2-144">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-144">Click **OK**.</span></span>

18. <span data-ttu-id="d67f2-145">在详细信息窗格中，单击“应用”\*\*\*\*，以保存所做的更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="d67f2-145">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="d67f2-146">单击“测试规则”\*\*\*\* 以验证是否正确设置了新规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-146">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="d67f2-147">修改现有 Web 发布规则以添加外部自动发现 SAN 和 URL</span><span class="sxs-lookup"><span data-stu-id="d67f2-147">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="d67f2-148">单击“开始”\*\*\*\*，依次指向“程序”\*\*\*\*、“Microsoft Forefront TMG”\*\*\*\*，然后单击“Forefront TMG 管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-148">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d67f2-149">您将对您拥有的每个发布规则和侦听器重复进行此修改。</span><span class="sxs-lookup"><span data-stu-id="d67f2-149">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="d67f2-150">通常情况下，这将是前端池的一个规则和侦听器，另一个是可选控制器或控制器池（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="d67f2-150">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="d67f2-p108">在左窗格中展开“服务器名称”\*\*\*\*，右键单击“防火墙策略”\*\*\*\*，再单击适用的规则。在“任务”\*\*\*\* 选项卡上，单击“编辑所选规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="d67f2-153">在“公共名称”\*\*\*\* 选项卡上的“此规则应用于”\*\*\*\* 中，选择“以下网站的请求”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-153">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="d67f2-154">单击“添加”\*\*\*\*，键入新的 Autodiscover 网站的名称（例如，“lyncdiscover.contoso.com”），然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-154">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="d67f2-p109">在“侦听器”\*\*\*\* 选项卡上，单击“选择证书”\*\*\*\* 并指定具有添加的自动发现 SAN 条目的新证书。关闭侦听器和 Web 发布属性。</span><span class="sxs-lookup"><span data-stu-id="d67f2-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="d67f2-157">在细节窗格中，单击“应用”\*\*\*\*，以保存所做的更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="d67f2-157">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="d67f2-158">单击“测试规则”\*\*\*\* 以验证是否正确设置了新规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-158">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="d67f2-159">为端口 80 创建 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="d67f2-159">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="d67f2-160">单击“开始”\*\*\*\*，依次指向“程序”\*\*\*\*、“Microsoft Forefront TMG”\*\*\*\*，然后单击“Forefront TMG 管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-160">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d67f2-161">在左窗格中，展开“服务器名称”\*\*\*\*，右键单击“防火墙策略”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“网站发布规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-161">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d67f2-162">在“欢迎使用新建 Web 发布规则向导”\*\*\*\* 页上，为新的发布规则键入一个显示名称（例如，Lync Autodiscover (HTTP)）。</span><span class="sxs-lookup"><span data-stu-id="d67f2-162">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="d67f2-163">在“选择规则操作”\*\*\*\* 页上，选择“允许”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-163">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d67f2-164">在“发布类型”\*\*\*\* 页上，选择“发布单个网站或负载平衡器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-164">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d67f2-165">在“服务器连接安全性”\*\*\*\* 页上，选择“使用不安全的连接连接发布的 Web 服务器或服务器场”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-165">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d67f2-166">在 " **内部发布详细信息** " 页上的 " **内部站点名称**" 中，键入前端池的内部 Web 服务 FQDN (例如，lyncpool01) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-166">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d67f2-167">在 " **内部发布详细信息** " 页上的 " \*\*路径 (可选) \*\*中，键入 **/\*** 作为要发布的文件夹的路径，然后选择" **转发原始主机标头，而不是在内部站点名称 "字段中指定的主机头**。</span><span class="sxs-lookup"><span data-stu-id="d67f2-167">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="d67f2-168">在“公共名称细节”\*\*\*\* 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d67f2-168">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d67f2-169">在“接受请求”\*\*\*\* 下，选择“此域名”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-169">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d67f2-170">在 " **公用名称**" 中，键入 **lyncdiscover.。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="d67f2-170">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="d67f2-171"> (外部自动发现服务 URL) 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-171">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="d67f2-172">在 " **路径**" 中，键入 **/\*** 。</span><span class="sxs-lookup"><span data-stu-id="d67f2-172">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d67f2-173">在“选择 Web 侦听器”\*\*\*\* 页上的“Web 侦听器”\*\*\*\* 中，选择 Web 侦听器或使用新建 Web 侦听器定义向导新建一个 Web 侦听器。</span><span class="sxs-lookup"><span data-stu-id="d67f2-173">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="d67f2-174">在“身份验证委派”\*\*\*\* 页上，选择“无委派，并且客户端无法直接进行身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-174">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="d67f2-175">在“用户集”\*\*\*\* 页上，选择“所有用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-175">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d67f2-176">在“正在完成新建 Web 发布规则向导”\*\*\*\* 页上，确认 Web 发布规则设置正确，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-176">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d67f2-177">在 Web 发布规则的 Forefront TMG 列表中，双击您刚添加的新规则以打开“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-177">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d67f2-178">在“桥接”\*\*\*\* 选项卡上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="d67f2-178">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d67f2-179">选择“Web 服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-179">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d67f2-180">选择“将请求重定向到 HTTP 端口”\*\*\*\*，并键入 **8080** 作为端口号。</span><span class="sxs-lookup"><span data-stu-id="d67f2-180">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d67f2-181">确认未选中“将请求重定向到 SSL 端口”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-181">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="d67f2-182">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d67f2-182">Click **OK**.</span></span>

17. <span data-ttu-id="d67f2-183">在详细信息窗格中，单击“应用”\*\*\*\*，以保存所做的更改并更新配置。</span><span class="sxs-lookup"><span data-stu-id="d67f2-183">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="d67f2-184">单击“测试规则”\*\*\*\* 以验证是否正确设置了新规则。</span><span class="sxs-lookup"><span data-stu-id="d67f2-184">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="d67f2-185">确认未针对任何其他 Web 发布规则定义外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="d67f2-185">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d67f2-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d67f2-186">See Also</span></span>


[<span data-ttu-id="d67f2-187">为 Lync Server 2013 设置反向代理服务器</span><span class="sxs-lookup"><span data-stu-id="d67f2-187">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

