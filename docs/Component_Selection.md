---
title: Component Selection
---



**Voltage regulator**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> LM2575T-3.3G Voltage regulator<br>$2.99/each<br>[link to product](https://www.digikey.com/en/products/detail/onsemi/LM2575T-3-3G/1476700)                 | \* Its pretty Inexpensive<br>\* Compatible with ESP32<br>\*                                                                                           | \* This isnot surface mount. |
| ![](image3.png)<br>\* Option 2. <br>\* LM2575T-3.3G Voltage regulator Onsemi <br>\* $2.99/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/onsemi/LM2575T-3.3G?qs=2OtswVQKCOGI3KWqs9UK2g%3D%3D&srsltid=AfmBOortntqRKRikqDGAmiPXAOOyckybAR0vXEoz6tZxH8LwnRsjO0iy) | \* Stable Tempurature <br>\* Regulates at 3.3V <br>  | \* Less documentation <br>                                                       |
| ![](image3.png)<br>\* Option 3. <br>\*998-LM2575T-3.3G Voltage regulator Onsemi <br>\* $1.75/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/Microchip-Technology/LM2575-33WU?qs=kh6iOki%2FeLFl2EB4QdXuKA%3D%3D&utm_id=8790913657&gad_source=1&gclid=CjwKCAiA74G9BhAEEiwA8kNfpSM8OPXtxbaCHgvZc1sHfrbZeLMksdtZdrtF3OnQCLQ7SpuZGOPnvhoC3ikQAvD_BwE) | \* Surface mount<br>\* Regulates at 3.3V <br>\* Very affordable <br> | \* more complicated to solder <br>                                                       |


**Choice:** Option 3: 998-M2575T-3.3G Voltage regulator Surface Mount Version

**Rationale:** This product is from Mouser, it also has great documentation as well as meeting the surface mount requirements.



**Diodes**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> 1N5819HWQ-7-F<br>$0.30/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/1N5819HWQ-7-F/10294862)                 | \* Has many low voltage applications<br>\* Can handle strong current spikes<br>\* Meets surface mount constraint of project                                               | \* Requires external surface mount soldering<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*1N5819W Diode <br>\* $0.21/each <br>\* [Link to product](https://www.digikey.com.br/en/products/detail/smc-diode-solutions/1N5819W/15964237?gQT=2) | \* resists alot of back EMF <br>\* Stable over operating temperature <br>  | * More fragile diode than the other options <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*1N5817G<br>\* $0.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/onsemi/1N5817G/1474208?gQT=2) | \* Surface mount<br>\* Regulates at 3.3V <br>\* Very affordable <br> | \* more complicated to solder <br>                                                       ||

**Choice:** Option 1: 1N5819HWQ-7-F Diodes

**Rationale:** A reliable diode that can handle lots of current and voervoltage if neccesary. A solid option that also meets the surface mount requirement



**100 uF 50V Capacitor**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> EEEFP1H101AL<br>$1.08/each<br>[link to product]((https://www.newark.com/panasonic/eee-fp1h101al/cap-100uf-50v-alu-elec-smd/dp/77AH6958?gQT=1))                 | \* is made from aluminum<br>\* very high tempurature opperation<br>\* low capacitive resistance                                              | \* slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $0.75/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/nic-components-corp/NACZ101M50V8X10.5TR15F/22237846?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=Pmax_Shopping_DK%2B%20Supplier_GEM%20Suppliers&utm_term=&utm_content=&utm_id=go_cmp-20940607809_adg-_ad-__dev-c_ext-_prd-22237846_sig-Cj0KCQiA-5a9BhCBARIsACwMkJ6SoxjzmShiHYpyNLZBKTV90kZgzpwd-frZ5nXwgLEiKssFXpOCy5caApXMEALw_wcB&gad_source=4&gclid=Cj0KCQiA-5a9BhCBARIsACwMkJ6SoxjzmShiHYpyNLZBKTV90kZgzpwd-frZ5nXwgLEiKssFXpOCy5caApXMEALw_wcB&gclsrc=aw.ds) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*1N5817G<br>\* $1.41/each <br>\* [Link to product(]https://www.digikey.com/en/products/detail/surge/VUJ101M1HTR-1313S/12451683?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive option <br>                                                       ||

**Choice:** Option 2:NACZ101M50V8X10.5TR15F

**Rationale:** This is the most affordable optionb alongside meeting all the requirements needed in a capacitor.




**300 uF 10V Capacitor**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> 593D337X9010E2TE3<br>$1.08/each<br>[link to product](https://www.mouser.com/ProductDetail/Vishay-Sprague/593D337X9010E2TE3?qs=sGAEpiMZZMsh%252B1woXyUXjwCXIFHUiAeHSeSfpcvZBjg%3D)                 | \* is made from aluminum<br>\* very high tempurature opperation<br>\* low capacitive resistance                                              | \* Rslightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $1.49/each <br>\* [Link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*EEE-FP1A331AP<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEE-FP1A331AP/1701024?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive otion <br>                                                       ||

**Choice:** Option 2:NACZ101M50V8X10.5TR15F





**220 uH Inductorr**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> Wurth Elektronik 744777222 Power inductor<br>$0.86/each<br>[link to product](https://us.rs-online.com/product/wurth-elektronik/744777222/70996735/?srsltid=AfmBOoplbC9HlsIm1DVj5emG3Z0cCukz7l6xsVKoGYbzKiF8KqjWqO827kQ&gQT=1)                 | \* small size <br>\* very high tempurature opperation<br>\*                                              | \* slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $1.49/each <br>\* [Link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*EEE-FP1A331AP<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEE-FP1A331AP/1701024?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive otion <br>                                                       ||

**Choice:** Option 2:NACZ101M50V8X10.5TR15F




**Barrel Jacks**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> Wurth Elektronik 744777222 Power inductor<br>$0.86/each<br>[link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1)                 | \* small size <br>\* very high tempurature opperation<br>\*                                              | \* slightly more expensive<br>\* |
| ![](image3.png)<br>\* Option 2. <br>\*NACZ101M50V8X10.5TR15F <br>\* $1.49/each <br>\* [Link to product](https://www.elliottelectronicsupply.com/surface-mount-smt-electrolytic-capacitors.html?gQT=1) | \* resists alot of back EMF <br>\* Is rated for 200V <br> \* can be bought in bulk for a discount| * Its a larger capacitor <br>\* 
| ![](image3.png)<br>\* Option 3. <br>\*EEE-FP1A331AP<br>\* $1.41/each <br>\* [Link to product](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEE-FP1A331AP/1701024?gQT=1) | \* Surface mount<br>\* smallest size <br>\* good voltage rating <br> | \* most expensive otion <br>                                                       ||

**Choice:** Option 2:NACZ101M50V8X10.5TR15F







**Rationale:** .

