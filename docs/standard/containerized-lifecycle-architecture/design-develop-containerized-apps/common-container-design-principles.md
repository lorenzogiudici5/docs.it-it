---
title: Principi di progettazione comuni di contenitore
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 8aa388c7c19f532829d64208a48b6e556e43d802
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152877"
---
# <a name="common-container-design-principles"></a>Principi di progettazione comuni di contenitore

-Ahead di introduzione nel processo di sviluppo sono disponibili alcuni concetti di base che è opportuno menzionare per quanto riguarda l'utilizzo di contenitori.

## <a name="container-equals-a-process"></a>Contenitore è uguale a un processo

Nel modello di contenitore, un contenitore rappresenta un singolo processo. Con la definizione di un contenitore come limite di processo, si inizia a creare le primitive utilizzate per scalabilità, o batch-off, i processi. Quando si esegue un contenitore Docker, si noterà un' [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definizione. Questa impostazione definisce il processo e la durata del contenitore. Al termine del processo, termina il ciclo di vita del contenitore. Esistono processi a esecuzione prolungata, ad esempio server web e processi di breve durati, ad esempio i processi di batch, che potrebbero essere stati implementati come Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se è stato richiesto l'agente di orchestrazione per mantenere cinque istanze in esecuzione e uno ha esito negativo, l'agente di orchestrazione verrà creato un altro contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato.

È possibile trovare uno scenario in cui si desidera più processi in esecuzione in un singolo contenitore. In qualsiasi documento di architettura, non riguarda mai un "," né è sempre disponibile un' "sempre". Per gli scenari che richiedono più processi, un modello comune consiste nell'usare [Supervisore](http://supervisord.org/).

>[!div class="step-by-step"]
>[Precedente](design-docker-applications.md)
>[Successivo](monolithic-applications.md)