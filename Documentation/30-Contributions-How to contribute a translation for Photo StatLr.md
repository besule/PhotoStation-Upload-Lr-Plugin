## How is localization done in Lightroom?
Lightroom supports localization through a "LOC" function. So, if the plugin developer strictly uses this function for UI elements, localization is easily done via accompanying translation files named __'TranslatedString_\<lang\>.txt'__ in the plugin directory, where \<lang\> stands for a language code like en, de, fr, ...<br>
Important note: translation files must be __UTF8__-encoded!

## How far does localization go in Photo StatLr?
Almost all visible text elements of Photo StatLr in the Lr UI are localized, some items in drop-down menues are stilling missing. The output to the logfile on the other is not localized.

## What is the native plugin language?
English is the native plugin language. So, if you would remove all translation files, you still get the English version. The English translation file is extracted from the code, so it makes no sense to edit the English translation file, since it will be overwritten with the next release. If you find flaws in the English text, please let me know, I will incorporate you suggestions into the code.

## What has to be done to add a translation
The plugin comes with translation files for (hopefully) all Lr-supported languages. All not yet translated language files will yield the native English version. As soon as you start translating text string within the file, the UI of Photo StatLr version will get (after restarting Lr) localized more and more. Translating is done as follows:
- each line in a translation file looks like "$$$\<string_path\>=\<translated string\>", where string_path is the unique identifier of the string. The string path should give a rough idea, where you will find the string in the UI
- open the file in an UTF8 capable editor and search for lines that include the string "__/PleaseTranslate__" as a suffix in the string_path, e.g.:<br>
	"$$$/PSUpload/ExportDialog/FlatCopyTT/PleaseTranslate=All photos/videos will be copied to the Target Album"
- translate the string right to the equal sign:
   - please make sure your text is not significantly longer than the English version, because otherwise Lr dialogs may be disrupted at the right side!
   - please leave in all placeholders like '^1', '^2' at the right position in your translation, they will be substituted by an actual value during runtime
   - '^n' stands for line break. Use it to format your text. Do not use more line breaks as the original, otherwise the text may be misaligned in you language.
- remove the suffix "/PleaseTranslate" from the string_path. Now in the German translation the line would look like:
	"$$$/PSUpload/ExportDialog/FlatCopyTT=Alle Fotos/Videos werden direkt in das Ziel-Album kopiert"
- save the file (and restart Lr to see the result). In our example, you just translated the tooltip text (suffix 'TT') in the Export and Publish Service dialog explaining the 'Flat Copy' setting.
- that's it!

## Do I need to translate all lines in the translation file?
You can translate as much as you like and you are able to. Any text that is not translated will be shown in English, that simple!

## How may I contribute my translation file?
You may incorporated your translation via GitHub mechanisms (pull, commit, push) and I will merge it.<br>
Or simply send it to photostatlr@messmer-online.de and I will incorporate into the next release.

## What happens if a new version of Photo StatLr adds or removes some strings?
Don't worry: all your translations will be preserved! Any new string will be marked with the suffix "/PleaseTranslate", any removed string will be marked with the suffix "/PleaseRemove". This helps you identifying changes and re-use old translations in case a new string is just a little bit different from an old, removed string.

## Will the plugin show my name/pseudonym as translation author?
Of course, it will do: __Honour to whom honour is due!__ If you adapt the line:
* "$$$/PSUpload/TranslationBy/PleaseTranslate=translated by: get your name here"

in the same way as you did for the other lines, your name/pseudonym will be shown in all Photo StatLr dialogs just below the Photo StatLr logo. That's your reward! :-)




