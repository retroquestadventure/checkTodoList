# checkTodoList
Eine ToDo Liste per Hotkey abhaken(oder anhacken) mittels Lokaler Textdatei, und Lokaler HTML Datei + der Verwendung von Streamer.bot

Erste Schritte:

1) ToDo Liste anlegen
 -> zb C:\checklist.txt
 -> Beispielinhalt:
   
 ☐ 1
 
 ☐ 2
 
 ☐ 3
 
 ☐ 4
 
 ☐ 5

 Das Zeichen ☐ am besten per copy+paste in die Datei kopieren.
 Der Text hinter dem Zeichen ( also zb 1 ) kann beliebig verändert werden.

 2) HTML Datei anlegen
    -> zb C:\checklist.html
    Die Liste muss im gleichen Ordner sein wie checklist.txt

    Inhalt der HTML Datei aus dem Git hier übernehmen.
    Datei speichern.

3) streamer.bot einstellen
  ->  Links im streamer.bot "Actions & Queues" -> dann "Actions" dann unter den "Actions" -> "Add" und eine Action erstellen
   zb mit den Namen "Hotkey für Liste (Strg+F1)"

  -> Dann rechts oben unter "Triggers" als Source "Coree > Inputs" den Typ "Krey Press" per "Add" hinzfügen 
  
   -> Nun eine Tastenkombination mittels "Capture Key" speichern -> zb  Strg+F1 ( bzw es steht dann da: Ctrl+F1 ) weil das die englische Bezeichnung von Strg ist.

   Jetzt kommen wir zur "Sub-Actions" unten rechts.
   
   -> Da im C# code die variable "path" genutzt wird, so wie auch die variable "line" müssen diese erst wie folgt getzt werden
   
    -> Also wieder "Add" -> "Core" -> "Arguments" -> "Set Argument"
    
     -> Bei Variable Name kommt dann "path" hin ( ohne "" )
     
     -> Bei Value muss der Pfad hin in dem die  checklist.txt liegt ( zb C:\\checklist.txt )
     Dann für die 2. Sub-Acttion:
     
        -> Also wieder "Add" -> "Core" -> "Arguments" -> "Set Argument"
        
        -> Bei Variable Name kommt dann "line" hin ( ohne "" )
        
        -> Bei Value muss nun 1 hin ( für den ersten Eintrag in der Liste )
        
    Als 3te Sub-Action folgt der C# code ( Inhalt siehe "toDolistCode.txt"
    
    -> Also "Add" -> "Core" -> "C#" -> "Execute C# Code"
    
    -> In das Fenster dann den Ihnhalt der Datei "toDoListCode.txt" kopieren und dann "Save and Compile" drücken.
    
    -----------------------
Der 3.te Schritt muss für jeden Hotkey wiederholt werden, aber natürlich mit anderer "line" und anderrem Hotkey
also für den 2ten Listeneintag den wert bei "line" auf 2 ändern und als Hotkey Strg+F2  wählen.
beim den 3ten Listeneintag den wert bei "line" auf 3 ändern und als Hotkey Strg+F3  wählen.
und so weiter.

-----------------------------------------------------------------------------------------------------------------------------------------------------

4) Streamlabs OBS oder OBS:
   -> Neue Browserquelle hinzufügen
     -> "Lokale Datei" aktivieren und die HTML datei als Datei auswählen ( Beispiel: C:\checklist.html  )

------------------------------------------------------------------------------------------------------------------------------------------------------

Hinweiß: Wenn der Code dann mittels Hotkey gestartet wird würd ein Debugfile in "C:\" erstellt. Hier "C:\debug.txt"
Der Name der Datei und der Pfad kann natürlich im C# Code geändert werden.

Ein Beisoielbild wie es aussehen kann im Streamerbot: Streamerbot.png
   
    
   
    
