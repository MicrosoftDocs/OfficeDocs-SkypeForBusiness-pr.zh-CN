---
title: Lync Server 2013：配置自定义状态状态
description: Lync Server 2013：配置自定义状态。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b277f096ff17ffa63615468ac9b4f21dead68e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557968"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="c1c68-103">在 Lync Server 2013 中配置自定义状态状态</span><span class="sxs-lookup"><span data-stu-id="c1c68-103">Configuring custom presence states in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1c68-104">_**上次修改的主题：** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="c1c68-104">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="c1c68-105">若要在 Lync 2013 中定义自定义状态状态，请创建 XML 自定义状态配置文件，然后使用 Lync Server 命令行管理程序 cmdlet **set-csclientpolicy** 或 **set-csclientpolicy** 参数 CustomStateURL 指定其位置。</span><span class="sxs-lookup"><span data-stu-id="c1c68-105">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="c1c68-106">配置文件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="c1c68-106">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="c1c68-107">自定义状态状态可配置为 "可用、忙碌和请勿打扰" 状态指示器。</span><span class="sxs-lookup"><span data-stu-id="c1c68-107">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="c1c68-108">Availability 属性确定哪个状态指标与自定义状态的状态文本相关联。</span><span class="sxs-lookup"><span data-stu-id="c1c68-108">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="c1c68-109">在本主题后面的示例中，从 Home 工作的状态文本将显示在绿色 () 状态指示器的右侧。</span><span class="sxs-lookup"><span data-stu-id="c1c68-109">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="c1c68-110">状态文本的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="c1c68-110">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="c1c68-111">最多可以添加四个自定义状态。</span><span class="sxs-lookup"><span data-stu-id="c1c68-111">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="c1c68-112">CustomStateURL 参数指定配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c1c68-112">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="c1c68-113">在 Lync 2013 中，SIP 高安全模式默认处于启用状态，因此您需要将自定义状态配置文件存储在启用了 HTTPS 的 web 服务器上。</span><span class="sxs-lookup"><span data-stu-id="c1c68-113">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="c1c68-114">否则，Lync 2013 客户端将无法连接到它。</span><span class="sxs-lookup"><span data-stu-id="c1c68-114">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="c1c68-115">例如，有效的地址为 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` 。</span><span class="sxs-lookup"><span data-stu-id="c1c68-115">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1c68-116">虽然不建议在生产环境中使用，但您可以通过使用 EnableSIPHighSecurityMode 注册表设置在客户端上禁用 SIP 高安全模式来测试位于非 HTTPS 文件共享上的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c1c68-116">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="c1c68-117">然后，您可以使用 CustomStateURL 注册表设置来指定配置文件的非 HTTPS 位置。</span><span class="sxs-lookup"><span data-stu-id="c1c68-117">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="c1c68-118">请注意，Lync 2013 采用 Lync 2010 注册表设置，但已更新注册表配置单元。</span><span class="sxs-lookup"><span data-stu-id="c1c68-118">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="c1c68-119">将创建注册表设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1c68-119">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c1c68-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="c1c68-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="c1c68-121">类型：DWORD</span><span class="sxs-lookup"><span data-stu-id="c1c68-121">Type: DWORD</span></span></P>
> <P><span data-ttu-id="c1c68-122">值数据：0</span><span class="sxs-lookup"><span data-stu-id="c1c68-122">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="c1c68-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="c1c68-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="c1c68-124">类型： String (REG_SZ) </span><span class="sxs-lookup"><span data-stu-id="c1c68-124">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="c1c68-125">值数据 (示例) ： file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="c1c68-125">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="c1c68-126">通过指定 XML 配置文件中 (LCID) 架构的一个或多个区域设置 ID 来本地化您的自定义状态状态。</span><span class="sxs-lookup"><span data-stu-id="c1c68-126">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="c1c68-127">本主题后面的示例演示如何本地化为英语-美国 (1033) 、挪威语 (1044) 、法语-法国 (1036) 和土耳其语 (1055) 。</span><span class="sxs-lookup"><span data-stu-id="c1c68-127">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="c1c68-128">有关 Lcid 的列表，请参阅由 Microsoft 分配的区域设置 Id <https://go.microsoft.com/fwlink/p/?linkid=157331> 。</span><span class="sxs-lookup"><span data-stu-id="c1c68-128">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="c1c68-129">将自定义状态状态添加到 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c1c68-129">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="c1c68-130">创建使用以下示例格式的 XML 配置文件：</span><span class="sxs-lookup"><span data-stu-id="c1c68-130">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="c1c68-131">将 XML 配置文件保存到启用了 HTTPS 的 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="c1c68-131">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="c1c68-132">在此示例中，文件被命名为 Presence.xml 并保存到该位置 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml 。</span><span class="sxs-lookup"><span data-stu-id="c1c68-132">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="c1c68-133">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1c68-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="c1c68-134">在 Lync Server 命令行管理程序中，使用类似如下的命令定义 XML 配置文件的位置：</span><span class="sxs-lookup"><span data-stu-id="c1c68-134">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="c1c68-135">使用 **set-csclientpolicy** cmdlet 可将此新策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c1c68-135">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="c1c68-136">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 和 [Grant set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="c1c68-136">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="c1c68-137">默认情况下，Lync Server 2013 &nbsp; 每三个小时更新一次客户端策略和设置。</span><span class="sxs-lookup"><span data-stu-id="c1c68-137">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="c1c68-138">如果要继续使用以前版本的组策略设置（如 CustomStateURL），Lync 2013 将识别这些设置（如果它们位于新策略注册表配置单元 ( # A0）。</span><span class="sxs-lookup"><span data-stu-id="c1c68-138">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="c1c68-139">但是，基于服务器的客户端策略优先。</span><span class="sxs-lookup"><span data-stu-id="c1c68-139">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

