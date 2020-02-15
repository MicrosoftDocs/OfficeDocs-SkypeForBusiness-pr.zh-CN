---
title: Lync Server 2013：设置 XMPP 联合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6cbe8db6b432f8e837e110875881e86adab9c51
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f5e66-102">在 Lync Server 2013 中设置 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="f5e66-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e66-103">_**上次修改的主题：** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="f5e66-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="f5e66-104">若要在边缘服务器上部署 XMPP 代理，您必须为 XMPP 联盟配置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="f5e66-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="f5e66-105">为此，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f5e66-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="f5e66-106">设置 XMPP 联合</span><span class="sxs-lookup"><span data-stu-id="f5e66-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="f5e66-107">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 部署向导的计算机。</span><span class="sxs-lookup"><span data-stu-id="f5e66-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f5e66-108">在前端服务器上，打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="f5e66-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="f5e66-109">单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="f5e66-110">单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-110">Click Run Again.</span></span>

3.  <span data-ttu-id="f5e66-p103">在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="f5e66-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="f5e66-p104">在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="f5e66-p105">在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="f5e66-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="f5e66-122">在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”旁边的“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f5e66-123">如果您是首次部署边缘服务器，您将看到“运行”而非“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="f5e66-124">在“可用的证书任务”页上，单击“创建新的证书请求”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="f5e66-125">在“证书请求”页上，单击“外部边缘证书”。</span><span class="sxs-lookup"><span data-stu-id="f5e66-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="f5e66-126">在“延迟的请求或即时请求”页上，选中“立即准备请求，但是稍后发送”复选框。</span><span class="sxs-lookup"><span data-stu-id="f5e66-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="f5e66-127">在 "证书请求文件" 页上，键入要将请求保存到的文件的完整路径和文件名（例如，c：\\cert\_外部\_edge）。</span><span class="sxs-lookup"><span data-stu-id="f5e66-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="f5e66-128">在“指定替代证书模板”页上，要使用除默认 WebServer 模板之外的模板，请选中“对选定的证书颁发机构使用替代证书模板”复选框。</span><span class="sxs-lookup"><span data-stu-id="f5e66-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="f5e66-129">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5e66-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="f5e66-130">在“友好名称”中，键入证书的显示名称</span><span class="sxs-lookup"><span data-stu-id="f5e66-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="f5e66-131">在“位长度”中，指定位长度（通常为默认值“2048”）。</span><span class="sxs-lookup"><span data-stu-id="f5e66-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="f5e66-132">验证是否选中了“将证书私钥标记为可导出”复选框。</span><span class="sxs-lookup"><span data-stu-id="f5e66-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="f5e66-133">在“组织信息”页上，键入组织和组织单位（例如，分部或部门）的名称</span><span class="sxs-lookup"><span data-stu-id="f5e66-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="f5e66-134">在“地理信息”页上，指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="f5e66-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="f5e66-135">在“使用者名称/使用者替代名称”页上，将显示向导自动填充的信息。</span><span class="sxs-lookup"><span data-stu-id="f5e66-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="f5e66-136">如果需要其他使用者替代名称，可以在接下来的两个步骤中指定</span><span class="sxs-lookup"><span data-stu-id="f5e66-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="f5e66-137">在 "使用者替代名称（San）的 SIP 域设置" 页上，选中 "域" 复选框以添加 sip。\<sipdomain\>条目到 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="f5e66-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="f5e66-138">在 "配置其他使用者替换名称" 页上，指定所需的其他任何其他主题替代名称</span><span class="sxs-lookup"><span data-stu-id="f5e66-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f5e66-p107">如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。</span><span class="sxs-lookup"><span data-stu-id="f5e66-p107">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="f5e66-141">在“请求摘要”页上，检查要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="f5e66-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="f5e66-142">在命令运行完后，您可以“查看日志”，或单击“下一步”继续操作。</span><span class="sxs-lookup"><span data-stu-id="f5e66-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="f5e66-143">在“证书请求文件”页上，您可以通过单击“查看”来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”退出证书向导。</span><span class="sxs-lookup"><span data-stu-id="f5e66-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="f5e66-144">复制请求文件并提交至公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="f5e66-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="f5e66-p108">在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：</span><span class="sxs-lookup"><span data-stu-id="f5e66-p108">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="f5e66-147">若要为 XMPP 联盟配置 DNS，请将以下 SRV 记录添加到外部 DNS\_： XMPP-server。\_tcp。\<域名 SRV 记录将解析为边缘服务器的访问边缘 FQDN，端口值为\> 5269。</span><span class="sxs-lookup"><span data-stu-id="f5e66-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="f5e66-148">此外，您还可以配置指向访问边缘服务器的 IP 地址的 "A" 主机记录（例如，xmpp.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="f5e66-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f5e66-149">如果您在多个站点中有边缘池，我们建议您为 XMPP 联合添加多个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="f5e66-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="f5e66-150">为组织中的每个边缘池添加一条 SRV 记录，并为每个 SRV 记录指定不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="f5e66-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="f5e66-151">在运行所有边缘池时，XMPP 请求将由具有第一个优先级的边缘池进行处理，但如果该边缘池处于关闭状态，则不必添加新的 SRV 记录以重新获得 XMPP 联合功能。</span><span class="sxs-lookup"><span data-stu-id="f5e66-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="f5e66-152">通过在前端打开 Lync Server 命令行管理程序并键入以下内容，将新的外部访问策略配置为启用所有用户：</span><span class="sxs-lookup"><span data-stu-id="f5e66-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="f5e66-153">通过键入以下内容为外部用户启用 XMPP 访问：</span><span class="sxs-lookup"><span data-stu-id="f5e66-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="f5e66-154">在部署 XMPP 代理的边缘服务器上，打开命令提示符或 Windows PowerShell™命令行接口，并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5e66-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="f5e66-155">Command **netstat – ano**是网络统计命令、参数 **– ano**请求 netstat 显示所有连接和侦听端口、地址和端口均以数字形式显示，并且拥有的进程 ID 与每个连接相关联。</span><span class="sxs-lookup"><span data-stu-id="f5e66-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="f5e66-156">该字符**|** 将管道定义为下一个命令、 **findstr**或查找字符串。</span><span class="sxs-lookup"><span data-stu-id="f5e66-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="f5e66-157">作为参数传递给 findstr 的数字5269和23456指示 findstr 搜索针对字符串5269和23456的 netstat 的输出。</span><span class="sxs-lookup"><span data-stu-id="f5e66-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="f5e66-158">如果正确配置了 XMPP，则命令的结果应导致侦听和建立的连接，这两个连接都在外部（端口5269）和边缘服务器的内部（端口23456）接口上。</span><span class="sxs-lookup"><span data-stu-id="f5e66-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="f5e66-159">如果命令未在5269和23456上返回已建立或正在侦听的端口，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="f5e66-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="f5e66-160">XMPP 联合身份验证疑难解答</span><span class="sxs-lookup"><span data-stu-id="f5e66-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="f5e66-161">若要确定 XMPP 代理是否正在运行，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5e66-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="f5e66-162">以本地管理员组成员身份登录到运行 XMPP 代理服务的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="f5e66-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="f5e66-163">依次单击 "**开始**"、"**所有程序**"、"**管理工具**"、"**服务**</span><span class="sxs-lookup"><span data-stu-id="f5e66-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="f5e66-164">在 "服务" 中，找到 "Lync Server XMPP 转换网关代理"。</span><span class="sxs-lookup"><span data-stu-id="f5e66-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="f5e66-165">服务应处于 "**已启动**" 状态。</span><span class="sxs-lookup"><span data-stu-id="f5e66-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="f5e66-166">如果未启动，请单击工具栏中的 "**开始**" 图标。</span><span class="sxs-lookup"><span data-stu-id="f5e66-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="f5e66-167">图标以绿色的向右箭头形式显示。</span><span class="sxs-lookup"><span data-stu-id="f5e66-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="f5e66-168">确认服务已更改为 "**已启动**"。</span><span class="sxs-lookup"><span data-stu-id="f5e66-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="f5e66-169">如果已成功启动，请关闭**服务**并继续。</span><span class="sxs-lookup"><span data-stu-id="f5e66-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="f5e66-170">如果为止服务尚未成功启动，请从 "管理工具" 中打开事件查看器，并在 "**应用程序和服务日志**" 下的**Lync Server**部分中引用错误和警告。</span><span class="sxs-lookup"><span data-stu-id="f5e66-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="f5e66-171">在**Lync SERVER XMPP 转换网关**服务运行后，重新检查以前使用的 netstat 命令。</span><span class="sxs-lookup"><span data-stu-id="f5e66-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="f5e66-172">如果你未看到已建立或正在侦听的会话，请检查并确保在拓扑生成器中正确配置了**XMPP 联合路由**</span><span class="sxs-lookup"><span data-stu-id="f5e66-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="f5e66-173">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="f5e66-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="f5e66-174">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="f5e66-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="f5e66-175">在拓扑生成器中，选择 XMPP 联盟路由和审阅的网站，以确认**XMPP 联合**的**站点联合路由分配**将边缘服务器或边缘池显示为选定的 XMPP 联合路由分配。</span><span class="sxs-lookup"><span data-stu-id="f5e66-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="f5e66-176">如果路由分配不正确或未设置，请右键单击网站，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="f5e66-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="f5e66-177">选中 "XMPP 联盟" 复选框，然后选择正确的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="f5e66-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="f5e66-178">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="f5e66-178">Publish the topology.</span></span> <span data-ttu-id="f5e66-179">有关详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f5e66-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="f5e66-180">尽管不是必需的且通常不必要，但您可能需要重新启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="f5e66-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="f5e66-181">使用之前使用的 netstat 进程，确认边缘服务器正在侦听或已在端口5269和端口23456上建立了会话。</span><span class="sxs-lookup"><span data-stu-id="f5e66-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="f5e66-182">如果仍未看到预期会话，请检查事件查看器是否有可能导致通信问题的原因。</span><span class="sxs-lookup"><span data-stu-id="f5e66-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5e66-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5e66-183">See Also</span></span>


[<span data-ttu-id="f5e66-184">Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="f5e66-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="f5e66-185">在 Lync Server 2013 中管理 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="f5e66-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

