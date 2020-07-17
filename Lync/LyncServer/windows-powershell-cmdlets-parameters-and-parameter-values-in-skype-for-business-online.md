---
title: Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c7b04c428297e74d0910a42c4136bf4a06dacd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="383cb-102">Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值</span><span class="sxs-lookup"><span data-stu-id="383cb-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="383cb-103">_**上次修改的主题：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="383cb-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="383cb-104">如果你熟悉在所有 Windows 版本（或你熟悉 MS-DOS）中找到的命令窗口，那么学习如何使用 Windows PowerShell 时，你将获得良好的开端。</span><span class="sxs-lookup"><span data-stu-id="383cb-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="383cb-105">在命令窗口中，键入命令，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="383cb-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="383cb-106">在响应中，计算机运行一个命令或一个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="383cb-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="383cb-107">例如，若要返回有关当前目录中的所有文件和文件夹的信息，请在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="383cb-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="383cb-108">反过来，您将获得有关当前目录中的所有文件和文件夹的信息：</span><span class="sxs-lookup"><span data-stu-id="383cb-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

```console
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

<span data-ttu-id="383cb-109">当您只键入命令的名称或可执行文件时，这就是结果的一个示例。</span><span class="sxs-lookup"><span data-stu-id="383cb-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="383cb-110">但是，从命令窗口中运行的许多命令也都接受*参数*。</span><span class="sxs-lookup"><span data-stu-id="383cb-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="383cb-111">参数是传递给命令的附加信息片段，用于修改命令的行为。</span><span class="sxs-lookup"><span data-stu-id="383cb-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="383cb-112">例如，如果您只想查看当前目录中的文件和文件夹的名称，则没有其他信息（如文件或文件夹的大小）或文件夹或文件夹的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="383cb-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="383cb-113">在这种情况下，在运行 dir 命令时，将会追加 **/b**参数：</span><span class="sxs-lookup"><span data-stu-id="383cb-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="383cb-114">包含 **/b**参数时， **dir**命令仅报告在当前目录中找到的文件夹和文件的名称：</span><span class="sxs-lookup"><span data-stu-id="383cb-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

```console
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
```

<span data-ttu-id="383cb-115">在上面的命令中， **/b**参数是将返回的数据限制为文件和文件夹名称所需的唯一信息。</span><span class="sxs-lookup"><span data-stu-id="383cb-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="383cb-116">使用命令行命令时，通常会出现这种情况：只需使用该参数即可更改命令的行为。</span><span class="sxs-lookup"><span data-stu-id="383cb-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="383cb-117">（即，包含 **/b**参数可隐藏其他信息，或排除 **/b**参数以显示额外信息。）但在其他情况下，您必须指定*参数值*。</span><span class="sxs-lookup"><span data-stu-id="383cb-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="383cb-118">参数值是传递给参数本身的附加信息。</span><span class="sxs-lookup"><span data-stu-id="383cb-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="383cb-119">例如， **/o**参数使您能够指定您希望 dir 命令对返回的数据进行排序的方式。</span><span class="sxs-lookup"><span data-stu-id="383cb-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="383cb-120">在其他选项中，可以使用参数值**e**按文件扩展名或参数值**s**进行排序，以按文件大小排序。</span><span class="sxs-lookup"><span data-stu-id="383cb-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="383cb-121">例如，此命令按文件扩展名对返回的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="383cb-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="383cb-122">请注意 **/o**参数后紧跟的参数值**e**的包含方式：</span><span class="sxs-lookup"><span data-stu-id="383cb-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="383cb-123">使用我们的示例文件夹，返回的数据将如下所示，文件扩展名的字母顺序排序：</span><span class="sxs-lookup"><span data-stu-id="383cb-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

```console
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

