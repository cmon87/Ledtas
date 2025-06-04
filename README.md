# Ledtas
Tas met ledmatrix

//arrays
uint16_t XY(uint8_t x, uint8_t y) {
  if (x < 8) {
    // Linkermatrix: normaal
    if (y % 2 == 0) {
      return y * 8 + x;
    } else {
      return y * 8 + (7 - x);
    }
  } else {
    // Rechtermatrix: spiegel X-as binnen paneel
    uint8_t rx = 15 - x; // <-- x=8 wordt 7, x=15 wordt 0
    if (y % 2 == 0) {
      return 256 + y * 8 + rx;
    } else {
      return 256 + y * 8 + (7 - rx);
    }
  }
}
