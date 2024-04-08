# Baimenak

- [Baimenak](#baimenak)
  - [Fitxategi eta direktorioaren baimenak](#fitxategi-eta-direktorioaren-baimenak)
    - [Baimenen taldeak](#baimenen-taldeak)
    - [Baimenak esleitzen modu simbolikoan](#baimenak-esleitzen-modu-simbolikoan)
    - [Baimenak modu oktalea](#baimenak-modu-oktalea)
  - [Sticky bit baimena](#sticky-bit-baimena)

## Fitxategi eta direktorioaren baimenak

Fitxategi eta direktoriaoaren baikenak urengo aginduarekin ikusi ditzakegu.

```Bash
ls -a
```
![eman ikusi dezakegu komandoa](dfas.PNG)

### Baimenen taldeak

**- Jabea (user)**: Fitxategi bat sortzen dugunean, sortzailea jabea izango da defektuz.
- **Talde (group)**: Fitxategi baten jabetza talde bati ere bai dagokio.
- **Besteak (other)**: Jabeak edo taldeak ez direnak.

![alt text](image-1.png)

### Baimenak esleitzen modu simbolikoan
Linuxen baimenak izendatzen ahal izateko, `chmod` komandoa erabil daiteke. Hemen daude baimen gehien erabiltzen direnak eta nola erabili aurrerantzean:

1. **Baimenak Entzuten (Read)**: Fitxategi edo direktorioa irakurtzeko baimena ematen du.
   ```bash
   chmod +r fitxategia_edo_direktorioa
   ```

2. **Baimenak Idazten (Write)**: Fitxategi edo direktorioan idazteko baimena ematen du.
   ```bash
   chmod +w fitxategia_edo_direktorioa
   ```

3. **Baimenak Exekutatzen (Execute)**: Script-a exekutatu edo direktorioan sartu ahal izateko baimena ematen du.
   ```bash
   chmod +x fitxategia_edo_direktorioa
   ```

4. **Baimenak Kenduz (Remove)**: Baimenak kendu nahi izanez gero, `-` erabil daiteke.
   ```bash
   chmod -r fitxategia_edo_direktorioa
   chmod -w fitxategia_edo_direktorioa
   chmod -x fitxategia_edo_direktorioa
   ```

Baimenak hainbat erabilera egokiagoak dituzten moduan ere konbinatu daitezke. Adibidez, fitxategi batek irakur, idaz eta exekutatzeko baimena emateko:
```bash
chmod +rwx fitxategia_edo_direktorioa
```

Baimenak zehazten dituzten 3 digituko kodigoa ere erabil daiteke. Hau da,:
- **4**: Irakurketa (Read)
- **2**: Idazketa (Write)
- **1**: Exekuzioa (Execute)

Adibidez, fitxategi bati irakur, idaz eta exekutatzeko baimena emateko:
```bash
chmod 777 fitxategia_edo_direktorioa
```

Kontuz! Baimenak berriz aldatzea eta egoera sisteman datuak aldatzea arriskutsua da. Baimenak egoki eta behar bezala esleitzea gomendatzen da.

Adibidez, Jabeari (user) exekutatzeko baimena horela eman ahal ditugu.

```Bash
chmod u+x froga.txt
```
Horela taldeari eta besteei exekuzio eta idazteko baimenak emango dizkiogu.
```Bash
chmod go+wx froga.txt
```

Besteei, irakurtzeko baimenak diezaiegu.
```Bash
chmod o-r froga.txt
```

### Baimenak modu oktalea

- 0 = 000 = --- = Baimerik gabe
- 1 = 001 = --x = Exekutazio baimena
- 2 = 010 = -W- = Idazteko baimena
- 3 = 011 = -wx = Idazteko eta exekutatzeko
- 4 = 100 = r-- = Irakurtzeko baimena
- 5 = 101 = r-x = Irakurtzeko eta exekutatzeko baimena
- 6 = 110 = rw- = Irakurtzeko eta idazteko baimena
- 7 = 111 = rwx = Baimena guztiak

Baimen guztiak kentzeko
```Bash
chmod 000 froga.txt
```
Baimen guztiak gehitzeko
```Bash
chmod 777 froga.txt
```
Exekutatzeko eta irakurtzeko baimena
```Bash
chmod 755 froga .txt
```

## Sticky bit baimena

Sticky bita daukat fitxategi edo direktorio bat bakarrik jabea edo root-ak aldatu ditzake izena edo ezabatu

Sticky bit gehitzeko
```Bash
chmod +t froga.txt
```
![alt text](dgfsdgfs.PNG)
