### Пример прошивки ESPHome для Zigbee-устройств на базе ESP32-C6 ###
Пример предназначен для демонстрации  принципиальной возможности сборки в ESPHome прошивки для Zigbee-устройств на базе ESP32-C6 или ESP32-H2.
Прошивка содержит минимальные функции Zigbee End Device для лампочки.

Пример использует кастомные компоненты, являющиеся обертками над [Zigbee-классами для ESP32-C6/H2](https://github.com/Muk911/zigbee/tree/main/esp32c6/zblc).
В дальнейшем планируется преобразовать кастомные компоненты ESPHome во внешние компоненты ESPHome и избавиться от костылей в виде шаблонных сенсоров, использованных для передачи значений между компонентами и сущностями ESPHome.

#### Сборка прошивки ####
Взято из [примера от luar123](https://github.com/luar123/esphome_zb_sensor?tab=readme-ov-file#build-esphome-zigbee-sensor).
После первой сборки, заканчивающейся ошибкой, необходимо:
- скопировать файл idf_component.yml в папку .esphome/build/hello-zigbee/src/
- добавить следующие строки в файл .esphome/build/zb-sensor/sdkconfig.hello-zigbee

### translation ###
### ESPHome firmware example for ESP32-C6-based Zigbee devices ###
The example is intended to demonstrate the fundamental possibility of assembling firmware in ESPHome for ESP32-C6 or ESP32-H2-based Zigbee devices.
The firmware contains minimal Zigbee End Device functions for a light bulb.

The example uses custom components that are wrappers over [ESP32-C6/H2 Zigbee classes](https://github.com/Muk911/zigbee/tree/main/esp32c6/zblc).
In the future, we plan to convert ESPHome custom components into external ESPHome components and get rid of the crutches in the form of template sensors used to transfer values ​​between ESPHome components and entities.

#### Firmware build ####
Taken from [luar123's example](https://github.com/luar123/esphome_zb_sensor?tab=readme-ov-file#build-esphome-zigbee-sensor).
After the first build, which ends with an error, you need to:
- copy the idf_component.yml file to the .esphome/build/hello-zigbee/src/ folder
- add the following lines to the .esphome/build/zb-sensor/sdkconfig.hello-zigbee file

```
CONFIG_ZB_ENABLED=y
CONFIG_ZB_RADIO_NATIVE=y
CONFIG_ZB_ZED=y
ZB_ED_ROLE=y
```
