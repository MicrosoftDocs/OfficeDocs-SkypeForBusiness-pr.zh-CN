---
title: 配置用户配置文件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a5ade3e0484d0b084f48ac75a2b13984706e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="80dee-102">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="80dee-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80dee-103">_**上次修改的主题：** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="80dee-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="80dee-104">Lync Server 2013 应力和性能工具包中包含的工具使您能够创建和配置可用于运行负载模拟的测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80dee-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="80dee-105">使用 Lync Server 2013 用户创建工具来创建用户。</span><span class="sxs-lookup"><span data-stu-id="80dee-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="80dee-106">（有关详细信息，请参阅[Create Users And Contacts](create-users-and-contacts.md)。）创建用户后，使用 Lync Server 2013 加载配置工具配置用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="80dee-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="80dee-107">运行 Lync Server 2013 加载配置工具</span><span class="sxs-lookup"><span data-stu-id="80dee-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="80dee-108">若要配置用户配置文件，请运行 Lync Server 2013 加载配置工具（UserProfileGenerator）并填写每个选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="80dee-109">对于需要运行模拟的每台客户端计算机，UserProfileGenerator 将生成一个目录。</span><span class="sxs-lookup"><span data-stu-id="80dee-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="80dee-110">每个客户端目录还附带一个脚本来启动 Lync Server 2013 压力和性能工具（LyncPerfTool）的所有实例。</span><span class="sxs-lookup"><span data-stu-id="80dee-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80dee-111">在 UserProfileGenerator 中指定的用户特定值必须与池的 Lync Server 2013 用户创建工具（UserProvisioningTool）中指定的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="80dee-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="80dee-112">在 "Lync Server 2013 加载配置" 工具的每个选项卡上填写字段，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="80dee-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="80dee-113">常见配置</span><span class="sxs-lookup"><span data-stu-id="80dee-113">Common Configuration</span></span>

