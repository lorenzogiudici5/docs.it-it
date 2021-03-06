---
title: Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Informazioni sull'architettura esterna per la progettazione e lo sviluppo di applicazioni .NET basate su più contenitori e microservizi.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 3bbf746aa9c0b66a097b8c4df2964b5679342fd0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144143"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi

*Sviluppare applicazioni di microservizi incluse in contenitori significa compilare applicazioni a più contenitori. Tuttavia, un'applicazione a più contenitori potrebbe anche essere più semplice, ad esempio un'applicazione a tre livelli, e potrebbe non essere compilata usando un'architettura di microservizi.*

In precedenza ci si è interrogati sulla necessità di Docker per la compilazione di un'architettura di microservizio. In realtà, Docker non è affatto necessario. Docker può rappresentare una chiave di volta e offrire vantaggi significativi, ma i contenitori e Docker non sono un requisito fondamentale per i microservizi. Ad esempio, è possibile creare un'applicazione basata su microservizi con o senza Docker quando si usa Azure Service Fabric, che supporta i microservizi in esecuzione come processi semplici o come contenitori Docker.

Tuttavia, se si sa come progettare e sviluppare un'applicazione basata su microservizi che sia basata anche su contenitori Docker, sarà possibile progettare e sviluppare qualsiasi altro modello di applicazione più semplice. Ad esempio, si potrebbe progettare un'applicazione a tre livelli che richieda anche un approccio a più contenitori. Per questo motivo, e poiché le architetture di microservizi rappresentano una tendenza importante nel mondo dei contenitori, questa sezione è incentrata sull'implementazione di un'architettura di microservizi tramite i contenitori Docker.

>[!div class="step-by-step"]
>[Precedente](../docker-application-development-process/docker-app-development-workflow.md)
>[Successivo](microservice-application-design.md)