---
title: Lync Server 2013：设置 XMPP 联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3941a-102">在 Lync Server 2013 中设置 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="3941a-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3941a-103">_**主题上次修改时间:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="3941a-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="3941a-104">若要在 Edge 服务器上部署 XMPP 代理, 必须为 XMPP 联盟配置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="3941a-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="3941a-105">若要执行此操作, 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="3941a-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="3941a-106">设置 XMPP 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="3941a-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="3941a-107">登录到安装了 Lync Server 部署向导的计算机, 作为 "域管理员" 组和 "RTCUniversalServerAdmins" 组的成员。</span><span class="sxs-lookup"><span data-stu-id="3941a-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3941a-108">在前端服务器上, 打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="3941a-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="3941a-109">单击 "安装或更新 Lync 服务器系统", 然后单击 "设置" 或 "删除 Lync Server 组件"。</span><span class="sxs-lookup"><span data-stu-id="3941a-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="3941a-110">再次单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="3941a-110">Click Run Again.</span></span>

3.  <span data-ttu-id="3941a-111">在 "安装 Lync 服务器组件" 中, 单击 "下一步"。</span><span class="sxs-lookup"><span data-stu-id="3941a-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="3941a-112">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="3941a-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3941a-113">部署完成后, 单击 "查看日志" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="3941a-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="3941a-114">单击 "完成" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="3941a-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="3941a-115">在边缘服务器上, 打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="3941a-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="3941a-116">单击 "安装或更新 Lync 服务器系统", 然后单击 "设置" 或 "删除 Lync Server 组件"。</span><span class="sxs-lookup"><span data-stu-id="3941a-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="3941a-117">再次单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="3941a-117">Click Run Again.</span></span>

