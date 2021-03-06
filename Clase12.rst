.. -*- coding: utf-8 -*-

.. _rcs_subversion:

Clase 12 - POO 2019
===================
(Fecha: 26 de abril)


Obtener una imagen desde internet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: c

	void Principal::slot_descargaFinalizada(QNetworkReply *reply)  {
	    QImage image = QImage::fromData(reply->readAll());
	}


**Algunas particularidades de QNetworkReply y QNetworkRequest**

- Para controlar los bytes que se van descargando se puede usar la señal de QNetworkReply:

.. code-block:: c

	void downloadProgress(qint64 bytesRecibidos, qint64 bytesTotal)

- Los campos de la cabecera HTTP se pueden setear con el método de QNetworkRequest:

.. code-block:: c

	void setRawHeader(const QByteArray &nombre, const QByteArray & valor)

	QNetworkRequest request;
	request.setUrl(QUrl(ui->le->text()));
	request.setRawHeader("User-Agent", "MiNavegador 1.0");


**Ejercicio 8**

- Buscar el correspondiente valor de User-Agent para un navegador en Android y otro para PC
- Realizar una interfaz que permita colocar en un QLineEdit la url de una página web
- Validar que si el usuario no escribe el www, que lo agregue, y si no coloca https://, que lo agregue.
- Realizar dos consultas a la página web con ambos valores de User-Agent
- Mostrar en dos QTextEdit el código fuente de ambas páginas.
- Comparar si los códigos son iguales y que un QLabel muestre "Iguales" o "Distintos" según corresponda.

**Ejercicio 9**

- Crear una clase Barra para dar funcionalidad a una barra de progreso
- Que la barra tenga el siguiente aspecto:

.. figure:: images/clase12/progressbar.png

- Debe tener métodos para setear su valor en porcentaje
- Usar la señal de downloadProgress de QNetworkReply
- Crear una interfaz que tenga un QLineEdit para la URL y una Barra.
- Probarlo con alguna URL que pertenezca a un archivo de tamaño superior a 50MB


