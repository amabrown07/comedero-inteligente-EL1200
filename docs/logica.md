# Lógica del comedero

1. El ESP32 lee el sensor PIR (GPIO 2).
2. Si detecta movimiento y todavía no ha servido comida
   (dispensado = false):
   - Mueve el servo a 140° (abre la compuerta).
   - Enciende el LED.
   - Espera 1,5 segundos.
   - Regresa el servo a 40° (cierra la compuerta) y apaga el LED.
   - Cambia dispensado a true.
3. Si ya no hay movimiento y dispensado es true,
   regresa dispensado a false: queda listo para la próxima vez.
