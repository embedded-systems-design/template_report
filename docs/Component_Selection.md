---
title: Component Selection Example
---



**Voltage regulator**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> LM2575T-3.3G Voltage regulator<br>$2.99/each<br>[link to product](https://www.digikey.com/en/products/detail/onsemi/LM2575T-3-3G/1476700)                 | \* Its pretty Inexpensive<br>\* Compatible with ESP32<br>\*                                                                                           | \* This isnot surface mount. |
| ![](image3.png)<br>\* Option 2. <br>\* LM2575T-3.3G Voltage regulator Onsemi <br>\* $2.99/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/onsemi/LM2575T-3.3G?qs=2OtswVQKCOGI3KWqs9UK2g%3D%3D&srsltid=AfmBOortntqRKRikqDGAmiPXAOOyckybAR0vXEoz6tZxH8LwnRsjO0iy) | \* Stable Tempurature <br>\* Regulates at 3.3V <br>  | \* Less documentation <br>                                                       |
| ![](image3.png)<br>\* Option 2. <br>\*998-LM2575T-3.3G Voltage regulator Onsemi <br>\* $1.75/each <br>\* [Link to product](https://www.mouser.com/ProductDetail/Microchip-Technology/LM2575-33WU?qs=kh6iOki%2FeLFl2EB4QdXuKA%3D%3D&utm_id=8790913657&gad_source=1&gclid=CjwKCAiA74G9BhAEEiwA8kNfpSM8OPXtxbaCHgvZc1sHfrbZeLMksdtZdrtF3OnQCLQ7SpuZGOPnvhoC3ikQAvD_BwE) | \* Surface mount<br>\* Regulates at 3.3V <br>\* Very affordable <br> | \* more complicated to solder <br>                                                       |


**Choice:** Option 3: 998-M2575T-3.3G Voltage regulator Surface Mount Version

**Rationale:** This product is from Mouser, it also has great documentation as well as meeting the surface mount requirements.



**Voltage regulator**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> XC1259TR-ND surface mount crystal<br>$1/each<br>[link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)                 | \* Inexpensive[^1]<br>\* Compatible with PSoC<br>\* Meets surface mount constraint of project                                               | \* Requires external components and support circuitry for interface<br>\* Needs special PCB layout. |
| ![](image3.png)<br>\* Option 2. <br>\* CTX936TR-ND surface mount oscillator <br>\* $1/each <br>\* [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940) | \* Outputs a square wave <br>\* Stable over operating temperature <br> \* Direct interface with PSoC (no external circuitry required) range | * More expensive <br>\* Slow shipping speed                                                         |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.
