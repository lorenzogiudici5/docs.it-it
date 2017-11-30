---
title: '&lt;deselezionare&gt; elemento per NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e91c3d9693cf656a8c56c82d1997f74c2b3d64c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5174e-102">\<Deselezionare > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="5174e-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5174e-103">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="5174e-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="5174e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5174e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5174e-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="5174e-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="5174e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Deselezionare >**</span><span class="sxs-lookup"><span data-stu-id="5174e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5174e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5174e-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="5174e-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="5174e-108">Attributes</span></span>

<span data-ttu-id="5174e-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5174e-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="5174e-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="5174e-110">Parent element</span></span>

|     | <span data-ttu-id="5174e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5174e-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="5174e-112">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="5174e-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="5174e-113">Definisce le impostazioni per le sezioni di configurazione personalizzate che utilizzano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi.</span><span class="sxs-lookup"><span data-stu-id="5174e-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5174e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5174e-114">Child elements</span></span>

<span data-ttu-id="5174e-115">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5174e-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5174e-116">Note</span><span class="sxs-lookup"><span data-stu-id="5174e-116">Remarks</span></span>

<span data-ttu-id="5174e-117">È possibile utilizzare il  **\<deselezionare >** elemento da rimuovere tutte le impostazioni dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5174e-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5174e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="5174e-118">Example</span></span>

<span data-ttu-id="5174e-119">In questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<deselezionare >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione di computer.</span><span class="sxs-lookup"><span data-stu-id="5174e-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5174e-120">Nel seguente codice di file di configurazione di computer viene dichiarata la sezione  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="5174e-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="5174e-121">Il seguente codice di file di configurazione dell'applicazione rimuove tutte le impostazioni di  **\<mySection >**.</span><span class="sxs-lookup"><span data-stu-id="5174e-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="5174e-122">L'applicazione non è possibile recuperare le impostazioni che sono state dichiarate nel nel  **\<mySection >** sezione del file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="5174e-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5174e-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5174e-123">Configuration file</span></span>

<span data-ttu-id="5174e-124">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5174e-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5174e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5174e-125">See also</span></span>

[<span data-ttu-id="5174e-126">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5174e-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)