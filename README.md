**Exemple simple, documenté, et valide d’ePub 3.0**

Un exemple d’ePub version 3.0, simple sans être minimaliste, documenté. Avec des polices, images, audio, vidéo, scripts, formulaires, tables, etc.

# Utiliser l'exemple

L’IDPF propose [ePubCheck, un valideur d’ePub](https://github.com/IDPF/epubcheck/).



## Valider les sources

Attention, le valideur de l’IDPF renvoie des faux-positifs sur différents éléments, notamment liés au SVG. Consultez les [rapports de bug](https://github.com/IDPF/epubcheck/issues) pour savoir ce qu'il en est réellement.
```bash
java -jar epubcheck-*.jar -mode exp "Damien Clauzel - Exemple ePub3"
```

## Empaqueter les sources
Si les sources sont complètement valides, le valideur peut assembler l’ePub à la volée.
```bash
java -jar epubcheck-*.jar -mode exp -save "Damien Clauzel - Exemple ePub3"
```
Il est aussi possible d'assembler l’ePub à la main (eh, ce n'est qu'une archive ZIP). Cependant, il faut prendre soin de placer en premier dans l'archive le fichier `mimetype`, et de placer les contenus dans la racine.

```bash
cd "Damien Clauzel - Exemple ePub3"

zip -X "Damien Clauzel - Exemple ePub3.epub" mimetype
zip -rg "Damien Clauzel - Exemple ePub3.epub" META-INF/ EPUB/
```

## Dépaqueter l’ePub
```bash
unzip "Damien Clauzel - Exemple ePub3.epub"
```


# Licence

[CreativeCommons Attribution - Partage dans les Mêmes Conditions 3.0 France (CC BY-SA 3.0 FR)](http://creativecommons.org/licenses/by-sa/3.0/fr/)
