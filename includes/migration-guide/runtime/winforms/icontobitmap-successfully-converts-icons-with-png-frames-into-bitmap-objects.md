### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap converte correttamente le icone con frame PNG in oggetti Bitmap

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.6, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> converte correttamente le icone con frame PNG in oggetti Bitmap. Nelle app destinate a .NET Framework 4.5.2 e versioni precedenti, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.ArgumentOutOfRangeException> se l'oggetto Icon include frame PNG. Questa modifica influisce sulle app che vengono ricompilate per essere destinate a .NET Framework 4.6 e che implementano una gestione speciale per l'eccezione <xref:System.ArgumentOutOfRangeException> generata quando un oggetto Icon include frame PNG. Quando è in esecuzione su .NET Framework 4.6, la conversione viene completata correttamente, non viene più generata un'eccezione <xref:System.ArgumentOutOfRangeException> e quindi non viene più richiamato il gestore di eccezioni.<ul><li>[X] Anomalo // Usa un meccanismo per attivare o disattivare la funzionalità, in genere usando una destinazione di runtime, AppContext o i file di configurazione. Deve essere attivato automaticamente per alcune situazioni.</li><li>[ ] Interruzione in fase di compilazione // Causa un'interruzione se si tenta di rieseguire la compilazione</li></ul>|
|Suggerimento|Se questo comportamento è indesiderato, è possibile conservare il comportamento precedente aggiungendo l'elemento seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>Se il file app.config contiene già l'elemento <code>AppContextSwitchOverrides</code>, il nuovo valore deve essere unito con l'attributo value come nell'esempio seguente:<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|
