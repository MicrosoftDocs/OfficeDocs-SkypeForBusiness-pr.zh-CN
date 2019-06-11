---
title: Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce954eff790bae6974f144360637d6061318d3d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="4a5e7-102">Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值</span><span class="sxs-lookup"><span data-stu-id="4a5e7-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5e7-103">_**主题上次修改时间:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="4a5e7-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="4a5e7-104">如果你熟悉在所有 Windows 版本 (或你熟悉 MS-DOS) 中找到的命令窗口, 则在学习如何使用 Windows PowerShell 时, 你将开始使用一个头部。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="4a5e7-105">在 "命令" 窗口中, 键入命令并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="4a5e7-106">在响应中, 计算机运行一个命令或一个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="4a5e7-107">例如, 若要返回有关当前目录中的所有文件和文件夹的信息, 请在命令提示符处键入此命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

    dir

<span data-ttu-id="4a5e7-108">然后, 你将返回有关当前目录中的所有文件和文件夹的信息:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="4a5e7-109">当您只键入命令的名称或可执行文件时, 这就是结果的一个示例。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="4a5e7-110">但是, 从命令窗口中运行的许多命令也都接受*参数*。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="4a5e7-111">参数是传递给命令的附加信息部分, 用于修改命令的行为。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="4a5e7-112">例如, 如果你只想查看当前目录中的文件和文件夹的名称, 而不是其他信息, 如文件或文件夹的大小, 或者文件夹或文件夹的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="4a5e7-113">在这种情况下, 当运行 dir 命令时, 将附加 **/b**参数:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

    dir /b

<span data-ttu-id="4a5e7-114">如果包含 **/b**参数, **dir**命令仅返回在当前目录中找到的文件夹和文件的名称:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

<span data-ttu-id="4a5e7-115">在前面的命令中, **/b**参数是将返回的数据限制为文件和文件夹名称所需的唯一信息。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="4a5e7-116">使用命令行命令时, 通常会出现这种情况: 只需更改命令的行为即可使用参数。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="4a5e7-117">(也就是说, 你包含 **/b**参数以隐藏其他信息, 或者排除 **/b**参数以显示额外信息。)但是, 在其他情况下, 必须指定*参数值*。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="4a5e7-118">参数值是传递给参数本身的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="4a5e7-119">例如, **/o**参数使你可以指定你希望 dir 命令对返回的数据进行排序的方式。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="4a5e7-120">在其他选项中, 你可以使用参数值**e**按文件扩展名或参数值**s**进行排序, 以按文件大小排序。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="4a5e7-121">例如, 此命令按文件扩展名对返回的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="4a5e7-122">注意 **/o**参数后紧跟的参数值**e**的包含方式:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

    dir /oe

<span data-ttu-id="4a5e7-123">使用我们的示例文件夹, 返回的数据将如下所示, 文件扩展名按字母顺序排序:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="4a5e7-124">或者, 帮助准确确定我们所谈论的内容:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

<span data-ttu-id="4a5e7-125">设定.</span><span class="sxs-lookup"><span data-stu-id="4a5e7-125">setup.</span></span> <span data-ttu-id="4a5e7-126">**首**</span><span class="sxs-lookup"><span data-stu-id="4a5e7-126">**doc**</span></span>  
<span data-ttu-id="4a5e7-127">RHDSetup.</span><span class="sxs-lookup"><span data-stu-id="4a5e7-127">RHDSetup.</span></span> <span data-ttu-id="4a5e7-128">**执行**</span><span class="sxs-lookup"><span data-stu-id="4a5e7-128">**exe**</span></span>  
<span data-ttu-id="4a5e7-129">pldok.</span><span class="sxs-lookup"><span data-stu-id="4a5e7-129">pldok.</span></span> <span data-ttu-id="4a5e7-130">**先**</span><span class="sxs-lookup"><span data-stu-id="4a5e7-130">**log**</span></span>

<span data-ttu-id="4a5e7-131">虽然 Windows PowerShell 使用不同术语, 但使用 Windows PowerShell 的基本方法与使用命令窗口相同: 你可以键入命令, 根据需要包含参数和参数值, 然后按 ENTER 执行这些命令。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-131">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="4a5e7-132">但是, 如所述, Windows PowerShell 使用的术语不同于命令外壳使用的术语。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-132">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="4a5e7-133">在 Windows PowerShell 中, 你执行的命令称为*cmdlet*。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-133">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="4a5e7-134">反过来, 传递给 cmdlet 的参数称为*参数*, 传递给参数的值称为*参数值*。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-134">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="4a5e7-135">前面的定义将稍加简化。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-135">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="4a5e7-136">Cmdlet 实质上是一个迷你应用程序, 只能从 Windows PowerShell 环境内运行。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-136">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="4a5e7-137">但是, 你也可以从 Windows PowerShell 内部运行其他命令和应用程序, 包括可以从命令窗口运行的大多数命令和应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-137">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="4a5e7-138">例如, 如果要从 Windows PowerShell 内部启动记事本, 只需键入以下内容, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-138">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

    notepad.exe

<span data-ttu-id="4a5e7-139">但是, 当需要管理 Skype for Business Online 时, 大多数管理员将依靠 Windows PowerShell cmdlet 来执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-139">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="4a5e7-140">在时, 有很少的其他类型的命令或应用程序可用于管理 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-140">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="4a5e7-141">有时, 可以使用 Skype for Business Online cmdlet, 无需任何其他参数 (如有说明, 参数称为 Windows PowerShell 中的参数)。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-141">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="4a5e7-142">例如, 以下命令调用[CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet, 不带任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-142">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="4a5e7-143">该命令将返回有关您的所有 Skype for Business Online 用户的信息:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-143">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="4a5e7-144">但是, 大多数 Skype for Business Online cmdlet 也接受参数 (和参数值)。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-144">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="4a5e7-145">请考虑以下命令:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-145">Consider the following command:</span></span>

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

<span data-ttu-id="4a5e7-146">此命令包括三个部分:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-146">This command consists of three parts:</span></span>

  - <span data-ttu-id="4a5e7-147">Cmdlet **CsOnlineUser**。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-147">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="4a5e7-148">标识参数。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-148">The Identity parameter.</span></span> <span data-ttu-id="4a5e7-149">请注意, 在 Windows PowerShell 中, 参数始终以短划线 (-) 开头。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-149">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="4a5e7-150">这意味着, 对于此同一 cmdlet, 将使用以下语法指示 UnassignedUser 参数:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-150">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
        -UnassignedUser
    
    <span data-ttu-id="4a5e7-151">这一点非常有用, 不仅是因为参数必须以短划线开头, 而且也是因为它不同于命令窗口, 其中参数是使用正斜杠 (/) 开头的:</span><span class="sxs-lookup"><span data-stu-id="4a5e7-151">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ``` 
    /b
    ```

  - <span data-ttu-id="4a5e7-152">参数值**kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-152">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="4a5e7-153">该命令 (顺便说一下) 将返回有关特定用户的信息: kenmyer@litwareinc.com 标识的用户。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-153">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4a5e7-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a5e7-154">See Also</span></span>


<span data-ttu-id="4a5e7-155">[Windows PowerShell 和 Skype for Business Online 简介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4a5e7-155">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

