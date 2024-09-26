# Solemne 1 - 2022
1. **El rango de frecuencias de trabajo de la luz visible es:** b) 430 THz a 770 THz
    
2. **Intensity Modulation/Direct Detection (IM/DD) se refiere a:** b) La señal óptica debe ser real y positiva
    
3. **La ventaja comparativa entre un LED y un Láser para sistemas VLC es:** d) Todas las anteriores
    (Mayor seguridad para el ojo humano, menor costo, mayor rango de longitud de ondas)
    
4. **En la transmisión óptica, la principal diferencia entre sistemas VLC y RF es:** c) Ninguna de las demás respuestas
    (El DC bias no es exclusivo de VLC y RF)
    
5. **En la recepción óptica, las partes principales que componen el fotoreceptor son:** c) Fotodiodo, concentrador y filtro
    
6. **La componente de canal VLC que más potencia aporta es:** a) Componente LoS 
    (LoS: Line-of-Sight, o línea de vista)
    
7. **La variable que más afecta a la componente de canal LoS es:** g) Distancia entre LED y PD  
    (PD: Fotodetector)
    
8. **La respuesta al impulso del canal es:** b) La métrica que verifica el efecto del canal de un sistema de comunicaciones
    
9. **Los criterios para escoger un esquema de modulación son:** c) Eficiencia de ancho de banda, eficiencia de potencia y confiabilidad de la transmisión
    
10. **La modulación óptica que tiene mejor eficiencia espectral es:** b) 4-PAM
    (4-PAM tiene una mejor eficiencia espectral que las otras opciones)

![[Pasted image 20240924194510.png]]
1. Se usan las formulas ![[Pasted image 20240906163656.png]] ![[Pasted image 20240906162547.png]]
1. 
	m y g = 1
	 inc = 30°
	 irr = 45°
	 d  = ?
	 Ap = ?
	 distancia = sqrt[1^2+3^2] = sqrt(10)
	 Ap = Aeff / cos(30°) 
	 Ap = 12 mm^2 / cos(30°)
	 Ap = 13.8564 mm^2
	 Ap = 13.8564 x 10^-6 m^2
	 Ap = 1.38564 x 10^-5 m^2
	 H = 2 x Ap x cos(45°) x cos(30°) / (2 x pi x 10)
	 H = 2.7 x 10^-7
	 t=?
	 v=d/t
	 t=d/v
	 t=d/c
	 t= sqrt(10) / (3x10^8)
	 t= 1.054093 x 10^-8
	 t = 0.1054093 ns
	 
![[Pasted image 20240924205859.png]]
2. asd
Preguntas:
1. ¿Cuánto tiempo tardará el pulso de luz en viajar desde la bombilla LED hasta el fotodiodo a una distancia de 2 metros?  
	R// 
		t = d / c = 2 / (3 x 10^8)
		t = 6.6666 nanosegundos
2. Suponiendo que el pulso de luz emitido por la bombilla LED tiene una duración de 10  
nanosegundos, ¿cuál será la duración temporal del impulso eléctrico generado por el fotodiodo en respuesta al pulso de luz?  
	R// 
3. Utilizando la sensibilidad del fotodiodo y la intensidad máxima de la luz emitida por la bombilla LED, calcula la corriente máxima generada por el fotodiodo como resultado del pulso de luz.
	R// 

# Solemne 1 - 2023
2. Calcular la respuesta al impulso de la componente de canal LoS de un sistema  
VLC bajo los siguientes parámetros:  
• Ángulo de incidencia: 20°  
• Ángulo de irradiancia: 60°  
• Posición del LED (x,y,z): (4, 3, 7)  
• Posición del PD (x,y,z): (2, 3, 1)  
• Área física del PD: 15 mm²  
• Ganancia unitaria y modo lambertiano de 1.

 ![[Pasted image 20240906163656.png]]
  ![[Pasted image 20240906162547.png]]
  d = sqrt(2^2 + 6^2) = sqrt(40)
  H = 2 x 15 x 10^-6 x cos(60°) x cos(20°) / (2 x pi x 40)
  H = 5.60838 x 10 ^-8
  t = sqrt(40) / (3x10^8)
  t = 2.108185 x 10^-8
  t = 0.2108185 ns
  ![[Pasted image 20240925183158.png]]