---
uid: mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/adding-a-controller
title: "添加控制器 (VB) |Microsoft 文档"
author: Rick-Anderson
description: "本教程将教您构建使用 Microsoft Visual Web Developer 2010 Express Service Pack 1，这是一个 ASP.NET MVC Web 应用程序的基础知识..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/12/2011
ms.topic: article
ms.assetid: 741259e1-54ac-4f71-b4e8-2bd5560bb950
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/adding-a-controller
msc.type: authoredcontent
ms.openlocfilehash: 74113d76a74b1da27a7f9a33a13038a0c36ad036
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2017
---
<a name="adding-a-controller-vb"></a><span data-ttu-id="975ba-103">添加控制器 (VB)</span><span class="sxs-lookup"><span data-stu-id="975ba-103">Adding a Controller (VB)</span></span>
====================
<span data-ttu-id="975ba-104">通过[Rick Anderson](https://github.com/Rick-Anderson)</span><span class="sxs-lookup"><span data-stu-id="975ba-104">by [Rick Anderson](https://github.com/Rick-Anderson)</span></span>

> <span data-ttu-id="975ba-105">本教程将教您构建使用 Microsoft Visual Web Developer 2010 Express Service Pack 1，这是 Microsoft Visual Studio 的免费版本的 ASP.NET MVC Web 应用程序的基础知识。</span><span class="sxs-lookup"><span data-stu-id="975ba-105">This tutorial will teach you the basics of building an ASP.NET MVC Web application using Microsoft Visual Web Developer 2010 Express Service Pack 1, which is a free version of Microsoft Visual Studio.</span></span> <span data-ttu-id="975ba-106">在开始之前，请确保已安装下面列出的先决条件。</span><span class="sxs-lookup"><span data-stu-id="975ba-106">Before you start, make sure you've installed the prerequisites listed below.</span></span> <span data-ttu-id="975ba-107">你可以通过单击以下链接安装所有这些： [Web 平台安装程序](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)。</span><span class="sxs-lookup"><span data-stu-id="975ba-107">You can install all of them by clicking the following link: [Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack).</span></span> <span data-ttu-id="975ba-108">或者，你可以单独安装系统必备组件，使用以下链接：</span><span class="sxs-lookup"><span data-stu-id="975ba-108">Alternatively, you can individually install the prerequisites using the following links:</span></span>
> 
> - [<span data-ttu-id="975ba-109">Visual Studio Web Developer Express SP1 系统必备</span><span class="sxs-lookup"><span data-stu-id="975ba-109">Visual Studio Web Developer Express SP1 prerequisites</span></span>](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)
> - [<span data-ttu-id="975ba-110">ASP.NET MVC 3 Tools 更新</span><span class="sxs-lookup"><span data-stu-id="975ba-110">ASP.NET MVC 3 Tools Update</span></span>](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=MVC3)
> - <span data-ttu-id="975ba-111">[SQL Server Compact 4.0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)（运行时 + 工具支持）</span><span class="sxs-lookup"><span data-stu-id="975ba-111">[SQL Server Compact 4.0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)(runtime + tools support)</span></span>
> 
> <span data-ttu-id="975ba-112">如果你正在使用 Visual Studio 2010，而不 Visual Web Developer 2010，通过单击以下链接安装必备组件： [Visual Studio 2010 系统必备组件](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack)。</span><span class="sxs-lookup"><span data-stu-id="975ba-112">If you're using Visual Studio 2010 instead of Visual Web Developer 2010, install the prerequisites by clicking the following link: [Visual Studio 2010 prerequisites](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack).</span></span>
> 
> <span data-ttu-id="975ba-113">Visual Web Developer 项目与 VB.NET 的源代码是可以附带本主题。</span><span class="sxs-lookup"><span data-stu-id="975ba-113">A Visual Web Developer project with VB.NET source code is available to accompany this topic.</span></span> <span data-ttu-id="975ba-114">[下载 VB.NET 版本](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098)。</span><span class="sxs-lookup"><span data-stu-id="975ba-114">[Download the VB.NET version](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098).</span></span> <span data-ttu-id="975ba-115">如果你愿意 C#，切换到[C# 版本](../cs/adding-a-controller.md)本教程。</span><span class="sxs-lookup"><span data-stu-id="975ba-115">If you prefer C#, switch to the [C# version](../cs/adding-a-controller.md) of this tutorial.</span></span>


<span data-ttu-id="975ba-116">MVC 代表*模型-视图-控制器*。</span><span class="sxs-lookup"><span data-stu-id="975ba-116">MVC stands for *model-view-controller*.</span></span> <span data-ttu-id="975ba-117">MVC 是用于开发应用程序，以便每个部分具有单独的责任的模式：</span><span class="sxs-lookup"><span data-stu-id="975ba-117">MVC is a pattern for developing applications such that each part has a separate responsibility:</span></span>

- <span data-ttu-id="975ba-118">模型： 你的应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="975ba-118">Model: The data for your application.</span></span>
- <span data-ttu-id="975ba-119">视图： 你的应用程序将使用动态生成 HTML 响应的模板文件。</span><span class="sxs-lookup"><span data-stu-id="975ba-119">Views: The template files your application will use to dynamically generate HTML responses.</span></span>
- <span data-ttu-id="975ba-120">控制器： 处理应用程序，传入 URL 请求的类中检索模型数据，然后指定呈现对客户端的响应的视图模板。</span><span class="sxs-lookup"><span data-stu-id="975ba-120">Controllers: Classes that handle incoming URL requests to the application, retrieve model data, and then specify view templates that render a response to the client.</span></span>

<span data-ttu-id="975ba-121">我们将涵盖所有这些概念，在本教程中，向您展示如何使用它们来生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="975ba-121">We'll be covering all these concepts in this tutorial and show you how to use them to build an application.</span></span>

<span data-ttu-id="975ba-122">通过右键单击创建新的控制器*控制器*文件夹中的**解决方案资源管理器**，然后选择**添加控制器**。</span><span class="sxs-lookup"><span data-stu-id="975ba-122">Create a new controller by right-clicking the *Controllers* folder in **Solution Explorer** and then selecting **Add Controller**.</span></span>

<span data-ttu-id="975ba-123">[![AddController](adding-a-controller/_static/image2.png "AddController")](adding-a-controller/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="975ba-123">[![AddController](adding-a-controller/_static/image2.png "AddController")](adding-a-controller/_static/image1.png)</span></span>

<span data-ttu-id="975ba-124">新控制器命名&quot;HelloWorldController&quot;单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="975ba-124">Name your new controller &quot;HelloWorldController&quot; and click **Add**.</span></span>

<span data-ttu-id="975ba-125">[![2AddEmptyController](adding-a-controller/_static/image4.png "2AddEmptyController")](adding-a-controller/_static/image3.png)</span><span class="sxs-lookup"><span data-stu-id="975ba-125">[![2AddEmptyController](adding-a-controller/_static/image4.png "2AddEmptyController")](adding-a-controller/_static/image3.png)</span></span>

<span data-ttu-id="975ba-126">请注意，在**解决方案资源管理器**右侧，已为你创建一个新文件命名为*HelloWorldController.cs* ，以及是否在 IDE 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="975ba-126">Notice in **Solution Explorer** on the right that a new file has been created for you named *HelloWorldController.cs* and that the file is open in the IDE.</span></span>

<span data-ttu-id="975ba-127">在新`public class HelloWorldController`块中，创建类似于下面的代码的两个新方法。</span><span class="sxs-lookup"><span data-stu-id="975ba-127">Inside the new `public class HelloWorldController` block, create two new methods that look like the following code.</span></span> <span data-ttu-id="975ba-128">作为示例，我们将直接从控制器返回 HTML 的字符串。</span><span class="sxs-lookup"><span data-stu-id="975ba-128">We'll return a string of HTML directly from the controller as an example.</span></span>

[!code-vb[Main](adding-a-controller/samples/sample1.vb)]

<span data-ttu-id="975ba-129">名为你的控制器`HelloWorldController`和新方法命名为`Index`。</span><span class="sxs-lookup"><span data-stu-id="975ba-129">Your controller is named `HelloWorldController` and your new method is named `Index`.</span></span> <span data-ttu-id="975ba-130">运行应用程序 （按 F5 或 Ctrl + F5）。</span><span class="sxs-lookup"><span data-stu-id="975ba-130">Run the application (press F5 or Ctrl+F5).</span></span> <span data-ttu-id="975ba-131">一旦你的浏览器已启动，则追加&quot;HelloWorld&quot;地址栏中的路径。</span><span class="sxs-lookup"><span data-stu-id="975ba-131">Once your browser has started up, append &quot;HelloWorld&quot; to the path in the address bar.</span></span> <span data-ttu-id="975ba-132">(在我的计算机，它具有`http://localhost:43246/HelloWorld`) 你的浏览器将类似于下面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="975ba-132">(On my computer, it's `http://localhost:43246/HelloWorld`) Your browser will look like the screenshot below.</span></span> <span data-ttu-id="975ba-133">在上面的方法中，代码直接返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="975ba-133">In the method above, the code returned a string directly.</span></span> <span data-ttu-id="975ba-134">我们告知系统以仅返回一些 HTML，并且它未 ！</span><span class="sxs-lookup"><span data-stu-id="975ba-134">We told the system to just return some HTML, and it did!</span></span>

![](adding-a-controller/_static/image5.png)

<span data-ttu-id="975ba-135">ASP.NET MVC 调用另一个控制器类 （和其中的不同的操作方法），具体取决于传入的 URL。</span><span class="sxs-lookup"><span data-stu-id="975ba-135">ASP.NET MVC invokes different controller classes (and different action methods within them) depending on the incoming URL.</span></span> <span data-ttu-id="975ba-136">使用 ASP.NET MVC 的默认映射逻辑使用如下格式来控制调用哪些代码：</span><span class="sxs-lookup"><span data-stu-id="975ba-136">The default mapping logic used by ASP.NET MVC uses a format like this to control what code is invoked:</span></span>

`/[Controller]/[ActionName]/[Parameters]`

<span data-ttu-id="975ba-137">URL 的第一部分确定要执行的控制器类。</span><span class="sxs-lookup"><span data-stu-id="975ba-137">The first part of the URL determines the controller class to execute.</span></span> <span data-ttu-id="975ba-138">因此*/HelloWorld*映射到`HelloWorldController`类。</span><span class="sxs-lookup"><span data-stu-id="975ba-138">So */HelloWorld* maps to the `HelloWorldController` class.</span></span> <span data-ttu-id="975ba-139">URL 的第二部分确定要执行的类上的操作方法。</span><span class="sxs-lookup"><span data-stu-id="975ba-139">The second part of the URL determines the action method on the class to execute.</span></span> <span data-ttu-id="975ba-140">因此*/HelloWorld/索引*将导致`Index`方法`HelloWorldController`类执行。</span><span class="sxs-lookup"><span data-stu-id="975ba-140">So */HelloWorld/Index* would cause the `Index` method of the `HelloWorldController` class to execute.</span></span> <span data-ttu-id="975ba-141">请注意，我们仅必须访问*/HelloWorld*上面和`Index`时默认情况下使用方法。</span><span class="sxs-lookup"><span data-stu-id="975ba-141">Notice that we only had to visit */HelloWorld* above and the `Index` method was used by default.</span></span> <span data-ttu-id="975ba-142">这是因为方法名为`Index`是如果有一个未显式指定调用在控制器的默认方法。</span><span class="sxs-lookup"><span data-stu-id="975ba-142">This is because a method named `Index` is the default method that will be called on a controller if one is not explicitly specified.</span></span>

<span data-ttu-id="975ba-143">浏览到 `http://localhost:xxxx/HelloWorld/Welcome`。</span><span class="sxs-lookup"><span data-stu-id="975ba-143">Browse to `http://localhost:xxxx/HelloWorld/Welcome`.</span></span> <span data-ttu-id="975ba-144">`Welcome`方法将运行并返回字符串&quot;这是欢迎操作方法...&quot;.</span><span class="sxs-lookup"><span data-stu-id="975ba-144">The `Welcome` method runs and returns the string &quot;This is the Welcome action method...&quot;.</span></span> <span data-ttu-id="975ba-145">默认 MVC 映射是`/[Controller]/[ActionName]/[Parameters]`。</span><span class="sxs-lookup"><span data-stu-id="975ba-145">The default MVC mapping is `/[Controller]/[ActionName]/[Parameters]`.</span></span> <span data-ttu-id="975ba-146">对于此 URL，该控制器是`HelloWorld`和`Welcome`是方法。</span><span class="sxs-lookup"><span data-stu-id="975ba-146">For this URL, the controller is `HelloWorld` and `Welcome` is the method.</span></span> <span data-ttu-id="975ba-147">我们尚未使用`[Parameters]`尚未的 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="975ba-147">We haven't used the `[Parameters]` part of the URL yet.</span></span>

![](adding-a-controller/_static/image6.png)

<span data-ttu-id="975ba-148">让我们修改该示例略有，以便我们可以将中的某些参数信息从 URL 中传递给控制器 (例如， */HelloWorld/欢迎？ 名称 = Scott&amp;numtimes = 4*)。</span><span class="sxs-lookup"><span data-stu-id="975ba-148">Let's modify the example slightly so that we can pass some parameter information in from the URL to the controller (for example, */HelloWorld/Welcome?name=Scott&amp;numtimes=4*).</span></span> <span data-ttu-id="975ba-149">更改你`Welcome`方法以包括两个参数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="975ba-149">Change your `Welcome` method to include two parameters as shown below.</span></span> <span data-ttu-id="975ba-150">请注意，我们已使用 VB 可选参数功能，则指示`numTimes`参数应默认为 1，如果为该参数不传递任何值。</span><span class="sxs-lookup"><span data-stu-id="975ba-150">Note that we've used the VB optional parameter feature to indicate that the `numTimes` parameter should default to 1 if no value is passed for that parameter.</span></span>

[!code-vb[Main](adding-a-controller/samples/sample2.vb)]

<span data-ttu-id="975ba-151">运行你的应用程序，并浏览到`http://localhost:xxxx/HelloWorld/Welcome?name=Scott&numtimes=4` **。**</span><span class="sxs-lookup"><span data-stu-id="975ba-151">Run your application and browse to `http://localhost:xxxx/HelloWorld/Welcome?name=Scott&numtimes=4`**.**</span></span> <span data-ttu-id="975ba-152">你可以尝试不同的值`name`和`numtimes`。</span><span class="sxs-lookup"><span data-stu-id="975ba-152">You can try different values for `name` and `numtimes`.</span></span> <span data-ttu-id="975ba-153">系统会自动映射到你的方法中的参数来自你的地址栏中的查询字符串的命名的参数。</span><span class="sxs-lookup"><span data-stu-id="975ba-153">The system automatically maps the named parameters from your query string in the address bar to parameters in your method.</span></span>

![](adding-a-controller/_static/image7.png)

<span data-ttu-id="975ba-154">已在这些示例中这两个控制器执行 MVC 的 VC 部分 — 即视图和控制器工作。</span><span class="sxs-lookup"><span data-stu-id="975ba-154">In both these examples the controller has been doing the VC portion of MVC — that is the view and controller work.</span></span> <span data-ttu-id="975ba-155">控制器直接返回 HTML。</span><span class="sxs-lookup"><span data-stu-id="975ba-155">The controller is returning HTML directly.</span></span> <span data-ttu-id="975ba-156">通常，我们不希望直接返回 HTML，因为该按钮将变为非常麻烦的代码的控制器。</span><span class="sxs-lookup"><span data-stu-id="975ba-156">Ordinarily we don't want controllers returning HTML directly, since that becomes very cumbersome to code.</span></span> <span data-ttu-id="975ba-157">而是我们通常将使用单独的视图模板文件来帮助生成 HTML 响应。</span><span class="sxs-lookup"><span data-stu-id="975ba-157">Instead we'll typically use a separate view template file to help generate the HTML response.</span></span> <span data-ttu-id="975ba-158">让我们看一下如何我们可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="975ba-158">Let's look at how we can do this.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="975ba-159">[上一页](intro-to-aspnet-mvc-3.md)
[下一页](adding-a-view.md)</span><span class="sxs-lookup"><span data-stu-id="975ba-159">[Previous](intro-to-aspnet-mvc-3.md)
[Next](adding-a-view.md)</span></span>