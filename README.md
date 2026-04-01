# FirmwarePro (HIRI) - Placa Madre Mini (ESP32-S3)

Firmware para estación de monitoreo técnico-científico basada en el microcontrolador ESP32-S3-WROOM-1, con adquisición de sensores, GNSS, registro en SD, telemetría HTTP y gestor de archivos.

## Estado
- **Plataforma objetivo:** ESP32-S3 Dev Module (`esp32:esp32:esp32s3`)
- **Diseño de Hardware:** Placa Madre Mini Rev. ESP32-S3
- **Versión de referencia:** Pro V0.0.35+

## Funcionalidades principales
- Lectura de **PMS5003/Sensores Plantower** (PM1/PM2.5/PM10 + T/H)
- Lectura de PM100 mediante formato extendido SDS198.
- GNSS por módem SIM7600 (posición, altitud, velocidad, satélites, HDOP).
- Power Gating mediante control de rieles 5V y 3.3V (SD, Modems, Sensores).
- Medición de batería precisa con API de calibración `esp_adc_cal` nativa.
- Registro en **CSV diario** en tarjeta SD de alta eficiencia.
- Envío HTTP de mediciones a backend optimizado para bajo consumo energético.
- UI local con OLED y botones con debounce por software para extrema estabilidad.
- Neopixel RGB integrado para estado de operación sin pantalla.

## Entorno de hardware y configuración
- **Placa:** ESP32-S3 (Soporte Nativo USB habilitado `USB CDC On Boot = Enabled`).
- **Control de energía:** Pines dedicados (Pin 2, 41, 42) para habilitación selectiva de módem e interrupción de la alimentación de periféricos.

## Mapeo de Sensores (V0.2)
El sistema utiliza una construcción dinámica de URL basada en el `DEVICE_ID_STR`.

| ID (`DEVICE_ID_STR`) | BaseID | Notas |
| :--- | :--- | :--- |
| "1" a "10" | 4xx | Sensores estándar |
| "80", "81", "82" | 9xx | Sensores serie 8x |
| "01M" | 10xx | Multi-Sensor Especial |

---

## Autoría
**Autor:** Alejandro Rebolledo  
**Contacto:** arebolledo@udd.cl / edo@udd.cl

## Descargo de Responsabilidad
Este proyecto de código y los archivos binarios asociados se entregan **"tal cual"** (as is), sin garantías de ningún tipo, explícitas o implícitas, incluyendo, pero no limitado a, garantías de comercialización, idoneidad para un propósito particular o no infracción. El usuario utiliza este software y/o hardware asociado bajo su propio riesgo. Los autores no serán responsables por ninguna reclamación, daño u otra responsabilidad legal, ya sea en una acción de contrato, agravio o cualquier otra forma, que surja o esté en conexión con el uso del sistema.

## Licencia
Este proyecto y toda su documentación y código fuente se publican bajo la licencia **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**. 
Para ver el texto legal completo, por favor refiérase al archivo `LICENSE` incluido en este repositorio.

- ✅ Puede compartir y adaptar el contenido, siempre y cuando otorgue el crédito adecuado.
- ❌ **No puede utilizar este material para fines comerciales** sin previa autorización expresa del autor.
