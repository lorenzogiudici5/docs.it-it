### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>Il testo selezionato nel controllo TextBox WPF viene visualizzato con un colore diverso quando la casella di testo è inattiva

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5, se una casella di testo WPF è inattiva (non ha lo stato attivo), il testo selezionato nella casella verrà visualizzato con un colore diverso rispetto a quando il controllo è attivo.|
|Suggerimento|È possibile ripristinare il comportamento precedente di .NET Framework 4.0 impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> su <code>false</code>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

