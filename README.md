# RockPaperScissors
//RSP.cpp is as follows:

#include "pch.h"
#include <iostream>
#include <SFML/Graphics.hpp>
//#include <SFML/Mouse.hpp>
int main()
{
	sf::RenderWindow window(sf::VideoMode(800, 800), "RockPaperScissors!");
	sf::Texture t1,t2,t3;
	t1.loadFromFile("RPS/rock.jpg");
	t2.loadFromFile("RPS/paper.jpg");
	t3.loadFromFile("RPS/scissors.jpg");
	sf::Sprite s1(t1), s2(t2), s3(t3);
	s1.setPosition(320,320);
	s2.setPosition(320, 650);
	s3.setPosition(320,98);
	window.draw(s1);
	window.draw(s2);
	window.draw(s3);
	//window.display();

	sf::Vector2i position = sf::Mouse::getPosition();
	
	/// // set mouse position relative to a window
	sf::Mouse::setPosition(sf::Vector2i(800, 800), window);
	int user,ran;
	if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s1.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s1.getPosition()).y)))
	{
		user = 0;
		sf::Sprite s4(t1);
		s4.setPosition(650, 650);
		window.draw(s4);
	}
	if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s2.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s2.getPosition()).y)))

	{
		user = 1;

		sf::Sprite s4(t2);
		s4.setPosition(650, 650);
		window.draw(s4);
	}
	if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s3.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s3.getPosition()).y)))
		
	{
		user = 2;

		sf::Sprite s4(t3);
		s4.setPosition(650, 650);
		window.draw(s4);
	}



	while (window.isOpen())
	{
		sf::Event event;
		while (window.pollEvent(event))
		{
			if (event.type == sf::Event::Closed)
				window.close();
		}

		
		//sf::Mouse::setPosition(sf::Vector2i(800, 800), window);
		do {
			if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s1.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s1.getPosition()).y)))
			{
				sf::Sprite s4(t1);
				s4.setPosition(650, 650);
				window.draw(s4);
			}
			if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s2.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s2.getPosition()).y)))

			{
				sf::Sprite s4(t2);
				s4.setPosition(650, 650);
				window.draw(s4);
			}
			if (sf::Mouse::isButtonPressed(sf::Mouse::Right) && (((sf::Mouse::getPosition()).x) == ((s3.getPosition()).x)) && (((sf::Mouse::getPosition()).y) == ((s3.getPosition()).y)))

			{
				sf::Sprite s4(t3);
				s4.setPosition(650, 650);
				window.draw(s4);
			}

			window.display();
			 ran = rand() % 3;
			sf::Sprite s5(t1), s6(t2), s7(t3);
			switch (ran)
			{
			case 0:
			{s5.setPosition(650, 400);
			window.draw(s5); }
			break;
			case 1:
			{s6.setPosition(650, 400);
			window.draw(s6); }
			break;
			case 2:
			{s7.setPosition(650, 400);
			window.draw(s7); }
			break;
			default:
				break;
			}
		} while (user == ran);
		
		window.clear();

		//if (user == 2 && ran == 1) std::cout << "user is the winner." << std::endl;
		if (user == 2 && ran == 0) std::cout << "computer is the winner." << std::endl;
		else if (user == 0 && ran == 2) std::cout << "user is the winner." << std::endl;
		else if (user>ran) std::cout << "user is the winner." << std::endl;
		else std::cout << "computer is the winner." << std::endl;

		window.display();
		

	}

	return 0;
}
