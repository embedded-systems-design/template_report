---
title: Component Selection
---

## Roles and Responsibilities

My job is to develop the web server and transmit data over Wi-Fi. The listed components are used to regulate the incoming voltage to my ESP32 device, ensuring reliable message transmission.



**Voltage regulator**


![image](https://github.com/user-attachments/assets/009b5012-767f-49b3-a916-c51b441b53a7)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> LM2575T-3.3G Voltage regulator<br>$2.99/each<br>[link to product](https://www.digikey.com/en/products/detail/onsemi/LM2575T-3-3G/1476700)                 | \* Its pretty inexpensive<br>\* Compatable with ESP32<br>\*                                                                                           | \* This is not surface mount. |
| ![](image3.png)<br>\* Option 2. <br>\* LM2575T-3.3G Voltage regulator Onsemi <br>\* $2.99/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/onsemi/LM2575T-3.3G?qs=2OtswVQKCOGI3KWqs9UK2g%3D%3D&srsltid=AfmBOortntqRKRikqDGAmiPXAOOyckybAR0vXEoz6tZxH8LwnRsjO0iy) | \* Stable Tempurature <br>\* Regulates at 3.3V <br>  | \* Less documentation <br>                                                       |
| ![](image3.png)<br>\* Option 3. <br>\*998-LM2575T-3.3G Voltage regulator Onsemi <br>\* $1.75/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/Microchip-Technology/LM2575-33WU?qs=kh6iOki%2FeLFl2EB4QdXuKA%3D%3D&utm_id=8790913657&gad_source=1&gclid=CjwKCAiA74G9BhAEEiwA8kNfpSM8OPXtxbaCHgvZc1sHfrbZeLMksdtZdrtF3OnQCLQ7SpuZGOPnvhoC3ikQAvD_BwE) | \* Surface mount<br>\* Regulates at 3.3V <br>\* Very affordable <br> | \* more complicated to solder <br>                                                       |


**Choice:** Option 3: 998-M2575T-3.3G Voltage regulator Surface Mount Version

**Rationale:** This product is from Mouser, it also has great documentation as well as meeting the surface mount requirements.



**Diodes**

