# Proyecto-de-Proyecto-juego-de-serpiente-
juego 2D de la serpiente para el proyecto de proyecto

#include <Adafruit_GFX.h>
#include <Adafruit_ST7735.h>
#include <SPI.h>

//librerias arriba

#define TFT_CS  10 //conexion de CS
#define TFT_DC  9  //conexion de A0
#define TFT_RST 8  //conexion de Reset
Adafruit_ST7735 pantalla = Adafruit_ST7735(TFT_CS, TFT_DC, TFT_RST);  //hace algo
int serpientepos[] = {65,70};  //posicion de la serpiente (X, Y)

void setup() 
{
  pantalla .initR(INITR_BLACKTAB);  //inicia la pantalla
  pantalla .fillScreen(ST77XX_WHITE);  // rellena la pantalla(fondo)
  
  pantalla.setTextSize(2);             // Tamaño del texto (1 es el más chico, 2 es mediano, etc.)
  pantalla.setTextColor(ST77XX_BLACK); // Color del texto (Letras negras)
  pantalla.setCursor(35, 30);          // Posición del cursor en la pantalla (X=35, Y=30)
  pantalla.print("Nivel");             // El texto que querés mostrar
  
  pantalla .fillCircle(serpientepos[0],serpientepos[1],3, ST77XX_GREEN);  //cabeza de serpiente(posX, posY, radio, color)
  pantalla.fillRect(serpientepos[0]-2,serpientepos[1]+3, 5, 10, ST77XX_GREEN);  //cuerpo de la serpiente (posX, posY, ancho, alto, color)
  pantalla.drawPixel(serpientepos[0]-2,serpientepos[1]-1, ST77XX_BLACK);  //ojo 1 (posX, posY, color)
  pantalla.drawPixel(serpientepos[0]+2,serpientepos[1]-1, ST77XX_BLACK);  //ojo 2 (posX, posY, color)
  pantalla.drawLine(serpientepos[0], serpientepos[1]-2, serpientepos[0], serpientepos[1]-3, ST77XX_RED);  //lengua serpiente (posX 0(inicio de linea), posY 0(inicio de linea), posX 1(fin de linea), posY 1(fin de linea), color)
  
}


void loop() 
{




}
