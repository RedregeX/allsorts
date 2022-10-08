#include <iostream>
#include <SFML/Graphics.hpp>
#include <ctime>
#include "drawingh.h"
#include "bubblesort.h"
#include <windows.h>
using namespace sf;

const int WINDOW_WIDTH = 1260;
const int WINDOW_HEIGHT = 720;
const int w = WINDOW_WIDTH / 5;
const int h = WINDOW_HEIGHT;

void drawArray(RenderWindow& window, int* s, int size) {
    int width = WINDOW_WIDTH / w;
    for (int i = 0; i < w; i++) {
        RectangleShape shape(Vector2f(width, s[i]));
        shape.setPosition(width * i, h - s[i]);
        shape.setFillColor(Color(255, 0, 0));
        window.draw(shape);
    }
}

void bubblesort(int* s, int len, RenderWindow& window) {
    for (int i = 0; i < len; i++) {
        for (int j = len - 1; j > i; j--) {
            if (s[j] < s[j - 1]) {
                std::swap(s[j], s[j - 1]);
                drawArray(window, s, len);
            }
        }
    }
}

int main() {
    RenderWindow window(VideoMode(WINDOW_WIDTH, h), "Sorts!");
    srand(time(0));
    int s[w];
    for (int i = 0; i < w; i++) {
        s[i] = rand() % (h - 10) + 10;
    }
    while (window.isOpen())

    {

        sf::Event event;

        while (window.pollEvent(event))

        {

            if (event.type == sf::Event::Closed)

                window.close();
            std::cout << event.type << std::endl;
        }

        window.clear();
        bubblesort(s, w, window);
        window.display();

    }

}