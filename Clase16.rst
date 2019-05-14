.. -*- coding: utf-8 -*-

.. _rcs_subversion:

Clase 16 - POO 2018 (No preparado aún)
===================
(Fecha: 14 de mayo)



**Google Maps**

- URL para su uso: https://developers.google.com/maps/documentation/staticmaps
- Ejemplo: http://maps.googleapis.com/maps/api/staticmap?center=rondeau+100+cordoba&zoom=15&size=500x300&maptype=roadmap&sensor=false
- Descripción de los parámetros en: https://developers.google.com/maps/documentation/staticmaps/#URL_Parameters
- Pueden habilitar otros servicios en https://code.google.com/apis/console


**Ejercicio 12** 

- Hacer una aplicación para buscar una dirección en Google Maps
- Definir la clase Mapa. Será el QWidget donde se dibujará el mapa de google.
- Definir la clase Ventana para contener al layout.
- Ese layout tendrá:
	- QLineEdit para ingresar un domicilio
	- QPushButton para buscar ese domicilio
	- Mapa
	- QSlider vertical para aumentar y disminuir el zoom



Uso de Qt Designer
..................

- Nuevo proyecto -> Qt GUI Application
- Utilizar el puntero ``ui`` para acceder a los objetos del diseño
- Tener en cuenta que los métodos virtuales de QWidget para eventos se pueden usar:

.. code-block:: c	

	virtual void mousePressEvent(QMouseEvent* event);
	virtual void resizeEvent(QResizeEvent* event);
	virtual void moveEvent(QMoveEvent* event);
	...

**Ejemplo**

.. code-block:: c	
	
	// ventana.h
	#ifndef VENTANA_H
	#define VENTANA_H

	#include <QWidget>

	namespace Ui {
	    class Ventana;
	}

	class Ventana : public QWidget  {
	    Q_OBJECT

	public:
	    explicit Ventana(QWidget *parent = 0);
	    ~Ventana();

	private:
	    Ui::Ventana *ui;
	};

	#endif // VENTANA_H

.. code-block:: c

	// ventana.cpp
	#include "ventana.h"
	#include "ui_ventana.h"

	Ventana::Ventana(QWidget *parent) : QWidget(parent), ui(new Ui::Ventana)  {
	    ui->setupUi(this);
	}

	Ventana::~Ventana()  {
	    delete ui;
	}



Un par de memes antes del examen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: images/clase10/meme2.jpg

.. figure:: images/clase10/meme4.jpg