5.  <span data-ttu-id="3941a-118">在 "安装 Lync 服务器组件" 中, 单击 "下一步"。</span><span class="sxs-lookup"><span data-stu-id="3941a-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="3941a-119">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="3941a-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3941a-120">部署完成后, 单击 "查看日志" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="3941a-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="3941a-121">单击 "完成" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="3941a-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="3941a-122">在边缘服务器上的 "部署向导" 中, 在 "步骤 3: 请求、安装或分配证书" 旁边, 再次单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="3941a-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="3941a-123">如果你是首次部署 Edge 服务器, 你将看到 "运行", 而不是再次运行。</span><span class="sxs-lookup"><span data-stu-id="3941a-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="3941a-124">在“可用的证书任务”页上，单击“创建新的证书请求”。</span><span class="sxs-lookup"><span data-stu-id="3941a-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="3941a-125">在 "证书请求" 页面上, 单击 "外部边缘证书"。</span><span class="sxs-lookup"><span data-stu-id="3941a-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="3941a-126">在 "延迟或立即请求" 页面上, 选中 "立即准备请求, 但稍后发送" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3941a-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="3941a-127">在 "证书请求文件" 页面上, 键入要保存请求的文件的完整路径和文件名 (例如, c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="3941a-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="3941a-128">在 "指定备用证书模板" 页面上, 若要使用默认 Web 台模板之外的模板, 请选中 "为所选证书颁发机构使用备用证书模板" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3941a-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="3941a-129">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3941a-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="3941a-130">在 "友好名称" 中, 键入证书的显示名称</span><span class="sxs-lookup"><span data-stu-id="3941a-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="3941a-131">在 "位长度" 中, 指定位长 (通常为默认值 2048)</span><span class="sxs-lookup"><span data-stu-id="3941a-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="3941a-132">验证已选中 "将证书私钥标记为可导出" 复选框</span><span class="sxs-lookup"><span data-stu-id="3941a-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="3941a-133">在 "组织信息" 页面上, 键入组织和组织单位的名称 (例如, "部门" 或 "部门")</span><span class="sxs-lookup"><span data-stu-id="3941a-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="3941a-134">在 "地理信息" 页面上, 指定位置信息</span><span class="sxs-lookup"><span data-stu-id="3941a-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="3941a-135">在 "主题名称/主题备用名称" 页面上, 将显示要由向导自动填充的信息。</span><span class="sxs-lookup"><span data-stu-id="3941a-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="3941a-136">如果需要其他主题备用名称, 请在接下来的两个步骤中进行指定</span><span class="sxs-lookup"><span data-stu-id="3941a-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="3941a-137">在 "主题备用名称 (San)" 页面上的 "SIP 域设置" 中, 选中 "域" 复选框以添加 SIP。\<sipdomain\>条目到 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="3941a-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="3941a-138">在 "配置其他主题备用名称" 页面上, 指定所需的任何其他主题备用名称</span><span class="sxs-lookup"><span data-stu-id="3941a-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="3941a-139">如果 XMPP 代理已安装, 则默认情况下会在 SAN 条目中填充域名 (如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="3941a-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="3941a-140">如果需要更多条目, 请在此步骤中添加这些条目。</span><span class="sxs-lookup"><span data-stu-id="3941a-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="3941a-141">在 "请求摘要" 页面上, 查看要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="3941a-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="3941a-142">命令完成运行后, 您可以查看日志, 或单击 "下一步" 继续。</span><span class="sxs-lookup"><span data-stu-id="3941a-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="3941a-143">在 "证书请求文件" 页面上, 您可以通过单击 "查看或退出证书向导" 查看生成的证书签名请求 (CSR) 文件, 方法是单击 "完成"。</span><span class="sxs-lookup"><span data-stu-id="3941a-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="3941a-144">将请求文件复制并提交到公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3941a-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="3941a-145">接收、导入和分配公共证书后, 必须停止并重新启动 Edge 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="3941a-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="3941a-146">可通过在 Lync Server 管理控制台中键入以下内容来执行此操作:</span><span class="sxs-lookup"><span data-stu-id="3941a-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. <span data-ttu-id="3941a-147">若要为 XMPP 联盟配置 DNS, 请将以下 SRV 记录添加到外部 DNS\_: XMPP-server。\_tcp。\<域名 SRV 记录将解析为 edge 服务器的访问边缘 FQDN, 其端口值为\> 5269。</span><span class="sxs-lookup"><span data-stu-id="3941a-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="3941a-148">此外, 您还可以配置一个指向访问边缘服务器的 IP 地址的 "A" 主机记录 (例如, xmpp.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="3941a-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3941a-149">如果你有多个网站中的 Edge 池, 我们建议你为 XMPP federation 添加多个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3941a-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="3941a-150">为组织中的每个边缘池添加 SRV 记录, 并为每个 SRV 记录提供不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="3941a-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="3941a-151">当所有边缘池都在运行时, XMPP 请求将由具有第一个优先级的边缘池进行处理, 但如果该边缘池停机, 则不必添加新的 SRV 记录即可重新获得 XMPP 联合功能。</span><span class="sxs-lookup"><span data-stu-id="3941a-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="3941a-152">通过在前端打开 Lync Server 管理外壳并键入以下内容, 将新的外部访问策略配置为启用所有用户:</span><span class="sxs-lookup"><span data-stu-id="3941a-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="3941a-153">通过键入以下内容为外部用户启用 XMPP 访问:</span><span class="sxs-lookup"><span data-stu-id="3941a-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="3941a-154">在部署 XMPP 代理的边缘服务器上, 打开命令提示符或 Windows PowerShell™命令行界面, 然后键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="3941a-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="3941a-155">Command **netstat-ano**是网络统计命令、参数 **-ano**请求 netstat 显示所有连接和侦听端口、地址和端口均以数字形式显示, 并且拥有的进程 ID 关联每个连接。</span><span class="sxs-lookup"><span data-stu-id="3941a-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="3941a-156">该字符**|** 定义管道到下一个命令、" **findstr**" 或 "查找" 字符串。</span><span class="sxs-lookup"><span data-stu-id="3941a-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="3941a-157">作为参数传递给 findstr 的数字5269和23456指示 findstr 搜索针对字符串5269和23456的 netstat 的输出。</span><span class="sxs-lookup"><span data-stu-id="3941a-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="3941a-158">如果 XMPP 配置正确, 则命令的结果应导致侦听和建立的连接在外部 (端口 5269) 和边缘服务器的内部 (端口 23456) 接口上。</span><span class="sxs-lookup"><span data-stu-id="3941a-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="3941a-159">如果命令未在5269和23456上返回已建立或侦听端口, 请检查以下内容:</span><span class="sxs-lookup"><span data-stu-id="3941a-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="3941a-160">XMPP 联盟疑难解答</span><span class="sxs-lookup"><span data-stu-id="3941a-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="3941a-161">若要确定 XMPP 代理是否正在运行, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="3941a-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="3941a-162">以本地管理员组的成员身份登录运行 XMPP 代理服务的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="3941a-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="3941a-163">依次单击 "**开始**"、"**所有程序**"、"**管理工具**"、"**服务**"</span><span class="sxs-lookup"><span data-stu-id="3941a-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="3941a-164">在 "服务" 中, 找到 "Lync Server XMPP 转换网关代理"。</span><span class="sxs-lookup"><span data-stu-id="3941a-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="3941a-165">服务应处于 "**已启动**" 状态。</span><span class="sxs-lookup"><span data-stu-id="3941a-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="3941a-166">如果未启动, 请单击工具栏中的 "**开始**" 图标。</span><span class="sxs-lookup"><span data-stu-id="3941a-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="3941a-167">图标显示为绿色的右箭头。</span><span class="sxs-lookup"><span data-stu-id="3941a-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="3941a-168">确认该服务已更改为 "已**启动**"。</span><span class="sxs-lookup"><span data-stu-id="3941a-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="3941a-169">如果它已成功启动, 请关闭**服务**并继续。</span><span class="sxs-lookup"><span data-stu-id="3941a-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="3941a-170">如果 ther 服务未成功启动, 请从 "管理工具" 打开事件查看器, 并在 "**应用程序和服务日志**" 下的**Lync Server**部分中参阅错误和警告。</span><span class="sxs-lookup"><span data-stu-id="3941a-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="3941a-171">在**Lync SERVER XMPP 转换网关**服务运行后, 重新检查以前使用的 netstat 命令。</span><span class="sxs-lookup"><span data-stu-id="3941a-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="3941a-172">如果你没有看到已建立或正在侦听的会话, 请检查并确保在拓扑结构生成器中正确配置了**XMPP 联合路线**</span><span class="sxs-lookup"><span data-stu-id="3941a-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="3941a-173">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="3941a-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="3941a-174">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="3941a-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="3941a-175">在拓扑生成器中, 选择 XMPP 联盟路线的网站并查看以确认**XMPP 联盟**的**站点联盟路由分配**是否将边缘服务器或边缘池显示为所选的 XMPP 联合路由分配。</span><span class="sxs-lookup"><span data-stu-id="3941a-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="3941a-176">如果路线分配不正确或未设置, 请右键单击该站点, 单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="3941a-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="3941a-177">选中 "XMPP 联盟" 复选框, 然后选择正确的 "边缘服务器" 或 "边缘池"。</span><span class="sxs-lookup"><span data-stu-id="3941a-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="3941a-178">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="3941a-178">Publish the topology.</span></span> <span data-ttu-id="3941a-179">有关详细信息, 请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="3941a-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="3941a-180">虽然不是必需的, 并且通常不必要, 但你可能需要重新启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3941a-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="3941a-181">使用以前使用的 netstat 进程, 确认 Edge 服务器正在侦听或已在端口5269和端口23456上建立了会话。</span><span class="sxs-lookup"><span data-stu-id="3941a-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="3941a-182">如果仍然看不到预期的会话, 请检查事件查看器是否有可能导致通信问题的原因。</span><span class="sxs-lookup"><span data-stu-id="3941a-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3941a-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3941a-183">See Also</span></span>


[<span data-ttu-id="3941a-184">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="3941a-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="3941a-185">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="3941a-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