<span data-ttu-id="383cb-124">或者，帮助你准确确定我们所讨论的内容：</span><span class="sxs-lookup"><span data-stu-id="383cb-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="383cb-125">虽然 Windows PowerShell 使用不同的术语，但使用 Windows PowerShell 的基本方法与使用命令窗口相同：您可以键入命令，根据需要包含参数和参数值，然后按 ENTER 执行这些命令。</span><span class="sxs-lookup"><span data-stu-id="383cb-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="383cb-126">但如前所述，Windows PowerShell 使用的术语与命令行管理程序使用的术语不同。</span><span class="sxs-lookup"><span data-stu-id="383cb-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="383cb-127">在 Windows PowerShell 中，所执行的命令称为*cmdlet*。</span><span class="sxs-lookup"><span data-stu-id="383cb-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="383cb-128">反过来，传递给 cmdlet 的参数称为*参数*，传递给参数的值称为*参数值*。</span><span class="sxs-lookup"><span data-stu-id="383cb-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="383cb-129">上述定义略有简化。</span><span class="sxs-lookup"><span data-stu-id="383cb-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="383cb-130">Cmdlet 实质上是最小化应用程序，只能从 Windows PowerShell 环境中运行。</span><span class="sxs-lookup"><span data-stu-id="383cb-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="383cb-131">但是，还可以从 Windows PowerShell 中运行其他命令和应用程序，包括可以从命令窗口运行的大多数命令和应用程序。</span><span class="sxs-lookup"><span data-stu-id="383cb-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="383cb-132">例如，如果要从 Windows PowerShell 中启动记事本，您只需键入以下内容，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="383cb-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="383cb-133">但是，在管理 Skype for Business Online 时，大多数管理员将依赖 Windows PowerShell cmdlet 来执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="383cb-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="383cb-134">同时，还可以使用许多其他类型的命令或应用程序来管理 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="383cb-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="383cb-135">有时，可以使用 Skype for Business Online cmdlet，而无需任何其他参数（如有说明，参数称为 Windows PowerShell 中的参数）。</span><span class="sxs-lookup"><span data-stu-id="383cb-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="383cb-136">例如，以下命令调用[get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet，而不带任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="383cb-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="383cb-137">该命令本身返回有关您的所有 Skype for Business Online 用户的信息：</span><span class="sxs-lookup"><span data-stu-id="383cb-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="383cb-138">但是，大多数 Skype for Business Online cmdlet 也接受参数（和参数值）。</span><span class="sxs-lookup"><span data-stu-id="383cb-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="383cb-139">请考虑以下命令：</span><span class="sxs-lookup"><span data-stu-id="383cb-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="383cb-140">此命令包含三个部分：</span><span class="sxs-lookup"><span data-stu-id="383cb-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="383cb-141">Cmdlet **get-csonlineuser**。</span><span class="sxs-lookup"><span data-stu-id="383cb-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="383cb-142">Identity 参数。</span><span class="sxs-lookup"><span data-stu-id="383cb-142">The Identity parameter.</span></span> <span data-ttu-id="383cb-143">请注意，在 Windows PowerShell 中，参数始终以短划线（-）开头。</span><span class="sxs-lookup"><span data-stu-id="383cb-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="383cb-144">这意味着，对于此相同的 cmdlet，将使用以下语法指示 UnassignedUser 参数：</span><span class="sxs-lookup"><span data-stu-id="383cb-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="383cb-145">这一点很有用，不仅因为参数必须以短划线开头，而且这与命令窗口不同，其中的参数是使用正斜杠（/）开头的：</span><span class="sxs-lookup"><span data-stu-id="383cb-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="383cb-146">参数值**kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="383cb-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="383cb-147">该命令将返回有关特定用户的信息： kenmyer@litwareinc.com 标识的用户。</span><span class="sxs-lookup"><span data-stu-id="383cb-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="383cb-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="383cb-148">See Also</span></span>


<span data-ttu-id="383cb-149">[Windows PowerShell 和 Skype for business Online 简介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="383cb-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

