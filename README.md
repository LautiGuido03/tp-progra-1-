package juego;

import java.awt.Color;

import entorno.Entorno;

public class Boton {
    int x; 
    int y; 
    int ancho; 
    int alto; 
    String texto; 
    boolean presionado; 

    public Boton(int x, int y, int ancho, int alto, String texto){
        this.x = x; 
        this.y = y; 
        this.ancho = ancho; 
        this.alto = alto; 
        this.texto = texto; 
    }

    public boolean fuePresionado(int mouseX, int mouseY, boolean clickDerecho){
        if(clickDerecho && mouseX >= x - ancho / 2 && mouseX <= x + ancho / 2 && mouseY >= y - alto / 2 && mouseY <= y + alto / 2) {
            return true; 
        }
        return false; 
    }

    public void setPresionado(boolean valor){
        this.presionado = valor; 
    }

    public boolean estaPresionado(){
        return this.presionado; 
    }

    public void escribirTexto(String texto){
        this.texto = texto; 
    }

    public void dibujar(Entorno entorno){
        Color color = Color.white; 
        if (presionado) {
            color = Color.green; 
        } else {
            color = Color.white; 
        }

        entorno.dibujarRectangulo(x, y, ancho, alto, 0, color); 
        entorno.escribirTexto(texto, 730, 100); 
        entorno.escribirTexto(texto, 730, 160);    
        //int desplazamiento = texto.length() * 3;  
        //entorno.dibujarTexto(x - desplazamiento, y + 5, Color.black, texto);     
    }
}
