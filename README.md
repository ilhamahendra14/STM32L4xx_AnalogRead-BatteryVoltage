# STM32L4xx_AnalogRead-BatteryVoltage

When I build embedded system device, I need monitor battery voltage.
I'm using simple [voltage divider](https://ohmslawcalculator.com/voltage-divider-calculator) to read the battery voltage.

Important:
+ Please check max 'external impedance input'. (ex : [STM32L432KC Datasheet](https://www.st.com/resource/en/datasheet/stm32l432kc.pdf) page 114)
+ Don't use more than 50kΩ resistor, but don't use small resistance because it makes high current consumption.
+ Add a capacitor across R2 to make the battery voltage reading stable.

  ![alt text](https://github.com/ilhamahendra14/STM32L4xx_AnalogRead-BatteryVoltage/blob/74d9e68ecae292dc1f61baf024ec4f6fd9469b3b/Images/voltage_divider_schematic.png?raw=true)
+ I'm build a low power consumption device, so I must disable/enable voltage divider with load switch.
  ![alt text](https://github.com/ilhamahendra14/STM32L4xx_AnalogRead-BatteryVoltage/blob/74d9e68ecae292dc1f61baf024ec4f6fd9469b3b/Images/load_switch.png?raw=true)

Details of the battery and resistor used:
+ Vbat  = 4v1
+ R1    = 5k23
+ R2    = 10k
+ C1    = 1uF

Formula:
Vbat = Vadc * (R1 + R2) / R2
