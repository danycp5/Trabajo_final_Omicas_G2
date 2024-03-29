# Tema:

# Anotación del genoma bacteriano de *Staphylococcus aureus* resistente a la meticilina 

**Autores:** 
+ Adriana Aguirre
+ Daniela Calderón
+ Patricia Dávalos

**Fecha:**  febrero de 2024

## PROBLEMA

*Staphylococcus aureus* es la especie patógena más prominente dentro de su género y es responsable de muchas infecciones, tanto adquiridas en la comunidad como en entornos hospitalarios. El enfoque actual en el estudio de este microorganismo se debe a su alta incidencia y a su capacidad de causar brotes de infecciones nosocomiales, especialmente cuando se trata de cepas resistentes a la meticilina. 

La anotación genómica implica describir la estructura y función de los componentes genómicos mediante su predicción, análisis e interpretación para entender sus implicaciones biológicas. Esto incluye la identificación de la ubicación de los genes y las regiones codificantes (anotación estructural) junto con la determinación de sus roles biológicos (anotación funcional). Como ejemplo, consideramos el proceso de anotación de un genoma bacteriano utilizando el ensamblaje de genoma bacteriano basado en datos de secuenciación de cepas de *Staphylococcus aureus* resistentes a la meticilina aisladas en Japón (García et.al, 2019).

## ANTECEDENTES
La resistencia a los antibioticos representa una prioridad en la salud pública a nivel mundial. Entender su impacto frente a los importantes cambios demográficos que están ocurriendo globalmente es una área de conocimiento esencial que requiere ser abordada. Según estimaciones de la Organización Mundial de la Salud, se prevé que para el año 2050 una de cada cinco personas en el mundo tendrá 60 años o más. Es sabido que la incidencia de infecciones bacterianas aumenta con la edad y varía según el género. El incremento de las infecciones en grupos etarios avanzados resulta en una mayor exposición a los antibióticos y un mayor contacto con ambientes médicos, los cuales son reconocidos como puntos críticos de transmisión de bacterias resistentes. Sin embargo, no se observa un aumento simple de la resistencia en todos los patógenos según la edad. Comprender cómo estas interacciones impulsan la dinámica de las infecciones resistentes a los medicamentos es crucial para entender la mejor manera de abordar la resistencia a antibioticos (walterlow NR, et al., 2024).

El empleo de antibióticos, la exposición a ambientes sanitarios con alta incidencia de transmisión y las modificaciones en la actividad del sistema inmunitario difieren en función de la edad y el género del individuo. A pesar de ello, la mayoría de los estudios sobre la resistencia a los antimicrobianos no toman en cuenta los factores demográficos y únicamente ofrecen datos sobre la prevalencia de la resistencia a nivel nacional (Gagliotti C, et al., 2018).


Las cepas resistentes a la meticilina (SARM) fueron identificadas casi inmediatamente después de la introducción de la meticilina en el tratamiento médico. Los primeros casos de brotes de infección nosocomial se registraron en hospitales europeos a principios de la década de 1960. Desde entonces, la prevalencia de estas cepas ha ido en aumento en la mayoría de las regiones del mundo. En nuestro país, los estudios sobre los aislados de SARM muestran un aumento significativo, pasando de un 1,5% en 1986 a un rango del 18 al 23% en 1996. Este incremento ha llevado a que ciertas áreas hospitalarias, especialmente aquellas consideradas de alto riesgo como las Unidades de Cuidados Intensivos, se conviertan en zonas endémicas para este tipo de infección. Algunas investigaciones realizadas en ciertos periodos incluso han reportado cifras de hasta un 40%  (Grupo de Trabajo EPINE, 1995; Cercenado et
al.,1997).
La infección causada por *Staphylococcus aureus* es de gran importancia clínica y representa un desafío significativo para la salud pública. La presencia de *S. aureus* resistente a la meticilina dificulta el tratamiento de infecciones graves, lo que resulta en un aumento de la morbilidad, mortalidad y costos adicionales. Además, contribuye significativamente a la carga de resistencia a los antimicrobianos.

## OBJETIVOS
+ Evaluar la calidad de las secuecuencias de *Staphylococcus aureus* mediante la herramienta virtual Galaxy.
+ Elaborar la anotación del genoma bacteriano de *Staphylococcus aureus*, mediante el uso de la herramienta  virtual Bakta.
  
## FLUJO DE TRABAJO