![image](https://github.com/user-attachments/assets/f4fa20fe-170e-4cdf-a20c-d72a22ec1989)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> 1N5819HWQ-7-F<br>$0.30/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/1N5819HWQ-7-F/10294862)                 | \* Has many low voltage applications<br>\* Can handle strong current spikes<br>\* Meets surface mount constraint of project                                               | \* Requires external surface mount soldering<br>\*Cant handle alot of current|
| ![](image3.png)<br>\* Option 2. <br>\*1N5819W Diode <br>\* $0.21/each <br>\* [Link to product](https://www.digikey.com.br/en/products/detail/smc-diode-solutions/1N5819W/15964237?gQT=2) | \* resists alot of back EMF <br>\* Stable over operating temperature <br>  | * More fragile diode than the other options <br>\*Has a bit more reverse leakage 
| ![](image3.png)<br>\* Option 3. <br>\*1N5817G<br>\* $0.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/onsemi/1N5817G/1474208?gQT=2) | \* Surface mount<br>\* Regulates at 3.3V <br>\* Very affordable <br> | \*This is not a surface mount component<br>                                                       ||

**Choice:** Option 1: 1N5819HWQ-7-F Diodes

**Rationale:** A reliable diode that can handle lots of current and voervoltage if neccesary. A solid option that also meets the surface mount requirement



**100 uF 50V Capacitor**


![image](https://github.com/user-attachments/assets/b2729910-1512-41d4-968a-5cf35018781b)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> EEEFP1H101AL<br>$1.08/each<br>[link to product](https://www.newark.com/panasonic/eee-fp1h101al/cap-100uf-50v-alu-elec-smd/dp/77AH6958?gQT=1)                 | \* is made from aluminum<br>\* very high tempurature opperation<br>\* low capacitive resistance                                              | \* slightly more expensive<br>\*Data sheet is not very good |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $0.75/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/nic-components-corp/NACZ101M50V8X10.5TR15F/22237846?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=Pmax_Shopping_DK%2B%20Supplier_GEM%20Suppliers&utm_term=&utm_content=&utm_id=go_cmp-20940607809_adg-_ad-__dev-c_ext-_prd-22237846_sig-Cj0KCQiA-5a9BhCBARIsACwMkJ6SoxjzmShiHYpyNLZBKTV90kZgzpwd-frZ5nXwgLEiKssFXpOCy5caApXMEALw_wcB&gad_source=4&gclid=Cj0KCQiA-5a9BhCBARIsACwMkJ6SoxjzmShiHYpyNLZBKTV90kZgzpwd-frZ5nXwgLEiKssFXpOCy5caApXMEALw_wcB&gclsrc=aw.ds) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* does not have a good bulk idscount
| ![](image3.png)<br>\* Option 3. <br>\*1N5817G<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/surge/VUJ101M1HTR-1313S/12451683?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive option <br>                                                       ||

**Choice:** Option 3: 1N5817G

**Rationale:** Although this is the most expensive, it meets all requirements with its size and polarization.




**330 uF 10V Capacitor**

![image](https://github.com/user-attachments/assets/8fb857aa-bbd6-4fc9-adc2-7ea65d496305)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> 593D337X9010E2TE3<br>$1.08/each<br>[link to product](https://www.mouser.com/ProductDetail/Vishay-Sprague/593D337X9010E2TE3?qs=sGAEpiMZZMsh%252B1woXyUXjwCXIFHUiAeHSeSfpcvZBjg%3D)                 | \* is made from aluminum<br>\* very high tempurature opperation<br>\* low capacitive resistance                                              | \* Slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $1.49/each <br>\* [Link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*EEE-FP1A331AP<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEE-FP1A331AP/1701024?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive otion <br>                                                       ||

**Choice:** Option 3 :NACZ101M50V8X10.5TR15F

**Rationale:** Its the smallest size and has unbeatable price.



**220 uH Inductorr**

![image](https://github.com/user-attachments/assets/3c6bf2ab-0947-4106-968e-380dce028a48)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> Wurth Elektronik 744777222 Power inductor<br>$0.86/each<br>[link to product](https://us.rs-online.com/product/wurth-elektronik/744777222/70996735/?srsltid=AfmBOoplbC9HlsIm1DVj5emG3Z0cCukz7l6xsVKoGYbzKiF8KqjWqO827kQ&gQT=1)                 | \* small size <br>\* very high tempurature opperation<br>\*                                              | \* slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $1.49/each <br>\* [Link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*EEE-FP1A331AP<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEE-FP1A331AP/1701024?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive otion <br>                                                       ||

**Choice:** Option 1: Wurth Elektronik 744777222 Power inductor

**Rationale:** This component has the best data sheet out of the bunch and seems to be the easiest to work with




**Barrel Jacks**

![image](https://github.com/user-attachments/assets/b253155e-0ba7-4ef5-ba25-19de1b7001a8)


| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> PJ-018H<br>[link to product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices-/PJ-018H/1644506?gQT=1)                 | \* only has two prongs<br>\* has a very flexable votlage range input<br> \*Handles high amperage                                           | \* slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*PJ-006B <br>\* $1.49/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices-/PJ-006B/408455?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*DCJ250-05-A-K1-A<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/gct/DCJ250-05-A-K1-A/9859679?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive option <br>                                                       ||

**Choice:** Option 3: DCJ250-05-A-K1-A

**Rationale:** Its the only one that incorporates surface mounting.







**wall mounted power supply**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br>L6R06H-120<br>\* $6.75/each <br>\*[link to product](http://digikey.com/en/products/detail/tri-mag-llc/L6R06H-120/7682617?gQT=1)                 | \* Short wire reach <br>\*Has very low current output which reduces the chances of EMF<br> \*The cheapest option                                           | \*worst quality plug<br>\* |
| ![](image3.png)<br>\* Option 2. <br>WDU12-100<br>\* $10.73/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/triad-magnetics/WDU12-100/6819553?gQT=1) | \*Low power surges <br>\* fits the selected barrel jack port <br> | * Its a larger plug <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*L6R12-120<br>\* $8.52/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/tri-mag-llc/L6R12-120/7682631?gQT=1) | \* can supply more current if needed<br>\* can operate in high tempuratures <br> | \*needs to be regulated because of high current capability <br>                                                       ||

**Choice:** Option 3: L6R12-120

**Rationale:** This product fits the systems needs with its voltage, land reliable documentation.


