---
title: '&lt;endpointDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 0dde8150632c5d8a7bcea3dbeffe70b380d3a322
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183841"
---
# <a name="ltendpointdiscoverygt"></a>&lt;endpointDiscovery&gt;
Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.  
  
\<system.ServiceModel>  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<endpointDiscovery >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Valore booleano che specifica se l'individuazione è abilitata in questo endpoint. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<gli ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Raccolta di URI di ambito per l'endpoint. A un singolo endpoint è possibile associare più URI di ambito.|  
|[\<le estensioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [di \<endpointDiscovery >]|Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.|  
|\<tipi >|Raccolta di interfacce da cercare.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
|||  
  
## <a name="remarks"></a>Note  
 L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione. Inoltre, è possibile usare la [ \<ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)elemento figlio alla definizione degli ambiti personalizzata gli URI che possono essere usati per filtrare gli endpoint di servizio durante l'esecuzione di query, nonché il [ \<estensioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) elemento figlio per specificare metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, ambito e ListenURI).  
  
 Questo elemento di configurazione dipende il [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento che fornisce il controllo a livello di servizio dell'individuazione. Ciò significa che le impostazioni dell'elemento vengono ignorate se [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) non è presente nella configurazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
