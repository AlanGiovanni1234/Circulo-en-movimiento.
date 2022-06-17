//Circulo-en-movimiento.//

#include <SFML/Graphics.hpp>
#include <stdio.h>
int main()
{
    int ancho_window = 1500, alto_window = 900;
    int y_coord = alto_window / 2;
    int x_coord = ancho_window / 2;
    sf::RenderWindow window(sf::VideoMode(ancho_window, alto_window), "IntellVirtual!");
    sf::CircleShape circulo(200.f);
    circulo.setFillColor(sf::Color::Green);
    circulo.setPosition(x_coord, y_coord);
    
    while (window.isOpen())
    {
        sf::Event event;
        while (window.pollEvent(event))
        {
            if (event.type == sf::Event::Closed)
                window.close();
        }
        if (sf::Keyboard::isKeyPressed(sf::Keyboard::D))
            x_coord += 1;
        if (sf::Keyboard::isKeyPressed(sf::Keyboard::A))
            x_coord -= 1;
        if (sf::Keyboard::isKeyPressed(sf::Keyboard::W))
            y_coord -= 1;
        if (sf::Keyboard::isKeyPressed(sf::Keyboard::S))
            y_coord += 1;
        window.clear();
        circulo.setPosition(x_coord, y_coord);
        window.draw(circulo);
        window.display();
    }
    return 0;
}