[Pipeline](https://app.diagrams.net/#Hdanycp5%2FTrabajo_final%2Fpipeline%2FDiagrama%20sin%20t%C3%ADtulo.drawio#%7B%22pageId%22%3A%22lsY_AHojMyWDu4EsEvxC%22%7D)

## MÉTODOLOGÍA
Primero se cargó la secuencia e *Staphylococcus aureus* a la plataforma Galaxy como se observa en la figura 1.
![Configuracion_de_bakta](imagenes/2.jpg)

Se cambió el nombre a historial como se observa en la figura 2.

![Cambio_ de_nombre](imagenes/1.jpg)
Después se realizó el analisis de calidad utilizando la herramientafastQC (figura 3).

![analisis_calidad](imagenes/33.jpeg)

Se realizó la configuración de la herramienta Bakta, la cual consistió en ir a  "Opciones de entrada/salida": y dar clic en  "La base de datos de bakta" y seleccionar la más reciente "La base de datos de amrfinderplus". Después, en la más reciente Archivo de parámetros "Seleccionar genoma en formato fasta": Archivo de contig En "Anotación opcional": "Mantener encabezado original del contig (--keep-contig-headers)": S ( ver figura 4).

![carga_de_scuencia](imagenes/3.jpg)



Para configurar los output en la herramienta bakta, se dió clic en "Selección de los archivos de salida": "Selección de archivos de salida": Archivo de anotación en TSV Anotación y secuencia en GFF3 Secuencias de nucleótidos de características como FASTA Resumen como TXT Gráfico del resultado de la anotación como SVG. Como se observa en la figura 5.

![Configuracion_output](imagenes/4.jpg)

Posteriormente, se realizó el análisis de la secuencia en archirvo fasta y se hizo un resumen de las anotaciones como TSV simples y legibles por humanos. Seguidamente, se realizó la anotación de la secuencia en GFF3 para describir genes y otras características de secuencias biológicas.

Bakta ofrece una cantidad considerable de datos, principalmente relacionados con CDS o  ARNy, sin embargo, es probable que algunas anotaciones estructurales importantes, como los plásmidos, no estén incluidas es por eso que se realizó la identificación de plásmidos en los contigs previamente realizados, para esto se utilizó la herramienta **PlasmidFinder** (figura 6).

![Identificacio_plasmidfinder](imagenes/10.jpg)

Después, se utilizó el archivo plasmid.fasta que contenía las secuencias que mejor coincidian del genoma utilizado y el archivo hit_in_genome.fasta ue contenía los genes plasmídicos que mejor coincidián de la base de datos ( figura 7).

![deteccion_integrones](imagenes/15.jpg) 

Se utilizó la herramienta IntegronFinder para detectar integrones y ISEScan para detectar los elementos IS ( secuencia de inserción) los cuales estan presentes en la anotación estructural adicional de la bacteria.
Para la visualización de la anotación se utilizó las idendificadas por Bakta, las secuencias de plásmidos identificadas por PlasmidFinder, los integrones identificados por IntegronFinder y los elementos IS identificados por ISEscan. Se utilizó la herramienta JBrowse, la cual necesitó que los archivos anteriormente mencionados esten en formato GFF y para esto se formateó las salidas de las secuencias de los integrones y plásmidos como se muestra en las figuras 8-14.

![visualización_anotacion](imagenes/24.jpg) ![visualización_anotacion](imagenes/25.jpg) ![visualización_anotacion](imagenes/26.jpeg) ![visualización_anotacion](imagenes/27.jpeg)![visualización_anotacion](imagenes/28.jpg) ![visualización_anotacion](imagenes/29.jpg)![visualización_anotacion](imagenes/30.jpg)


## RESULTADOS
El análisis de calidad con FastQc comprobó que la secuencia de *Staphylococcus aureus* cumplió con todos los estandares de calidad, demostrando que es una secuencia apta para el posterior análisis (Figura 15).
![Resultado_calidad](imagenes/34.jpeg)


En la herramienta bakta, como se observa en la figura 16, se obtuvieron 44 contigs como entrada con una duración del borrador del genoma de 2.911.349 pb, un poco más corto que los 2.914.567 pb esperados.

![resumen_de_analisis](imagenes/5.jpg)


Se encontró 2.717 CDS, un poco más que los 2.704 CDS esperados y de proteínas pequeñas 5 SORF, también, se encontró otros componentes como: 
                                                                
 | Comonetes  | Bakta | Hikichi et al2019 |
 | ------------- | ------------- |  ------------- |
 | ARNt | 57 | 61 |
 | ARNm de transferencia | 1 | 1 |
 | ARNr | 9  | 5 |
 | mcRNA | 95  | sin información |


En el análisis de la secuencia en archivo fasta se observó que existieron 2884 secuencias, en las cuales se encontraba ARNt, ARNm, ARNr, ncARN, CDS y SORF ( figura 17).

![resultados_nucleotid](imagenes/6.jpg)


Además, en el resumen obtenido en las anotaciones se encontró Sequence Id, Type, Start, Stop, Strand, Locus Tag, Gene, Product, DbXrefs, las cuales contenían 2.916 líneas ( figura 18).

![resultados_summary](imagenes/7.jpg)

Se observó que existe 51k+ (número de líneas en el GFF), como se observa en la figura 19. 
![resultados_GFF3](imagenes/8.jpg)

En la figura 20 se visualiza la trama de anotación del genoma circular, en la cual el círculo inicial muestra el contenido de GC en cada ventana deslizante de todas las secuencias, donde el color verde indica valores por encima del promedio y el color rojo indica valores por debajo. En el segundo círculo se muestra la tendencia del contenido de GC en tonos naranja y azul. Además, se han representado todas las características en dos anillos que muestran la hebra delantera y trasera de afuera hacia adentro, con las secuencias codificantes en gris (los demás colores son complicados de diferenciar).

![genoma_circular](imagenes/9.jpg)


En las figuras 21 y 22 se observan los diferentes resultados que generó plasmidFinder, los cuales son archivos de texto que contienen la tabla de resultados y las alineaciones.

![resultados_plasmidfinder](imagenes/11.jpg) ![resultados_plasmidfinder](imagenes/12.jpg)

Posterior al análisis en la herramienta PlasmidFinder se encontró 5 secuencias de plásmidos, los cuales estaban ubicados de la sigueinte manera: 3	están en contig00019, 1 en contig00002 y 1 en contig00024. 
Donde todas las secuencias de plásmidos correspondientes a los plásmidos de *Staphylococcus aureus* están todas en contig00019, lo que hace que este contig probablemente sea un plásmido. Además, tiene una longitud de 30.347 pb.
Así mismo, al comparar las secuencias asociadas con  *Staphylococcus aureus* en NCBI se encontró que CP000737, AP003139 (2 veces) corresponden a plásmidos de *Staphylococcus aureus*, AF503772 corresponde a un plásmido de *Enterococcus faecalis*, CP003584 corresponde a un plásmido de *Enterococcus faecium*.

 Los resultados provenientes de los archivos  plasmid.fasta y el archivo hit_in_genome.fasta se observan en las figuras 23 y 24 respectivamente.
 
![resultados_plasmmidFasta](imagenes/13.jpg) ![resultados_hit](imagenes/14.jpg) 
 

Los integrones son componentes genéticos que posibilitan a las bacterias ajustarse y desarrollarse rápidamente mediante la captura y expresión de genes nuevos. Un integron típico consta de un gen que codifica una enzima específica de recombinación (intI), un sitio de recombinación cercano (attI) donde se pueden insertar segmentos de genes, y un controlador de transcripción (Pc) que regula la actividad genética en estos segmentos. Para identificar integrones, se recurre a herramientas como IntegronFinder (Néron et al., 2022). En la figura 24 se puede observar que no se encontró  elementos integrones en ningún contig, esto podría deberse ya que el genoma es demasiado estable o a que la calidad del ensamblaje no es lo suficientemente buena y se eliminaron algunas partes útiles para la detección de integrones. 

![resultados_integron_finder](imagenes/16.png) 

En las figuras 25-29, se observó los resultados de la secuencia de inserción empleando la herramienta ISEScan, la cual permitió detectar los elementos de secuencia de inserción (IS), que es una breve secuencia de ADN que funciona como un elemento transponible básico. Estos IS son los más diminutos, pero también los más comunes de los elementos transponibles autónomos que se encuentran en los genomas bacterianos. Su código genético se limita únicamente a las proteínas relacionadas con la actividad de transposición, lo que los convierte en actores fundamentales en la estructura y la evolución de los genomas bacterianos.

![secuencias_insercion](imagenes/17.jpg) ![secuencias_insercion](imagenes/18.jpg) ![secuencias_insercion](imagenes/19.jpg) ![secuencias_insercion](imagenes/20.jpg) ![secuencias_insercion](imagenes/21.jpg) 


Además, como se observa en la figura 30 y 31, la herramienta permitió obtener la secuencia de aminoácidos ORF, detectectando así 20 elementos de insersión (IS), los cuales se encontraron agrupados como se observa en la tabla 2. 

![nucleotidos_ORF](imagenes/22.jpg)![aminoacidos_ORF](imagenes/23.jpg)

| Contig  | Numero de elemento IS |
| ------------- | ------------- |
| contig00001  | 2  |
| contig00002 | 1 |
| contig00003  | 2  |
| contig00004 | 1 |
| contig00005  | 1  |
| contig00006 | 1 |
| contig00009  | 3  |
| contig00010 | 1|
| contig00011 | 1  |
| contig00012 | 1 |
| contig00019  | 3  |
| contig00027 | 1|
| contig00032  | 1  |
| contig00037 | 1 |
                                                                  

Dectectándose también, las diferentes familias del IS ( tabla 3)
| familia IS  | elemento IS identificado |
| ------------- | ------------- |
| IS1182  |4 |
| IS21|7|
|IS3 |3 |
| IS6 | 5|
| ISL3 | 1|

En la salida de JBrowse se logró ver los genes, IS, plásmidos, etc. en los contigs, como se observa en la figura 32.

![visualización_genoma_JBrowse](imagenes/32.jpg)

## CONCLUSIONES
+ Mediante la plataforma virtual Galaxy, empleando la herramienta FastQC se evaluó la calidad de la secuencia de *Staphylococcus aureus*, determinándose que los parámetros analizados cumplen con los estándares.

+ Se realizó la anotación del genoma bacteriano de la secuencia de *Staphylococcus aureus* resistente a la meticilina, mediante la herramienta Bakta en la cual se logró encontrar la posición de los contings, además, se logró visualizar la posición del porcentaje de GC que poseía la secuencia. 
+ Se empleó el uso de  otras herramientas como plasmidFinder e IntegronFinder con el fin de econtrar plasmidos e integrones que normalmente en la anotación del genoma no suelen aparecer.


## REFERENCIAS
+ García, A., Martínez, C., Juárez, R. I., Téllez, R., Paredes, M. A., Herrera, M. D. R., & Giono, S. (2019). Methicillin resistance and biofilm production in clinical isolates of Staphylococcus aureus and coagulase-negative Staphylococcus in México. Resistencia a la meticilina y producción de biopelícula en aislamientos clínicos de Staphylococcus aureus y Staphylococcus coagulasa negativa en México. Biomedica : revista del Instituto Nacional de Salud, 39(3), 513–523. https://doi.org/10.7705/biomedica.4131
  
+ Néron, B., E. Littner, M. Haudiquet, A. Perrin, J. Cury et al., 2022 IntegronFinder 2.0: identification and analysis of integrons across bacteria, with a focus on antibiotic resistance in Klebsiella. Microorganisms 10: 700. 10.3390/microorganisms10040700
  
+ Grupo de Trabajo EPINE. Prevalencia de las infecciones nosocomiales en los hospitales españoles EPINE 1990-1994.
Barcelona: Vaqué Rafart J. (ed.), 1995.

+ Gagliotti C, Högberg LD, Billström H, Eckmanns T, Giske CG, Heuer OE, et al. Infecciones del torrente sanguíneo por Staphylococcus aureus: tendencias divergentes de aislados resistentes y susceptibles a la meticilina, UE/EEE, 2005 a 2018. Eur Secur. 2021 18 de noviembre ; 26 ( 46 ): 2002094. doi: 10.2807/1560-7917.ES.2021.26.46.2002094
+ Waterlow NR, Cooper BS, Robotham JV, Knight GM. Antimicrobial resistance prevalence in bloodstream infection in 29 European countries by age and sex: An observational study. PLoS Med. 2024 Mar 14;21(3):e1004301. doi: 10.1371/journal.pmed.1004301. PMID: 38484006; PMCID: PMC10939247
+ Xie, Z., and H. Tang, 2017 ISEScan: automated identification of insertion sequence elements in prokaryotic genomes. Bioinformatics 33: 3340–3347. 10.1093/bioinformatics/btx433
  
