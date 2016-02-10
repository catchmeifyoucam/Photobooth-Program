//Photobooth-Program
//Program using SFML Graphics via XCode in language C++

//Camille Ruiz-Funes
//Independent Study
//"photobooth" manipulation

#include <SFML/Graphics.hpp>
#include <SFML/OpenGL.hpp>
#include <SFML/Window.hpp>
#include <iostream>
#include "ResourcePath.hpp"

int main() {
    
    //create a window
    sf::RenderWindow window;
    window.create(sf::VideoMode(1140,800), "SFML Photobooth");
   
    //create a dialog window
    sf::RenderWindow dialwind;
    dialwind.create(sf::VideoMode(425,210), "Photobooth Instructions");
    
    
    //create texture, load file
    sf::Texture texture;
    if(!texture.loadFromFile(resourcePath() + "NGTC.jpg"))
        std::cout<< "Error! Could not load image" << std::endl;
    
    //openGL
   // glEnable(Gl_TEXTURE_2D);
    //sf::Texture::bind(& texture); //select this texxture for openGL rendering
    
   //create another texture, limit the amount of textures made, because they are slow and costly
    sf::Texture texture2;
    if(!texture2.loadFromFile(resourcePath() + "imgres.jpg"))
        std::cout<< "Error! Could not load image" << std::endl;
        texture2.setRepeated(true);
    
    //font
    sf::Font font;
    if(!font.loadFromFile(resourcePath() + "sansation.ttf"));
     std::cout<< "Error! Could not find font" << std::endl;
    
    //text
    sf::Text text("Gradient", font, 20);
    text.setColor(sf::Color::Black);
    text.setPosition(40.f, 10.f);
    
    sf::Text text2("Transparency", font, 20);
    text2.setColor(sf::Color::Black);
    text2.setPosition(40.f, 255.f);
    
    sf::Text text3("Color Change", font, 20);
    text3.setColor(sf::Color::Black);
    text3.setPosition(40.f, 500.f);

    
    sf::Text text4("Repeated", font, 20);
    text4.setColor(sf::Color::Black);
    text4.setPosition(590.f, 10.f);
    
    sf::Text text5("Direction Change", font, 20);
    text5.setColor(sf::Color::Black);
    text5.setPosition(590.f, 500.f);
    
    
    
    sf::Text dwtext("Welcome to SFML Photobooth!", font, 25);
    dwtext.setPosition(10,5);
    dwtext.setColor(sf::Color(65, 105, 225));
    sf::Text dwtext2("To interact with SFML Photobooth, follow these directions:", font, 15);
    dwtext2.setPosition(10,35);
    dwtext2.setColor(sf::Color(123,104, 238));
    sf::Text dwtext3("   For Gradient, press G", font, 15);
    dwtext3.setPosition(10, 60);
    dwtext3.setColor(sf::Color(123,104,238));
    sf::Text dwtext4("   For Transparency , press numbers 2, 5, and 7", font, 15);
    dwtext4.setPosition(10,80);
    dwtext4.setColor(sf::Color(123,104,238));
    sf::Text dwtext5("   For Color, press letters B, Y. and P", font, 15);
    dwtext5.setPosition(10,100);
    dwtext5.setColor(sf::Color(123,104,238));
    sf::Text dwtext6("   For Repeated, press T", font, 15);
    dwtext6.setPosition(10,120);
    dwtext6.setColor(sf::Color(123,104,238));
    sf::Text dwtext7("   For Direction, press the up, down, and right arrow keys", font, 15);
    dwtext7.setPosition(10,140);
    dwtext7.setColor(sf::Color(123,104, 238));
    sf::Text dwtext8("To begin, click anywhere on SFML Photobooth and refer back", font, 15);
    dwtext8.setPosition(10,165);
    dwtext8.setColor(sf::Color(123,104, 238));
    sf::Text dwtext9(" to this box as needed. Enjoy!", font, 15);
    dwtext9.setPosition(10,181);
    dwtext9.setColor(sf::Color(123,104, 238));
    
    
 

    //create a sprite.
    sf::Sprite sprite;
    sprite.setTexture(texture);
    sprite.setPosition(40.f, 40.f);
    sprite.setScale(.5f, .3f);
    
        sf::Sprite sprite1;
        sprite1.setTexture(texture);
        sprite1.setPosition(40.f, 40.f);
        sprite1.setScale(.5f, .3f);
        sprite1.setTextureRect(sf::IntRect(0, -688, 1000, 688));
    
    //transparent sprite series
    sf::Sprite sprite2;
    sprite2.setTexture(texture);
    sprite2.setPosition(40.f, 285.f);
    sprite2.setScale(.5f, .3f);
    
        sf::Sprite sprite21;
        sprite21.setTexture(texture);
        sprite21.setPosition(40.f,285.f);
        sprite21.setScale(.5f, .3f);
        sprite21.setColor(sf::Color(255,255,255,192)); //.75 transparent
    
        sf::Sprite sprite22;
        sprite22.setTexture(texture);
        sprite22.setPosition(40.f,285.f);
        sprite22.setScale(.5f, .3f);
        sprite22.setColor(sf::Color(255,255,255,128)); //.5 transparent
    
    
        sf::Sprite sprite23;
        sprite23.setTexture(texture);
        sprite23.setPosition(40.f,285.f);
        sprite23.setScale(.5f, .3f);
        sprite23.setColor(sf::Color(255,255,255,64)); //.25 transparent
    

    //repetition series
    sf::Sprite sprite3;
    sprite3.setTexture(texture2);
    sprite3.setPosition(590.f, 40.f);
    sprite3.setScale(.275f, .273f);
    
        sf::Sprite sprite31;
        sprite31.setTexture(texture2);
        sprite31.setTextureRect(sf::IntRect(0,0, 1850,2235));
        sprite31.setPosition(590.f, 40.f);
        sprite31.setScale(.275f, .2f);
    
    //color series
    sf::Sprite sprite4;
    sprite4.setTexture(texture);
    sprite4.setPosition(40.f, 530.f);
    sprite4.setScale(.5f, .3f);
    
        sf::Sprite sprite41;
        sprite41.setTexture(texture);
        sprite41.setPosition(40.f, 530.f);
        sprite41.setScale(.5f, .3f);
        sprite41.setColor(sf::Color(0,205, 205));
    
        sf::Sprite sprite42;
        sprite42.setTexture(texture);
        sprite42.setPosition(40.f, 530.f);
        sprite42.setScale(.5f, .3f);
        sprite42.setColor(sf::Color(255, 52, 179));
    
        sf::Sprite sprite43;
        sprite43.setTexture(texture);
        sprite43.setPosition(40.f, 530.f);
        sprite43.setScale(.5f, .3f);
        sprite43.setColor(sf::Color(255, 165, 0));
    
    
    //direction series
    sf::Sprite sprite5;
    sprite5.setTexture(texture);
    sprite5.setPosition(590.f, 530.f);
    sprite5.setScale(.5f, .3f);
    
        sf::Sprite sprite51;
        sprite51.setTexture(texture);
        sprite51.setTextureRect(sf::IntRect(1000, 0, -1000,688));
        sprite51.setPosition(590.f, 530.f);
        sprite51.setScale(.5f, .3f);
    
        sf::Sprite sprite52;
        sprite52.setTexture(texture);
        sprite52.setTextureRect(sf::IntRect(0, 688, 1000, -688));
        sprite52.setPosition(590.f, 530.f);
        sprite52.setScale(.5f, .3f);
    
        sf::Sprite sprite53;
        sprite53.setTexture(texture);
        sprite53.setTextureRect(sf::IntRect(1000, 688, -1000, -688));
        sprite53.setPosition(590.f, 530.f);
        sprite53.setScale(.5f, .3f);
    
    //run as long as the window is open
    while (window.isOpen())
    {
        
        //clear window before rendering new frame
        
        window.clear(sf::Color::White);
       /* window.draw(sprite);
        window.draw(sprite2);
         window.draw(sprite3);
         window.draw(sprite4);
         window.draw(sprite5);
        */
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::G)) {
            window.clear(sf::Color::White);
            window.draw(sprite1);
        }
        else if(sf::Keyboard::isKeyPressed(sf::Keyboard::Num2)) {
            window.clear(sf::Color::White);
            window.draw(sprite21);
            
        }
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Num5)){
            window.clear(sf::Color::White);
            window.draw(sprite22);
       
        }
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Num7)){
            window.clear(sf::Color::White);
            window.draw(sprite23);
        }
        
        //color
        window.draw(sprite4);
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::B)){
            window.clear(sf::Color::White);
            window.draw(sprite41);
        }
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::P)){
            window.clear(sf::Color::White);
            window.draw(sprite42);
        }
    
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Y)){
            window.clear(sf::Color::White);
            window.draw(sprite43);
        }
        
        
        //direction
         window.draw(sprite5);
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Right)){
            window.clear(sf::Color::White);
            window.draw(sprite51);
            
        }
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Down)){
            window.clear(sf::Color::White);
            window.draw(sprite52);
          
        }
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::Up)){
            window.clear(sf::Color::White);
            window.draw(sprite53);
       
        }
        
        //repetition
        window.draw(sprite3);
        if(sf::Keyboard::isKeyPressed(sf::Keyboard::T)){
            window.clear(sf::Color::White);
            window.draw(sprite31);
          
        }
     
        //make an event
        sf::Event event;
        while(window.pollEvent(event))
        {
            //close window
            if(event.type == sf::Event::Closed)
                window.close();
            
            //if escape key is pressed, close window
            if(event.type == sf::Event::KeyPressed && event.key.code == sf::Keyboard::Escape)
                window.close();
        }
        
      
     
        //draw text
        window.draw(text);
        window.draw(text2);
        window.draw(text3);
        window.draw(text4);
        window.draw(text5);
        
        dialwind.draw(dwtext);
        dialwind.draw(dwtext2);
        dialwind.draw(dwtext3);
        dialwind.draw(dwtext4);
        dialwind.draw(dwtext5);
        dialwind.draw(dwtext6);
        dialwind.draw(dwtext7);
        dialwind.draw(dwtext8);
        dialwind.draw(dwtext9);

        window.
     
        //update the window
        window.display();
        dialwind.display();
    
        }
    return;
        
    }



