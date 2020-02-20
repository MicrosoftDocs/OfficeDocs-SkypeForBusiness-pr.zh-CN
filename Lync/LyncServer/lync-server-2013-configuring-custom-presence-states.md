---
title: Lync Server 2013：配置自定义状态状态
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
ms.openlocfilehash: 304bd14e62f6ee9c629dfcf43e37cb8ee7880cb6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="c4448-102">在 Lync Server 2013 中配置自定义状态状态</span><span class="sxs-lookup"><span data-stu-id="c4448-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4448-103">_**上次修改的主题：** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="c4448-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="c4448-104">若要在 Lync 2013 中定义自定义状态状态，请创建 XML 自定义状态配置文件，然后使用 Lync Server 命令行管理程序 cmdlet **set-csclientpolicy**或**set-csclientpolicy**参数 CustomStateURL 指定其位置。</span><span class="sxs-lookup"><span data-stu-id="c4448-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="c4448-105">配置文件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="c4448-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="c4448-106">自定义状态状态可配置为 "可用、忙碌和请勿打扰" 状态指示器。</span><span class="sxs-lookup"><span data-stu-id="c4448-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="c4448-107">Availability 属性确定哪个状态指标与自定义状态的状态文本相关联。</span><span class="sxs-lookup"><span data-stu-id="c4448-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="c4448-108">在本主题后面的示例中，"在家中工作的状态文本" 显示在 "绿色（可用）" 状态指示器的右侧。</span><span class="sxs-lookup"><span data-stu-id="c4448-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="c4448-109">状态文本的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="c4448-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="c4448-110">最多可以添加四个自定义状态。</span><span class="sxs-lookup"><span data-stu-id="c4448-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="c4448-111">CustomStateURL 参数指定配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c4448-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="c4448-112">在 Lync 2013 中，SIP 高安全模式默认处于启用状态，因此您需要将自定义状态配置文件存储在启用了 HTTPS 的 web 服务器上。</span><span class="sxs-lookup"><span data-stu-id="c4448-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="c4448-113">否则，Lync 2013 客户端将无法连接到它。</span><span class="sxs-lookup"><span data-stu-id="c4448-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="c4448-114">例如，有效的地址为`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。</span><span class="sxs-lookup"><span data-stu-id="c4448-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4448-115">虽然不建议在生产环境中使用，但您可以通过使用 EnableSIPHighSecurityMode 注册表设置在客户端上禁用 SIP 高安全模式来测试位于非 HTTPS 文件共享上的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4448-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="c4448-116">然后，您可以使用 CustomStateURL 注册表设置来指定配置文件的非 HTTPS 位置。</span><span class="sxs-lookup"><span data-stu-id="c4448-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="c4448-117">请注意，Lync 2013 采用 Lync 2010 注册表设置，但已更新注册表配置单元。</span><span class="sxs-lookup"><span data-stu-id="c4448-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="c4448-118">将创建注册表设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4448-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c4448-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="c4448-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="c4448-120">类型：DWORD</span><span class="sxs-lookup"><span data-stu-id="c4448-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="c4448-121">值数据：0</span><span class="sxs-lookup"><span data-stu-id="c4448-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="c4448-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="c4448-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="c4448-123">类型： String （REG_SZ）</span><span class="sxs-lookup"><span data-stu-id="c4448-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="c4448-124">值数据（示例）： file://\\lspool or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="c4448-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="c4448-125">通过在 XML 配置文件中指定一个或多个区域设置 ID （LCID）架构来本地化您的自定义状态状态。</span><span class="sxs-lookup"><span data-stu-id="c4448-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="c4448-126">本主题后面的示例演示如何本地化为英语-美国（1033）、挪威语（1044）、法语-法国（1036）和土耳其语（1055）。</span><span class="sxs-lookup"><span data-stu-id="c4448-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="c4448-127">有关 Lcid 的列表，请参阅由 Microsoft 分配的区域设置<https://go.microsoft.com/fwlink/p/?linkid=157331>id。</span><span class="sxs-lookup"><span data-stu-id="c4448-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="c4448-128">将自定义状态状态添加到 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c4448-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="c4448-129">创建使用以下示例格式的 XML 配置文件：</span><span class="sxs-lookup"><span data-stu-id="c4448-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="c4448-130">将 XML 配置文件保存到启用了 HTTPS 的 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="c4448-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="c4448-131">在此示例中，该文件命名为 "web.xml" 并保存到该https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml位置。</span><span class="sxs-lookup"><span data-stu-id="c4448-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="c4448-132">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c4448-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="c4448-133">在 Lync Server 命令行管理程序中，使用类似如下的命令定义 XML 配置文件的位置：</span><span class="sxs-lookup"><span data-stu-id="c4448-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="c4448-134">使用**set-csclientpolicy** cmdlet 可将此新策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c4448-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="c4448-135">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)和[Grant set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="c4448-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="c4448-136">默认情况下，Lync Server&nbsp;2013 每三个小时更新一次客户端策略和设置。</span><span class="sxs-lookup"><span data-stu-id="c4448-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="c4448-137">如果要继续使用以前版本的组策略设置（如 CustomStateURL），Lync 2013 将识别这些设置（如果它们位于新策略注册表配置单元（HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync）中。</span><span class="sxs-lookup"><span data-stu-id="c4448-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="c4448-138">但是，基于服务器的客户端策略优先。</span><span class="sxs-lookup"><span data-stu-id="c4448-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

