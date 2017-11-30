---
title: Compilare .NET Core dal codice sorgente
description: Informazioni su come compilare .NET Core e .NET Core CLI dal codice sorgente.
keywords: .NET, .NET Core, codice sorgente, compilazione
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8b49079c-6ede-429a-92d7-ecd2fda1ab0e
ms.openlocfilehash: b2e62074992432dc5ee1360e17f87c782685dc35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="11007-104">Compilare .NET Core dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="11007-104">Build .NET Core from source</span></span>

<span data-ttu-id="11007-105">La possibilità di compilare .NET Core dal relativo codice sorgente è importante per diversi motivi: rende più semplice il trasferimento di .NET Core sulle nuove piattaforme, abilita i contributi e le correzioni per il prodotto e consente la creazione di versioni personalizzate di .NET.</span><span class="sxs-lookup"><span data-stu-id="11007-105">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="11007-106">Questo articolo offre materiale sussidiario agli sviluppatori che vogliono compilare e distribuire le proprie versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="11007-106">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="11007-107">Compilare Common Language Runtime (CLR) dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="11007-107">Build the CLR from source</span></span>

<span data-ttu-id="11007-108">Il codice sorgente per .NET CoreCLR è reperibile [nel repository `dotnet/coreclr` su GitHub](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="11007-108">The source code for the .NET CoreCLR can be found in [the `dotnet/coreclr` repository on GitHub](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="11007-109">La compilazione attualmente dipende dai prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="11007-109">The build currently depends on the following prerequisites:</span></span>
* [<span data-ttu-id="11007-110">Git</span><span class="sxs-lookup"><span data-stu-id="11007-110">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="11007-111">CMake</span><span class="sxs-lookup"><span data-stu-id="11007-111">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="11007-112">Python</span><span class="sxs-lookup"><span data-stu-id="11007-112">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="11007-113">un compilatore C++.</span><span class="sxs-lookup"><span data-stu-id="11007-113">a C++ compiler.</span></span>

<span data-ttu-id="11007-114">Dopo aver installato questi prerequisiti è possibile compilare CLR effettuando una chiamata allo script di compilazione (`build.cmd` in Windows o `build.sh` in Linux e macOS) alla base del [repositori CoreCLR](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="11007-114">After you've installed these prerequisites are installed, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of [the CoreCLR repository](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="11007-115">L'installazione dei componenti varia in base al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="11007-115">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="11007-116">Vedere le istruzioni di compilazione per il sistema operativo specifico:</span><span class="sxs-lookup"><span data-stu-id="11007-116">See the build instructions for your specific OS:</span></span>

 * [<span data-ttu-id="11007-117">Windows</span><span class="sxs-lookup"><span data-stu-id="11007-117">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
 * [<span data-ttu-id="11007-118">Linux</span><span class="sxs-lookup"><span data-stu-id="11007-118">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
 * [<span data-ttu-id="11007-119">macOS</span><span class="sxs-lookup"><span data-stu-id="11007-119">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
 * [<span data-ttu-id="11007-120">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="11007-120">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md) 
 * [<span data-ttu-id="11007-121">NetBSD</span><span class="sxs-lookup"><span data-stu-id="11007-121">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="11007-122">Non esiste alcuna compilazione incrociata tra sistemi operativi (solo per ARM, che è basato su X64).</span><span class="sxs-lookup"><span data-stu-id="11007-122">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="11007-123">È necessario essere sulla piattaforma specifica per compilare quella piattaforma.</span><span class="sxs-lookup"><span data-stu-id="11007-123">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="11007-124">La compilazione ha due `buildTypes` principali:</span><span class="sxs-lookup"><span data-stu-id="11007-124">The build has two main `buildTypes`:</span></span>

 * <span data-ttu-id="11007-125">Debug (impostazione predefinita): compila il runtime con le ottimizzazioni minime e controlli di runtime aggiuntivi (asserzioni).</span><span class="sxs-lookup"><span data-stu-id="11007-125">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="11007-126">La riduzione del livello di ottimizzazione e i controlli aggiuntivi rallentano l'esecuzione di runtime, ma sono utili per il debug.</span><span class="sxs-lookup"><span data-stu-id="11007-126">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="11007-127">Questa è l'impostazione consigliata per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="11007-127">This is the recommended setting for development and testing environments.</span></span>
 * <span data-ttu-id="11007-128">Release: compila il runtime con le ottimizzazioni complete e senza i controlli di runtime aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="11007-128">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="11007-129">Si ottengono così prestazioni di runtime molto più veloci, ma la compilazione può richiedere un po' più di tempo e può essere difficile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="11007-129">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="11007-130">Passare `release` allo script di compilazione per selezionare questo tipo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="11007-130">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="11007-131">Inoltre, per impostazione predefinita la compilazione non solo crea gli eseguibili di runtime, ma compila anche tutti i test.</span><span class="sxs-lookup"><span data-stu-id="11007-131">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="11007-132">I test sono piuttosto numerosi e richiedono una quantità significativa di tempo che non è necessaria se si vuole solo sperimentare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="11007-132">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="11007-133">È possibile ignorare le compilazioni dei test aggiungendo l'argomento `skiptests` allo script di compilazione, come nell'esempio seguente (sostituire `.\build` con `./build.sh` nei computer Unix):</span><span class="sxs-lookup"><span data-stu-id="11007-133">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests 
```

<span data-ttu-id="11007-134">L'esempio precedente illustra come compilare la versione `Debug`, in cui sono abilitati i controlli della fase di sviluppo (asserzioni) e sono disabilitate le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="11007-134">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="11007-135">Per compilare la versione di rilascio (velocità completa), eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="11007-135">To build the release (full speed) flavor, do the following:</span></span>

```bat 
    .\build release skiptests
```

<span data-ttu-id="11007-136">Sono disponibili altre opzioni di compilazione se si esegue la compilazione con il qualificatore -?</span><span class="sxs-lookup"><span data-stu-id="11007-136">You can find more build options with build by using the -?</span></span> <span data-ttu-id="11007-137">o -help.</span><span class="sxs-lookup"><span data-stu-id="11007-137">or -help qualifier.</span></span>   

### <a name="using-your-build"></a><span data-ttu-id="11007-138">Uso della compilazione</span><span class="sxs-lookup"><span data-stu-id="11007-138">Using Your Build</span></span>

<span data-ttu-id="11007-139">La compilazione colloca tutti i file generati sotto la directory `bin` alla base dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="11007-139">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="11007-140">È presente una directory *bin\Log* che contiene i file di log generati durante la compilazione ed è particolarmente utile quando la compilazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="11007-140">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="11007-141">L'output effettivo viene inserito in una directory *bin\Product\[piattaforma]. [architettura CPU]. [tipo di compilazione]* , ad esempio *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="11007-141">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="11007-142">Benché l'output non elaborato della compilazione spesso sia utile, di solito interessano solo i pacchetti NuGet, che vengono inseriti nella sottodirectory `.nuget\pkg` della directory di output precedente.</span><span class="sxs-lookup"><span data-stu-id="11007-142">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="11007-143">Esistono due tecniche di base per l'uso del nuovo runtime:</span><span class="sxs-lookup"><span data-stu-id="11007-143">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="11007-144">**Usare dotnet.exe e NuGet per creare un'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="11007-144">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="11007-145">Vedere [Uso della compilazione](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) per istruzioni sulla creazione di un programma che usa il nuovo runtime con i pacchetti NuGet appena creati e l'interfaccia della riga di comando "dotnet" (CLI).</span><span class="sxs-lookup"><span data-stu-id="11007-145">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="11007-146">Questa tecnica è probabilmente il modo in cui gli sviluppatori non di runtime preferiscono usare il nuovo runtime.</span><span class="sxs-lookup"><span data-stu-id="11007-146">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>    

 2. <span data-ttu-id="11007-147">**Usare corerun.exe per eseguire un'applicazione con le DLL non in pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="11007-147">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="11007-148">Questo archivio definisce anche un host semplice denominato corerun.exe che NON accetta dipendenze in NuGet.</span><span class="sxs-lookup"><span data-stu-id="11007-148">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="11007-149">Si dovrà indicare all'host dove si ottengono le DLL necessarie in uso e raccogliere le DLL manualmente.</span><span class="sxs-lookup"><span data-stu-id="11007-149">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="11007-150">Questa tecnica viene usata da tutti i test nel [repository CoreCLR](https://github.com/dotnet/coreclr) ed è utile in un ciclo rapido di "modifica-compilazione-debug" locale, ad esempio per gli unit test preliminari.</span><span class="sxs-lookup"><span data-stu-id="11007-150">This technique is used by all the tests in [the CoreCLR repo](https://github.com/dotnet/coreclr), and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="11007-151">Vedere l'argomento relativo all'[esecuzione delle app .NET Core con CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) per informazioni dettagliate sull'uso di questa tecnica.</span><span class="sxs-lookup"><span data-stu-id="11007-151">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="11007-152">Compilare l'interfaccia della riga di comando dal codice sorgente</span><span class="sxs-lookup"><span data-stu-id="11007-152">Build the CLI from source</span></span>

<span data-ttu-id="11007-153">Il codice sorgente per l'interfaccia della riga di comando di .NET Core è reperibile [nell'archivio `dotnet/cli` su GitHub](https://github.com/dotnet/cli/).</span><span class="sxs-lookup"><span data-stu-id="11007-153">The source code for the .NET Core CLI can be found in [the `dotnet/cli` repository on GitHub](https://github.com/dotnet/cli/).</span></span>

<span data-ttu-id="11007-154">Per compilare l'interfaccia della riga di comando di .NET Core, i seguenti componenti devono essere installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="11007-154">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="11007-155">Windows e Linux:</span><span class="sxs-lookup"><span data-stu-id="11007-155">Windows & Linux:</span></span>
    - <span data-ttu-id="11007-156">git nel PERCORSO</span><span class="sxs-lookup"><span data-stu-id="11007-156">git on the PATH</span></span>
* <span data-ttu-id="11007-157">macOS:</span><span class="sxs-lookup"><span data-stu-id="11007-157">macOS:</span></span>
    - <span data-ttu-id="11007-158">git nel PERCORSO</span><span class="sxs-lookup"><span data-stu-id="11007-158">git on the PATH</span></span>
    - <span data-ttu-id="11007-159">Xcode</span><span class="sxs-lookup"><span data-stu-id="11007-159">Xcode</span></span>
    - <span data-ttu-id="11007-160">Openssl</span><span class="sxs-lookup"><span data-stu-id="11007-160">OpenSSL</span></span>

<span data-ttu-id="11007-161">Per compilare, eseguire `build.cmd` in Windows o `build.sh` in Linux e macOS dalla radice.</span><span class="sxs-lookup"><span data-stu-id="11007-161">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="11007-162">Per non eseguire i test, eseguire `build.cmd /t:Compile` o `./build.sh /t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="11007-162">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="11007-163">Per compilare l'interfaccia della riga di comando in macOS Sierra, è necessario impostare la variabile di ambiente DOTNET_RUNTIME_ID eseguendo `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="11007-163">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="11007-164">Uso della compilazione</span><span class="sxs-lookup"><span data-stu-id="11007-164">Using your build</span></span>

<span data-ttu-id="11007-165">Usare l'eseguibile `dotnet` da *artifacts/{os}-{arch}/stage2* per provare l'interfaccia della riga di comando appena creata.</span><span class="sxs-lookup"><span data-stu-id="11007-165">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="11007-166">Per usare l'output della compilazione quando si chiama `dotnet` dalla console corrente, è anche possibile aggiungere *artifacts/{os}-{arch}/stage2* al PERCORSO.</span><span class="sxs-lookup"><span data-stu-id="11007-166">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="11007-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11007-167">See also</span></span>

* [<span data-ttu-id="11007-168">.NET Core Common Language Runtime (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="11007-168">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="11007-169">Guida per sviluppatori di .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="11007-169">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="11007-170">Pacchetti di distribuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="11007-170">.NET Core distribution packaging</span></span>](./distribution-packaging.md)