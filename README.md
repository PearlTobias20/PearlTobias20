#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <graphics.h>

void drawHappyNewYear() {
    setcolor(YELLOW);
    settextstyle(BOLD_FONT, HORIZ_DIR, 5);
    outtexttxy(100,200, "Happy New Year") ;
} 
void drawFireworks(int x, int y) {
    for (int i = 0; i < 10; i++) {
        int angle = rand() % 360;
        int length = rand() % 100 + 50;
        int endX = x + length * cos(angle * M_PI / 180);
        int endY = y + length * sin(angle * M_PI / 180);
        line(x, y, endX, endY);
}
}

int main() {
    int gd = DETECT, gm;
    initgraph(&gd, &gm, "");

    while (1) {
        cleardevice();
        drawHappyNewYear();
        for (int i = 0; i < 5; i++) {
            int x = rand() % getmaxx();
            int y = rand() % getmaxy();
            drawFireworks(x, y);
        }
        delay(1000);
    }

    closegraph();
    return 0;
}        
    
