# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen Abständen ein `Tick`-Event aus. Der [`System.Windows.Forms`.`Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)



## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken).
- Die folgende Liste kann gerne ergänzt werden :)

### Bewegung animieren
Um Bewegungen animieren zu können, muss Zunächst ein Timer erstellt werden der die Ticks zählt.
Als nächstes müssen wir innerhalb des Timer-Events ein Codeabschnitt implementieren, welcher in jedem Tick ausgeführt werden soll. Anschließend müssen wir den Timer nur noch starten.

- Um das Timer Event anzulegen `private void tmrGameTick_Tick(object sender, EventArgs e)`
- Für die Animation implementieren wir Code, welcher ein Hindernis bewegt, `aktuellesHindernis.Move();`
- Zuletzt den Code für den start implementieren `tmrGameTick.Start();`

### Objekte mit Tasten steuern
Um die Steuerung mit Tasten zu ermöglichen, müssen wir Zunächst ein Steuerungs-Event anlegen.
In diesem Event können wir anschließend Befehle geben, auf welche Eingaben das Event achten muss.
Zum Schluss muss man nur noch den Code für die jeweilige Eingabe implementieren.

- Um das Steuerungs Event anzulegen  `private void FrmFrogger_KeyDown(object sender, KeyEventArgs e)`
- Um abzufragen ob die Pfeil Taste genutzt wurde, können wir den Code schreiben  `if (e.KeyCode == Keys.Up)`
- Code der bei Aktion ausgeführt werden soll `punktzahl++;`

### Verhindern, dass ein Spieler aus dem Bild läuft
Um dies zu verhindern können wir innerhalb des Steuerungs-Events eine Bewegungsgrenze für die betroffene Aktion einstellen.

```csharp
if (e.KeyCode == Keys.Up)
                {
                    if (currentline != 4)
    {

    spieler.Y = spieler.Y - hoeheJeBereich;
    currentline++;
    }
                }
```

### Spiel pausieren

### Ihr schönstes Ergebnis





