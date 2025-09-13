# Viikko 1

## Tietoa minusta:

Minä olen **Riku**, ikää *24v* ja asun **Limingassa**.

>Harrastuksena DX-kuuntelu, radiotekniikka ja valokuvaaminen.

### Mielenkiinnon kohteita:
1. Radiot
2. DX-kuuntelu
3. Lähetysverkkojen toiminta
4. Autot


## Viimeaikana on tullut syvennettyä myös kaapeliverkkojen toimintaan. Alla esimerkkinä oman testiverkon taajuudet, ja modulaattorin malli:

| Modulaattori       | Taajuus MHz |
|------------|-----|
| BladeRF       | 102.4  |
| BladeRF       | 102.9  |
| BladeRF       | 103.3  |
| BladeRF       | 103.7  |
| Si4713            | 103.9  |
| Profline SFY      | 104.2  |
| BH1415F       | 104.6  |
| BH1415F       | 105.0  |
| BH1415F       | 105.2  |
| BH1415F       | 105.7  |
| Si4713        | 106.4  |
| BH1417F       | 106.7  |
| BH1417F       | 107.1  |
| BH1417F       | 107.9  |

Valmistajat:

* Nuand
* Silicon Labs
* ROHM



## Alla kuva Kokkolan Patamäeltä.
![Patamäki](https://rmartinmaki.com/kuvat/mastot/Kokkola,%20Patam%C3%A4ki/2019/IMG_2590.jpg)


# Linkki tähän repoon
[Linkki](https://github.com/rikum11/repo2)

---

## Koodiesimerkki Si4713 modulaattorin Python scriptistä joka ajaa dynaamista RDS dataa.

```def serialReader():
    while True:
        print(serialport.readline())
        time.sleep(0.1)

timeThread = threading.Thread(target=generateCT)
timeThread.start()
metadataThread = threading.Thread(target=getMetadataFromServer)
metadataThread.start()
serialReaderThread = threading.Thread(target=serialReader)
serialReaderThread.start()
serialport.write(("{PWR: 115}").encode('UTF-8'))

time.sleep(5)


