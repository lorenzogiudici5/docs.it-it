---
title: NuGet e librerie .NET
description: Procedure consigliate per la creazione di pacchetti con NuGet per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185622"
---
# <a name="nuget"></a>NuGet

NuGet è uno strumento di gestione pacchetti per l'ecosistema .NET e rappresenta il modo principale in cui gli sviluppatori individuano e acquisiscono librerie open source .NET. [NuGet.org](https://www.nuget.org/), un servizio gratuito fornito da Microsoft per l'hosting dei pacchetti NuGet, è l'host primario per i pacchetti NuGet pubblici, ma è possibile eseguire la pubblicazione in servizi NuGet personalizzati, come [MyGet](https://www.myget.org/) e [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Creare un pacchetto NuGet

Un pacchetto NuGet (`*.nupkg`) è un file ZIP che contiene gli assembly .NET e i metadati associati.

Ci sono due modi principali per creare un pacchetto NuGet. Il modo più recente e consigliato consiste nel creare un pacchetto da un progetto in stile SDK (file di progetto il cui contenuto inizia con `<Project Sdk="Microsoft.NET.Sdk">`). Destinazioni e assembly vengono aggiunti automaticamente al pacchetto e i metadati rimanenti vengono aggiunti al file MSBuild, ad esempio numero di versione e nome del pacchetto. La compilazione con il comando [`dotnet pack`](../../core/tools/dotnet-pack.md) genera un file `*.nupkg` invece di assembly.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

Il modo meno recente per creare un pacchetto NuGet consiste nell'usare un file `*.nuspec` e lo strumento da riga di comando `nuget.exe`. Un file nuspec offre uno straordinario controllo, ma è necessario specificare attentamente quali assembly e destinazioni includere nel pacchetto NuGet finale. È facile commette un errore o dimenticarsi di aggiornare il file nuspec quando si apportano modifiche. Il vantaggio di un file nuspec è la possibilità di usarlo per creare pacchetti NuGet per framework che ancora non supportano un file di progetto in stile SDK.

**✔️ VALUTARE** l'uso di un file di progetto in stile SDK per creare il pacchetto NuGet.

**✔️ VALUTARE** la configurazione di SourceLink per aggiungere metadati di controllo del codice sorgente agli assembly e al pacchetto NuGet.

## <a name="package-dependencies"></a>Dipendenze dei pacchetti

Le dipendenze dei pacchetti NuGet sono illustrate in dettaglio nell'articolo [Dipendenze](./dependencies.md).

## <a name="important-nuget-package-metadata"></a>Metadati importanti dei pacchetti NuGet

Un pacchetto NuGet supporta numerose [proprietà dei metadati](/nuget/reference/nuspec). La tabella seguente contiene i principali metadati che ogni progetto open source deve fornire:

| Nome proprietà MSBuild              | Nome nuspec              | Descrizione  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identificatore del pacchetto. Un prefisso dell'identificatore può essere riservato se soddisfa i [criteri](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versione del pacchetto NuGet. Per altre informazioni, vedere [Versione dei pacchetti NuGet](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Titolo descrittivo del pacchetto. Il valore predefinito è `PackageId`.             |
| `Description`                      | `description`              | Descrizione lunga del pacchetto visualizzata nell'interfaccia utente.             |
| `Authors`                          | `authors`                  | Elenco di autori del pacchetto delimitati da virgole, corrispondenti ai nomi dei profili in nuget.org.             |
| `PackageTags`                      | `tags`                     | Elenco di tag e parole chiave delimitati da spazi che descrivono il pacchetto. I tag vengono usati per la ricerca di pacchetti.             |
| `PackageIconUrl`                   | `iconUrl`                  | URL di un'immagine da usare come icona per il pacchetto. L'URL deve essere di tipo HTTPS e l'immagine deve avere dimensioni di 64x64 e uno sfondo trasparente.             |
| `PackageProjectUrl`                | `projectUrl`               | URL della home page del progetto o del repository di origine.             |
| `PackageLicenseUrl`                | `licenseUrl`               | URL della licenza del progetto. Può essere l'URL del file `LICENSE` nel controllo del codice sorgente.             |

