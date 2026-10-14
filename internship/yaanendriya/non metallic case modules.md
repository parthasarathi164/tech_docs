## 1. Best leads for plastic or polymer enclosure designs

![Hardware Integration: EVB-1 - InertialSense](https://images.openai.com/static-rsc-4/sQx0ELJshO8OZXZhuY4jzcZuqdDBLMtZ6d9V6WaSDuoTAFf4Ntbwbpmr__b5KVhLoLZVGD41GL3DnS8_fUd-sYAcbrBFDZiY5SQWjkAh_JZmMcDmJQDRJmq4hGiGcR6SVCnrDT71ELcbGezGZBDFt0KeW_YydCnGfBFWNaZdev0?purpose=inline)

### 1. Inertial Sense

United States · GNSS-aided INS and embedded modules

Its product documentation identifies a plastic housing for the EVB1 development/evaluation hardware, while the separate rugged INS versions use aluminum. This is a useful lead for studying plastic enclosure implementation, although the plastic-housed evaluation unit is not confirmed as a rugged, sealed production module.

- [GNSS/INS product family and housing comparison](https://inertialsense.com/multi-band-ins-sensors/)
- [Technical datasheet and sensor-module information](https://content.inertialsense.com/imu-datasheet-download)

![MTI-680G /  / 디바이스마트](https://images.openai.com/static-rsc-4/n5u5Yv16lFgVfPeevgQgeC75byQMOSCPQSoZsFSEwEYntQii5BzGzz5wuZFUz12lRdLyRFMmSWlhJHaJjOQvpKJA4Z-uAJLuCIiS0aLEXfg_2UYPvIVCv_4grq6psEEjXAu4sr_R2xXThdNnNJDYmCIhUlR8xYW5MTu26JuCYps?purpose=inline)

### 2. Xsens — MTi-600 series

Netherlands · GNSS/INS and RTK-GNSS/INS

The OEM version is documented with a PC-ABS housing, a useful plastic-based enclosure reference. The series includes GNSS/INS models such as MTi-670 and RTK-GNSS/INS models such as MTi-680. The rugged variant uses aluminum, so the plastic OEM version should not automatically be considered ruggedized or IP-rated.

- [Official MTi-600 series page](https://www.xsens.com/products/sensor-modules/xsens-mti-600-series-flexible-reliable-imus-for-all-design-needs)
- [Housing material and interface specifications](https://freedspace.com.au/tracklab/products/brands/xsens/xsens-inertial-sensor-modules/xsens-mti-600-series/)

These two are the strongest starting points I found for documented plastic-based enclosure construction in an inertial-sensing product family. The critical distinction is that a plastic housing is not necessarily a rugged, sealed housing.

## 2. Other overseas manufacturers with useful enclosure documentation

These are worth examining if your priority is a complete ruggedized product, even if the housing material may not match your plastic requirement.

![Ship inertial navigation system - Certus Mini N - Advanced Navigation - GNSS / MEMS / ITAR Free](https://images.openai.com/static-rsc-4/hu78aI9MrH1ROqd9xTGZ2VzQNpa_tgkZDjbZ40Dja26c2jhsH-btpqu1gC8Lk4AxPaPfqZdpPribIakErtFLTtOGlmrUaH6rFn6MpRdOw11Hq7IlvP99une0u86NqEh3s5A_BvedgsJfM3i5-1DVlx9Q1atqYb5Fs6F_-OKnKsg?purpose=inline)

3. Advanced Navigation

Australia · MEMS GNSS/INS

Offers OEM modules and IP67-rated rugged housing versions. Good for comparing compact packaging, sealing requirements and environmental protection. The public overview does not establish that the rugged housing is plastic.

[Official product range](https://www.advancednavigation.com/inertial-navigation-systems/mems-gnss-ins/)

![GNSS Sensors & Modules | Tersus GNSS](https://images.openai.com/static-rsc-4/d2NeQYIjB0HvXzVOEoY2gHsowu74cP04I57iBF7_tFI_Q3759hM_MBEHB9HP0sNNOjrlfaTOTKTHA2UK_rEgLdyaQjAaPlhY7khA0HujmzKRtNXcPMcc6m5BMWxeoTVcpIEx3cjqo7orOYcalfBguzCX9-YssZ4wirf_257V1J4?purpose=inline)

4. Tersus GNSS

China · Integrated GNSS+INS

The INS200 has an all-in-one, IP67-rated enclosure, serial/CAN/Ethernet interfaces and an automotive-grade IMU. The official page provides a product image and downloadable datasheet, but does not specify the enclosure material in the product overview.

[INS200 product page and datasheet](https://www.tersus-gnss.com/product/INS200)

![Trimble BX940 | NAELCOM](https://images.openai.com/static-rsc-4/Oz7GmLLXbkOfUXc-Sgm4JuIaSEbu-SiE0mhh54o4SfMLyAfzqDGgFxRpC0_CtC1OchAJ_qmn3IPXwnbXSLGGNGebrWvnTfEJxngkkDDUqUZDHD5pB3IrM-JtXAkyjRJqlcRgoHC7pET95bl6m7uMX9n_nPSOB6qyd5xK9Xp9Y3w?purpose=inline)

5. Trimble

United States · GNSS/INS receiver enclosure

The BX940 combines GNSS and inertial navigation in a rugged, environmentally sealed receiver enclosure. Its product page links to datasheets and technical resources, making it useful for studying the overall enclosure and connector arrangement. Plastic construction is not confirmed.

[Official BX940 page and resources](https://oemgnss.trimble.com/en/products/receiver-enclosures/bx940)

![Septentrio AsteRx RBi3 Pro+ | Récepteur GNSS/INS ultra-robuste IP69K RTK centimétrique](https://images.openai.com/static-rsc-4/tNOGJpGkmxL92XfQLYHGxcN2sxxQyxP2ny-xbiOFzKpbgQHNt5foEi7NEYGYkdO1q6qTMl8iCQxe0vYlvCBHD1pvvosyQtDhspJJQ26vYDSiP-ZD6rKJD-Eiy4tCcu6PR34AFZG5wAnajL3XHZn8IkO7N79s0OEhAI4jdVsTqKo?purpose=inline)

6. Septentrio

Belgium · GNSS/INS receivers

Offers rugged GNSS/INS boxes and OEM boards, including the AsteRx RBi3 Pro family and AntaRx-Si3. Useful for studying sealed receiver designs and the distinction between a bare board and a complete rugged enclosure. Plastic material is not confirmed.

- [Rugged GNSS/INS receivers](https://www.septentrio.com/en/products/gnss-ins-receivers/ins-rugged-boxes)
- [GNSS receiver form factors](https://www.septentrio.com/en/company/about-us/which-form-factors-are-septentrio-gnss-receivers-available)