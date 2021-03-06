---
title: Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET
description: Informazioni su come usare i normalizzatori per pre-elaborare i dati di training da usare per la creazione del modello di Machine Learning, il training e l'assegnazione dei punteggi con ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c8b959904705e996c97bdcd8b3444e754d14d046
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148834"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dei dati - ML.NET

ML.NET espone alcuni [algoritmi parametrici e non parametrici](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

La scelta del normalizzatore **non** è importante quanto l'**uso** di un normalizzatore per il training di modelli parametrici lineari o di altro tipo.

Includere sempre il normalizzatore direttamente nella pipeline di apprendimento di ML.NET in modo che:

- il training venga eseguito solo sui dati di training e non sui dati di test,
- venga correttamente applicato a tutti i nuovi dati in ingresso, senza che siano necessarie altre operazioni di pre-elaborazione in fase di stima.

Di seguito è riportato un frammento di codice che illustra la normalizzazione nelle pipeline di apprendimento. Presuppone che venga usato il set di dati Iris:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features", DataKind.R4, 0, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