**✔️ VALUTARE** la scelta di un nome di pacchetto NuGet con un prefisso che soddisfi i [criteri](/nuget/reference/id-prefix-reservation) per riservare il prefisso NuGet.

**✔️ VALUTARE** l'uso del file `LICENSE` nel controllo del codice sorgente come oggetto `LicenseUrl`. Ad esempio, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Per un progetto senza una licenza viene applicato per impostazione predefinita il [copyright esclusivo](https://choosealicense.com/no-permission/), che ne impedisce l'uso da parte di altre persone.

**✔️ USARE** un attributo href HTTPS per l'icona del pacchetto.

> I siti come NuGet.org vengono eseguiti con il protocollo HTTPS abilitato e la visualizzazione di un'immagine non HTTPS comporta la generazione di un avviso di contenuto misto.

**✔️ USARE** un'immagine di icona del pacchetto con dimensioni di 64x64 e con uno sfondo trasparente per ottenere una migliore visualizzazione.

## <a name="pre-release-packages"></a>Pacchetti in versione non definitiva

I pacchetti NuGet con un suffisso di versione sono considerati [versioni non definitive](/nuget/create-packages/prerelease-packages). Per impostazione predefinita, l'interfaccia utente di Gestione pacchetti NuGet mostra le versioni stabili, a meno che un utente non scelga esplicitamente pacchetti in versione non definitiva, ideali per test utente limitati.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Una pacchetto stabile non può dipendere da un pacchetto in versione non definitiva. È necessario impostare un pacchetto come versione non definitiva oppure fare in modo che dipenda da una versione stabile precedente.

![Dipendenza dei pacchetti NuGet in versione non definitiva](./media/nuget/nuget-prerelease-package.png "Dipendenza dei pacchetti NuGet in versione non definitiva")

**✔️ PUBBLICARE** un pacchetto in versione non definitiva a scopi di test, anteprima o sperimentazione.

**✔️ PUBBLICARE** un pacchetto stabile quando è pronto, in modo che altri pacchetti stabili possano farvi riferimento.

## <a name="symbol-packages"></a>Pacchetti di simboli

I file di simboli (`*.pdb`) vengono prodotti dal compilatore .NET insieme agli assembly. I file di simboli mappano le posizioni di esecuzione al codice sorgente originale, in modo che sia possibile esaminare il codice sorgente mentre è in esecuzione usando un debugger. NuGet supporta la [generazione di un pacchetto di simboli separato](/nuget/create-packages/symbol-packages) contenente i file di simboli insieme al pacchetto principale che contiene gli assembly .NET. L'idea dei pacchetti di simboli è che siano ospitati in un server di simboli e scaricati solo da uno strumento come Visual Studio su richiesta.

Attualmente l'host pubblico principale per i simboli, [SymbolSource](http://www.symbolsource.org/), non supporta i nuovi [file di simboli portabili](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) creati dai progetti in stile SDK e i pacchetti di simboli non sono utili. Fino a quando non sarà disponibile un host consigliato per i pacchetti di simboli, i file di simboli possono essere incorporati nel pacchetto NuGet principale. Se si sta creando un pacchetto NuGet usando un progetto in stile SDK, è possibile incorporare i file di simboli impostando la proprietà `AllowedOutputExtensionsInPackageBuildOutputFolder`: 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

**✔️ VALUTARE** l'incorporamento dei file di simboli nel pacchetto NuGet principale.

**❌ EVITARE** di creare un pacchetto di simboli contenente file di simboli.

>[!div class="step-by-step"]
[Precedente](./strong-naming.md)
[Successivo](./dependencies.md)