<span data-ttu-id="80dee-114">下图显示了 Lync Server 2013 加载配置工具的 "**常见配置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="80dee-115">按照以下步骤中所述，填写 "**通用配置**" 选项卡的字段。</span><span class="sxs-lookup"><span data-stu-id="80dee-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="80dee-116">!["常见配置" 选项卡。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg ""常见配置" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="80dee-117">在 "**可用计算机数**" 中，键入或单击要用于运行 LyncPerfTool 的计算机的数量。</span><span class="sxs-lookup"><span data-stu-id="80dee-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="80dee-118">我们建议您对每个要模拟的4500用户拥有一台计算机。</span><span class="sxs-lookup"><span data-stu-id="80dee-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="80dee-119">如果您降低负载级别或仅使用可用功能的子集，该数字可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="80dee-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="80dee-120">（在 "**常规方案**" 选项卡上设置加载级别。）</span><span class="sxs-lookup"><span data-stu-id="80dee-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="80dee-121">在 "**用户名的前缀**" 中，键入用户用户名的前缀。</span><span class="sxs-lookup"><span data-stu-id="80dee-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="80dee-122">若要登录，统一资源标识符（URI）将为： UserPrefix\[User Start Index .。。（用户数-1）\]@User 域。</span><span class="sxs-lookup"><span data-stu-id="80dee-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="80dee-123">在 "**所有用户的密码**" 中，输入用于创建用户的密码。</span><span class="sxs-lookup"><span data-stu-id="80dee-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="80dee-124">如果将此字段留空，将使用用户名作为密码。</span><span class="sxs-lookup"><span data-stu-id="80dee-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="80dee-125">在 "**用户启动索引**" 中，单击或键入要配置的第一个用户的索引。</span><span class="sxs-lookup"><span data-stu-id="80dee-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="80dee-126">您可以为不同的负载类型或级别配置不同的范围，但必须针对要配置的区域运行 UserProfileGenerator 一次。</span><span class="sxs-lookup"><span data-stu-id="80dee-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="80dee-127">在 "**用户数**" 中，单击或键入要配置的用户总数。</span><span class="sxs-lookup"><span data-stu-id="80dee-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="80dee-128">在 "**用户域**" 中，键入用于 SIP URI 的域。</span><span class="sxs-lookup"><span data-stu-id="80dee-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="80dee-129">这用于构造每个用户登录到 Lync Server 2013 前端服务器或 Standard Edition server 的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="80dee-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="80dee-130">它可以不同于帐户域。</span><span class="sxs-lookup"><span data-stu-id="80dee-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="80dee-131">在 "**帐户域**" 中，键入 Active Directory 域服务域登录。</span><span class="sxs-lookup"><span data-stu-id="80dee-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="80dee-132">输入希望该工具在所有终结点/用户中记录的并发终结点的最大数量 **（每个实例的登录数）（每个实例）** 。</span><span class="sxs-lookup"><span data-stu-id="80dee-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="80dee-133">建议的速率为\<= 每秒 2/标准 SKU FE。</span><span class="sxs-lookup"><span data-stu-id="80dee-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="80dee-134">在 "**访问代理服务器" 或 "池 FQDN**" 中，键入您希望客户端连接到的服务器的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="80dee-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="80dee-135">如果用户在外部登录，请指定访问代理服务器。</span><span class="sxs-lookup"><span data-stu-id="80dee-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="80dee-136">如果用户是内部用户，请指定其池或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="80dee-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="80dee-137">在 "**端口**" 中，单击或键入您希望用户用于 SIP 的端口（默认值为5061）。</span><span class="sxs-lookup"><span data-stu-id="80dee-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="80dee-138">对于 "外部网络服务器设置"，请指定**访问代理服务器或池 FQDN**和**端口**。</span><span class="sxs-lookup"><span data-stu-id="80dee-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="80dee-139">这些设置仅用于外部终结点负载模拟。</span><span class="sxs-lookup"><span data-stu-id="80dee-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="80dee-140">常规方案</span><span class="sxs-lookup"><span data-stu-id="80dee-140">General Scenarios</span></span>

<span data-ttu-id="80dee-141">下图显示了 Lync Server 2013 加载配置工具的 "**常规方案**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="80dee-142">为要运行的每个常规方案配置加载级别和参数，或保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="80dee-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="80dee-143">!["常规方案" 选项卡。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg ""常规方案" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="80dee-144">在包含对等和会议的**即时消息**中，为加载级别指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80dee-145">所有字段（位置信息服务除外）的负载级别值被<STRONG>禁用</STRONG>、<STRONG>低</STRONG>、<STRONG>中</STRONG>、<STRONG>高</STRONG>和<STRONG>自定义</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="80dee-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="80dee-146">如果选择 "低"、"中"、"高" 或 "自定义"，则将为每个模态和客户端生成配置。</span><span class="sxs-lookup"><span data-stu-id="80dee-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="80dee-147">"高" 将导致为服务器生成最大支持的负载，"中" 对应于60% 的负载，"低" 对应于负载的30%。</span><span class="sxs-lookup"><span data-stu-id="80dee-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="80dee-148">在仅音频会议的**音频会议**中，为负载级别指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="80dee-149">对等呼叫在本主题后面的 "语音方案" 一节中介绍。</span><span class="sxs-lookup"><span data-stu-id="80dee-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="80dee-150">若要启用 "可查看"，请打开该模态的 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="80dee-151">在 "**应用程序共享**" 中，为加载级别指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="80dee-152">在包含数据会议的**数据协作**中，为负载级别指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="80dee-153">在 "**通讯组列表展开**" 中，为 "加载级别" 指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="80dee-154">您还必须单击 "**高级**" 按钮，然后使用您在 Lync Server 用户创建工具（UserProvisioningTool）的 "**通讯组列表**" 选项卡上配置的值来填充字段。</span><span class="sxs-lookup"><span data-stu-id="80dee-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="80dee-155">有关这些字段的详细信息，请参阅[创建用户和联系人](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="80dee-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="80dee-156">在**通讯簿 Web 查询**（即通讯簿查找服务（而不是通讯簿文件下载）中，为 "加载级别" 指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="80dee-157">若要启用通讯簿下载，请单击相应的 "**高级**" 按钮，然后将**EnableABSDownload**设置为 true。</span><span class="sxs-lookup"><span data-stu-id="80dee-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="80dee-158">在 "**响应组服务**" 中，为 "加载级别" 指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="80dee-159">您还必须单击相应的 "**高级**" 按钮，然后指定在设置响应组服务代理时已创建的响应组的 uri。</span><span class="sxs-lookup"><span data-stu-id="80dee-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="80dee-160">您必须指定至少一个响应组。</span><span class="sxs-lookup"><span data-stu-id="80dee-160">You must specify at least one response group.</span></span> <span data-ttu-id="80dee-161">使用分号分隔多个响应组。</span><span class="sxs-lookup"><span data-stu-id="80dee-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="80dee-162">将 RGSUriSuffixStartIndex 和 RGSUriSuffixEndIndex 更新为实际值。</span><span class="sxs-lookup"><span data-stu-id="80dee-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="80dee-163">在 "**位置信息服务**" 中，为 "加载级别" 选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="80dee-164">必须**启用**或**禁用**Location 信息服务的负载级别。</span><span class="sxs-lookup"><span data-stu-id="80dee-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dee-165">每个方案都有一个位于其旁边的 "<STRONG>高级</STRONG>" 按钮，以及一组启用方案变体的复选框。</span><span class="sxs-lookup"><span data-stu-id="80dee-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="80dee-166"><STRONG>临时方式生成</STRONG>将在一小时内创建的会议的模拟。</span><span class="sxs-lookup"><span data-stu-id="80dee-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="80dee-167"><STRONG>大型</STRONG>会议意味着将模拟大型会议方案。</span><span class="sxs-lookup"><span data-stu-id="80dee-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="80dee-168"><STRONG>外部</STRONG>方式也模拟外部用户。</span><span class="sxs-lookup"><span data-stu-id="80dee-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="80dee-169">这些按钮和复选框允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具（LyncPerfTool）的行为并使自定义成为可能。</span><span class="sxs-lookup"><span data-stu-id="80dee-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="80dee-170">对于 "<STRONG>常规方案</STRONG>" 选项卡（"位置信息服务" 除外）中的每个方案，如果 "负载级别" 的值是<STRONG>Custom</STRONG>，则将使用 "<STRONG>高级</STRONG>" 对话框中对应的字段计算会话速率。</span><span class="sxs-lookup"><span data-stu-id="80dee-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="80dee-171">字段名称不同，具体取决于方案，但字段说明将声明 "注意：仅在从下拉菜单中选择自定义项时，才使用此号码。"</span><span class="sxs-lookup"><span data-stu-id="80dee-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="80dee-172">通常情况下，<STRONG>高</STRONG>、<STRONG>中</STRONG>和<STRONG>低</STRONG>值将通过与所有方案之间的平衡的用户模型来更改每个模态的会话速率。</span><span class="sxs-lookup"><span data-stu-id="80dee-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="80dee-173">如果由于预期使用率不同而需要更改每个模态的负载级别，建议使用<STRONG>自定义</STRONG>对话速率。</span><span class="sxs-lookup"><span data-stu-id="80dee-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="80dee-174">语音方案</span><span class="sxs-lookup"><span data-stu-id="80dee-174">Voice Scenarios</span></span>

<span data-ttu-id="80dee-175">下图显示了 Lync Server 2013 加载配置工具的 "**语音方案**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="80dee-176">使用 "**语音方案**" 选项卡配置所有与语音相关的方案。</span><span class="sxs-lookup"><span data-stu-id="80dee-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="80dee-177">!["语音方案" 选项卡。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg ""语音方案" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="80dee-178">在**VoIP**中，单击 "**高级**" 按钮，然后为 " **PhoneAreaCode** " 和 " **LocationProfile** （拨号计划）" 字段提供值。</span><span class="sxs-lookup"><span data-stu-id="80dee-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="80dee-179">此外，还必须为**加载级别**指定值。</span><span class="sxs-lookup"><span data-stu-id="80dee-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="80dee-180">如果启用了**VoIP**和**UC/PSTN 网关**的负载级别，则将始终生成将模拟外部呼叫的公共交换电话网络（PSTN）到统一通信（UC）配置文件。</span><span class="sxs-lookup"><span data-stu-id="80dee-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="80dee-181">在**UC/PSTN 网关上**，为加载级别指定值。</span><span class="sxs-lookup"><span data-stu-id="80dee-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="80dee-182">如果选择 "**禁用**" 以外的加载级别，则必须通过单击 "中介服务器" 和 "PSTN" 下的 "**添加**" 按钮来为**PSTN 区域代码**提供一个值。</span><span class="sxs-lookup"><span data-stu-id="80dee-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="80dee-183">验证是否为该区号配置了路由。</span><span class="sxs-lookup"><span data-stu-id="80dee-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80dee-184">您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序验证语音路由配置。</span><span class="sxs-lookup"><span data-stu-id="80dee-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="80dee-185">在**会议助理**中，为加载级别指定值。</span><span class="sxs-lookup"><span data-stu-id="80dee-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="80dee-186">选择一个加载级别（"**禁用**" 除外）将启用 "**电话号码**" 字段。</span><span class="sxs-lookup"><span data-stu-id="80dee-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="80dee-187">输入要使用的自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="80dee-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="80dee-188">此外，单击 "**高级**" 按钮，然后为 " **LocationProfile** " 域指定一个值。</span><span class="sxs-lookup"><span data-stu-id="80dee-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="80dee-189">在 "**呼叫寄存服务**" 中，为**负载级别**指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="80dee-190">在**中介服务器和 PSTN**中，对于要使用的每个中介服务器，您必须具有单独的 PSTN 模拟器。</span><span class="sxs-lookup"><span data-stu-id="80dee-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="80dee-191">确定要用作模拟器的客户端之后，您需要将中介服务器配置为在您配置的 PSTN 模拟器端口上将呼叫路由到该计算机。</span><span class="sxs-lookup"><span data-stu-id="80dee-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="80dee-192">单击 "**添加**" 以配置中介服务器的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dee-193">每个方案都有一个位于它旁边的 "<STRONG>高级</STRONG>" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80dee-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="80dee-194">这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具（LyncPerfTool）的行为并启用自定义。</span><span class="sxs-lookup"><span data-stu-id="80dee-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="80dee-195">对于 "<STRONG>语音方案</STRONG>" 选项卡上的每个方案，如果 "<STRONG>加载级别</STRONG>" 的值是 "<STRONG>自定义</STRONG>"，则使用 "<STRONG>高级</STRONG>" 对话框中对应的字段计算会话速率。</span><span class="sxs-lookup"><span data-stu-id="80dee-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="80dee-196">字段名称不同，具体取决于方案，但字段说明将声明 "注意：仅在从下拉菜单中选择自定义项时，才使用此号码。"</span><span class="sxs-lookup"><span data-stu-id="80dee-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="80dee-197">到达</span><span class="sxs-lookup"><span data-stu-id="80dee-197">Reach</span></span>

<span data-ttu-id="80dee-198">在 Lync Server 2013 中，通过在前端服务器上安装的统一通信 Web API （UCWA）服务器支持会议方案，达到新的体验。</span><span class="sxs-lookup"><span data-stu-id="80dee-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="80dee-199">下图显示了 Lync Server 2013 加载配置工具的 "**访问**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="80dee-200">使用 "转至 **" 选项卡**可配置所有与相关的应用场景。</span><span class="sxs-lookup"><span data-stu-id="80dee-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="80dee-201">!["访问" 选项卡。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg ""访问" 选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="80dee-202">单击 "**常规到达设置**" 旁的 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80dee-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="80dee-203">将字段**UcwaTargetServerUrl**设置为控制器池虚拟 IP （VIP）或前端池 VIP。</span><span class="sxs-lookup"><span data-stu-id="80dee-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="80dee-204">在 "**应用程序共享**"、"**数据协作**" 和 " **IM**" 中，为 "**负载级别**" 选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="80dee-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dee-205">每个方案都有一个位于它旁边的 "<STRONG>高级</STRONG>" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80dee-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="80dee-206">这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具（LyncPerfTool）的行为并启用自定义。</span><span class="sxs-lookup"><span data-stu-id="80dee-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="80dee-207">对于每个访问方案，如果<STRONG>加载级别</STRONG>是<STRONG>自定义</STRONG>的，则使用<STRONG>ConversationsPerHour</STRONG>字段中指定的值，而不是默认值</span><span class="sxs-lookup"><span data-stu-id="80dee-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="80dee-208">使用 "**移动**" 选项卡配置所有移动性相关的方案。</span><span class="sxs-lookup"><span data-stu-id="80dee-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="80dee-209">![移动选项卡。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "移动选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="80dee-210">单击 "**移动性（UCWA）**" 旁边的 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80dee-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="80dee-211">将字段**UcwaTargetServerUrl**设置为控制器池虚拟 IP （VIP）或前端池 VIP。</span><span class="sxs-lookup"><span data-stu-id="80dee-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="80dee-212">在**状态和 P2P 即时消息\\音频**中，选择适当的**负载级别**值以启用移动方案模拟。</span><span class="sxs-lookup"><span data-stu-id="80dee-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dee-213">每个方案都有一个位于它旁边的 "<STRONG>高级</STRONG>" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80dee-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="80dee-214">这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具（LyncPerfTool）的行为并启用自定义。</span><span class="sxs-lookup"><span data-stu-id="80dee-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="80dee-215">对于每个访问方案，如果<STRONG>加载级别</STRONG>是<STRONG>自定义</STRONG>的，则使用<STRONG>ConversationsPerHour</STRONG>字段中指定的值，而不是默认值。</span><span class="sxs-lookup"><span data-stu-id="80dee-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="80dee-216">摘要</span><span class="sxs-lookup"><span data-stu-id="80dee-216">Summary</span></span>

<span data-ttu-id="80dee-217">下图显示了 Lync Server 2013 加载配置工具的 "**摘要**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80dee-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="80dee-218">![摘要 "选项卡。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要 "选项卡。")</span><span class="sxs-lookup"><span data-stu-id="80dee-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="80dee-219">"**摘要**" 选项卡指示要对每个方案使用的用户。</span><span class="sxs-lookup"><span data-stu-id="80dee-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="80dee-220">通过选中 "**启用自定义用户范围生成**" 复选框，然后双击表中具有您要自定义的**用户区域**的方案，可以手动配置用户号码范围。</span><span class="sxs-lookup"><span data-stu-id="80dee-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="80dee-221">检查（RunClient）在启动时添加登录延迟，以便在生成的批处理文件中包含延迟以与登录速率相对应。</span><span class="sxs-lookup"><span data-stu-id="80dee-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="80dee-222">这有助于在登录大量用户时防止服务器超载。</span><span class="sxs-lookup"><span data-stu-id="80dee-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="80dee-223">单击 "**生成文件**"，然后选择要在其中生成配置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="80dee-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="80dee-224">成功创建文件后，将显示与下图类似的对话框。</span><span class="sxs-lookup"><span data-stu-id="80dee-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="80dee-225">![确认已创建文件。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "确认已创建文件。")</span><span class="sxs-lookup"><span data-stu-id="80dee-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="80dee-226">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80dee-226">See Also</span></span>


[<span data-ttu-id="80dee-227">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="80dee-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
