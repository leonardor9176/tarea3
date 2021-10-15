# Tarea 3

Solución tarea 3 Bootcamp Full Stack BICTIA

Se presenta la solución a la tarea 3, ofreciendo una alternativa al caso planteado de un colegio interesado en obtener una herramienta para tealizar distintos cálculos.
La información es manipulada desde un archivo .json.

## Funciones Principales

Las funciones utilizadas para realizar las peticiones establecidas son:

### __countStudents(*jsonObject*, *levelWanted*, *genderWanted*)__
La función retorna el total de estudiantes que contiene el parámetro *jsonObject* que cumplen con los criterios establecidos en los parámetros *levelWanted* y *genderWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el conteo. Los valores válidos para este parámetro son: 

  - *'colegio'*: realiza el conteo de todos los estudiantes.

  - *'primaria'* o *'secundaria'*: realiza el conteo de los estudiantes de primaria o secundaria.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: realiza el conteo de los estudiantes del grado establecido en el parámetro.

- __*genderWanted*__: string que establece el género con el que se desea realizar el conteo. Este parámetro es opcional, si la funcion no lo recibe, realiza el conteo incluyendo ambos géneros. Los valores válidos para este parámetro son:

  - *'niños'*: realiza el conteo de los de género masculino (male) en el nivel establecido por el parámetro __*levelWanted*__.

  - *'niñas'*: realiza el conteo de los de género femenino (female) en el nivel establecido por el parámetro __*levelWanted*__.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*genderWanted*__ es de tipo *undefined*, es equivalente a no recibireste parámetro y realiza la cuenta de ambos generos.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__Ejemplos:__

__countStudents(*schoolJson*)__: Retorna el total de estudiantes que hay en el colegio.

__countStudents(*schoolJson*, *'colegio'*)__: Retorna el total de estudiantes que hay en el colegio.

__countStudents(*schoolJson*, *'colegio'*, *'niños'*)__: Retorna el total de niños que hay en el colegio.

__countStudents(*schoolJson*, *'primaria'*)__: Retorna el total de estudiantes que hay en primaria.

__countStudents(*schoolJson*, *'primaria'*, *'niñas'*)__: Retorna el total de niñas que hay en primaria.

__countStudents(*schoolJson*, *'secundaria'*)__: Retorna el total de estudiantes que hay en secundaria.

__countStudents(*schoolJson*, *'secundaria'*, *'niñas'*)__: Retorna el total de niñas que hay en secundaria.

### __getMean(*jsonObject*, *levelWanted*)__
La función retorna la nota promedio de los estudiantes del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el cálculo. Los valores válidos para este parámetro son: 

  - *'colegio'*: retorna la nota promedio de todos los estudiantes.

  - *'primaria'* o *'secundaria'*: retorna la nota promedio de los estudiantes de primaria o secundaria.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: retorna la nota promedio de los estudiantes del grado establecido en el parámetro.

  - *'A'* o *'B'*: retorna la nota promedio de los estudiantes de los cursos A o B.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__*Nota:* esta funcion utiliza la función intermedia *getScores* que retorna un arreglo con todas las notas del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*__.

__Ejemplos:__

__getMean(*schoolJson*)__: Retorna la nota promedio de todos los estudiantes que hay en el colegio.

__getMean(*schoolJson*, *'colegio'*)__: Retorna la nota promedio de todos los estudiantes que hay en el colegio.

__getMean(*schoolJson*, *'primaria'*)__: Retorna la nota promedio de todos los estudiantes que hay en primaria.

__getMean(*schoolJson*, *'sexto'*)__: Retorna la nota promedio de todos los estudiantes que hay en el grado sexto (incluye curso A y curso B).

__getMean(*schoolJson*, *'A'*)__: Retorna la nota promedio de todos los estudiantes que hay en todos los cursos A de todos los grados.

### __getMode(*jsonObject*, *levelWanted*)__
La función retorna la moda de las notas (la nota más comun) de los estudiantes del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el cálculo. Los valores válidos para este parámetro son: 

  - *'colegio'*: retorna la moda de las notas de todos los estudiantes.

  - *'primaria'* o *'secundaria'*: retorna la moda de las notas de los estudiantes de primaria o secundaria.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: retorna la moda de las notas de los estudiantes del grado establecido en el parámetro.

  - *'A'* o *'B'*: retorna la moda de las notas de los estudiantes de los cursos A o B.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__*Nota:* esta funcion utiliza la función intermedia *getScores* que retorna un arreglo con todas las notas del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*__.

__Ejemplos:__

__getMode(*schoolJson*)__: Retorna la moda de las notas de todos los estudiantes que hay en el colegio.

__getMode(*schoolJson*, *'colegio'*)__: Retorna la moda de las notas de todos los estudiantes que hay en el colegio.

__getMode(*schoolJson*, *'primaria'*)__: Retorna la moda de las notas de todos los estudiantes que hay en primaria.

__getMode(*schoolJson*, *'sexto'*)__: Retorna la moda de las notas de todos los estudiantes que hay en el grado sexto (incluye curso A y curso B).

__getMode(*schoolJson*, *'A'*)__: Retorna la moda de las notas de todos los estudiantes que hay en todos los cursos A de todos los grados.

### __getMedian(*jsonObject*, *levelWanted*)__
La función retorna la media de las notas de los estudiantes del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el cálculo. Los valores válidos para este parámetro son: 

  - *'colegio'*: retorna la media de las notas de todos los estudiantes.

  - *'primaria'* o *'secundaria'*: retorna la media de las notas de los estudiantes de primaria o secundaria.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: retorna la media de las notas de los estudiantes del grado establecido en el parámetro.

  - *'A'* o *'B'*: retorna la media de las notas de los estudiantes de los cursos A o B.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__*Nota:* esta funcion utiliza la función intermedia *getScores* que retorna un arreglo con todas las notas del parámetro *jsonObject* que cumplen con los criterios establecidos en el parámetro *levelWanted*__.

__Ejemplos:__

__getMedian(*schoolJson*)__: Retorna la media de las notas de todos los estudiantes que hay en el colegio.

__getMedian(*schoolJson*, *'colegio'*)__: Retorna la media de las notas de todos los estudiantes que hay en el colegio.

__getMedian(*schoolJson*, *'primaria'*)__: Retorna la media de las notas de todos los estudiantes que hay en primaria.

__getMedian(*schoolJson*, *'sexto'*)__: Retorna la media de las notas de todos los estudiantes que hay en el grado sexto (incluye curso A y curso B).

__getMedian(*schoolJson*, *'A'*)__: Retorna la media de las notas de todos los estudiantes que hay en todos los cursos A de todos los grados.

### __getHigherScoresBySubject(*jsonObject*, *levelWanted*)__
La función retorna un objeto con los datos (nombre, grado, curso y nota promedio de la materia) de los estudiantes del parámetro *jsonObject* que obtuvieron la mayor nota promedio en cada materia, que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el filtro. Los valores válidos para este parámetro son: 

  - *'colegio'*: calcula la nota promedio que obtuvo cada estudiante del colegio en cada materia y retorna un dato de tipo objetola con los datos de los estudiantes con mejor nota promedio en cada materia.

  - *'primaria'* o *'secundaria'*: calcula la nota promedio que obtuvo cada estudiante de primaria o secundaria en cada materia y retorna un dato de tipo objetola con los datos de los estudiantes con mejor nota promedio en cada materia.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: calcula la nota promedio que obtuvo cada estudiante del grado establecido (incluye cursos A y B) en cada materia y retorna un dato de tipo objetola con los datos de los estudiantes con mejor nota promedio en cada materia.

  - *'A'* o *'B'*: calcula la nota promedio que obtuvo cada estudiante del colegio en cada grado del curso A o curso B, en cada materia y retorna un dato de tipo objetola con los datos de los estudiantes con mejor nota promedio en cada materia..

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__*Nota:* esta funcion utiliza la función intermedia *compareHigherScores* que que compara la nota promedio obtenida por un estudiante en una materia, con la nota máxima registrada hasta el momento para esa materia.

__Ejemplos:__

__getHigherScoresBySubject(*schoolJson*)__: Retorna el objeto con los estudiantes de todo el colegio con la mejor nota promedio en cada materia.

__getHigherScoresBySubject(*schoolJson*, *'colegio'*)__: Retorna el objeto con los estudiantes de todo el colegio con la mejor nota promedio en cada materia.

__getHigherScoresBySubject(*schoolJson*, *'primaria'*)__: Retorna el objeto con los estudiantes de primaria con la mejor nota promedio en cada materia.

__getHigherScoresBySubject(*schoolJson*, *'sexto'*)__: Retorna el objeto con los estudiantes de grado sexto (considerando cursos A y B) con la mejor nota promedio en cada materia.

__getHigherScoresBySubject(*schoolJson*, *'A'*)__: Retorna el objeto con los estudiantes de todo el colegio que pertenecen a todos los grados de los cursos A, con la mejor nota promedio en cada materia.

### __getStudentHigherAvgScore(*jsonObject*, *levelWanted*)__
La función retorna un objeto con los datos (nombre, grado, curso y nota promedio de todas las materias) de los estudiantes del parámetro *jsonObject* la mayor nota promedio en todas las materia, que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el filtro. Los valores válidos para este parámetro son: 

  - *'colegio'*: calcula la nota promedio de todas las materias que obtuvo cada estudiante del colegio y retorna un dato de tipo objeto con los datos del estudiante con mejor nota promedio en todas las materias.

  - *'primaria'* o *'secundaria'*: calcula la nota promedio de todas las materias que obtuvo cada estudiante de primaria o secundaria y retorna un dato de tipo objeto con los datos del estudiante con mejor nota promedio en todas las materias.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: calcula la nota promedio de todas las materias que obtuvo cada estudiante del grado establecido (incluye cursos A y B) y retorna un dato de tipo objeto con los datos del estudiante con mejor nota promedio en todas las materias.

  - *'A'* o *'B'*: calcula la nota promedio de todas las materias que obtuvo cada estudiante del colegio en cada grado del curso A o curso B, y retorna un dato de tipo objeto con los datos del estudiante con mejor nota promedio en todas las materias.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un avlor de tipo *undefined*.

__*Nota:* esta funcion utiliza la función intermedia *compareAvgScore* que compara la nota promedio de todas las materias obtenida por un estudiante, con la nota máxima registrada hasta el momento.

__Ejemplos:__

__getStudentHigherAvgScore(*schoolJson*)__: Retorna el objeto con los datos del estudiante con la mejor nota promedio de todo el colegio.

__getStudentHigherAvgScore(*schoolJson*, *'colegio'*)__: Retorna el objeto con los datos del estudiante con la mejor nota promedio de todo el colegio.

__getStudentHigherAvgScore(*schoolJson*, *'primaria'*)__: Retorna el objeto con los datos del estudiante con la mejor nota promedio en primaria.

__getStudentHigherAvgScore(*schoolJson*, *'sexto'*)__: Retorna el objeto con los datos del estudiante con la mejor nota promedio en grado sexto (considerando cursos A y B).

__getHigherScoresBySubject(*schoolJson*, *'A'*)__: Retorna el objeto con los datos del estudiante con la mejor nota promedio en todos los todos los grados de los cursos A.

### getStudentOfGrade(*jsonObject*, *gradeWanted*)__
La función retorna un objeto con los datos (nombre, genero, grado, curso y nivel) de uno de los estudiantes del parámetro *jsonObject*, selexionado aleatoriamente que pertenece al grado *gradeWanted*, considerando curso A y curso B; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*gradeWanted*__: __PARAMETRO OBLIGATORIO__ string que establece el grado en el que se desea realizar el filtro. Los valores válidos para este parámetro son: 

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: retorna un estudiante selecionado de matera aleatoria que pertenece al curso dado en el parámetro.

__*Nota:*__ cuando el parámetro __*gradeWanted*__ es de tipo *undefined*, la funcion retorna un valor de tipo *undefined*.

__*Nota:*__ cuando el parámetro __*gradeWanted*__ no se reconoce, la funcion retorna un valor de tipo *undefined*.

__Ejemplos:__

__getStudentHigherAvgScore(*schoolJson*, *'sexto'*)__: Retorna el objeto con los datos de un estudiante selexionado aleatoriamente que pertenece a grado sexto (considerando cursos A y B).

## Funciones Intermedias:

algunas de las funciones principales descritas anteriormente hacen uso de otras funciones para otener los resultados, estas ultimas, en este proyecto se han denominado funciones intermedias y son:

### __getScores(*jsonObject*, *levelWanted*)__
La función es utilizada en las funciones *getMean*, *getMode* y *getMedian*. Retorna un arreglo con todas las notas de los estudiantes del parámetro *jsonObject* organizadas ascendentemente, que cumplen con los criterios establecidos en el parámetro *levelWanted*; donde:

- __*jsonObject*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información de todos los estudiantes del colegio.

- __*levelWanted*__: string que establece el nivel en el que se desea realizar el filtrado. Los valores válidos para este parámetro son: 

  - *'colegio'*: retorna un arreglo con todas las notas de todos los estudiantes.

  - *'primaria'* o *'secundaria'*: retorna un arreglo con todas las notas de los estudiantes de primaria o secundaria.

  - *'primero'*, *'segundo'*, *'tercero'*, *'cuarto'*, *'quinto'*, *'sexto'*, *'septimo'*, *'octavo'*, *'noveno'*, *'decimo'* u *'once'*: retorna un arreglo con todas las notas de los estudiantes del grado establecido en el parámetro.

  - *'A'* o *'B'*: retorna un arreglo con todas las notas de los estudiantes de los cursos A o B.

__*Nota:*__ cuando la función no recibe ningún parámetro, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando el parámetro __*levelWanted*__ es de tipo *undefined*, es equivalente a recibir __*levelWanted*__ con el valor *'colegio'*.

__*Nota:*__ cuando alguno de los parámetros pasados a la funcion no se reconoce, la función tetorna un valor de tipo *undefined*.

__Ejemplos:__

__getScores(*schoolJson*)__: retorna un arreglo con todas las notas de todos los estudiantes.

__getScores(*schoolJson*, *'colegio'*)__: retorna un arreglo con todas las notas de todos los estudiantes.

__getScores(*schoolJson*, *'primaria'*)__: retorna un arreglo con todas las notas de todos los estudiantesde primaria.

__getScores(*schoolJson*, *'sexto'*)__: retorna un arreglo con todas las notas de todos los estudiantes de grado sexto (considerando cursos A y B).

__getScores(*schoolJson*, *'A'*)__: retorna un arreglo con todas las notas de todos los estudiantes de todos los todos los grados de los cursos A.

### __compareHigherScores(*objectSource*, *studentData*, *subjectToCheck*)__
La función es utilizada en la funcion *getHigherScoresBySubject*. Compara la nota almacena en el parámetro *objectSource* de tipo objeto para la materia del parámetro *subjectToCheck* de tipo string, con la nota de un estudiante almacenada en el parámetro *studentData* de tipo objeto y retorna un dato de tipo objeto con los datos (nombre, grado, curso y nota) de los estudiantes con notas más altas en cada materia; donde:

- __*objectSource*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con los datos de los estudiantes con las notas más altas en cada materia.

- __*studentData*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con los datos del estudiante que se desea comparar con el registro de estuantes con nota más alta almacenado en *objectSource*.

- __*subjectToCheck*__: __PARAMETRO OBLIGATORIO__ string con el nombre de la materia en la que se va a comparar la nota del estudiante pasado en el parámetro *studentData*.

__*Nota:*__ como la función *getHigherScoresBySubject* pasa los parámetros a esta función, se espera que los parámetros tengan estructura y valores válidos.

__Ejemplos:__

__compareHigherScores(*higherScores*, *studentInformation*, *'matemáticas'*)__: compara la nota máxima registrada hasta el momento para la materia *'matemáticas'* en el objeto *higherScores* con la nota de *'matemáticas'* obtenida por el estudiante del objeto *studentInformation* y retorna un objeto con los datos de los estudiantes con nota más alta en cada materia.

### __compareAvgScore(*objectSource*, *studentData*)__
La función es utilizada en la funcion *getStudentHigherAvgScore*. Compara la nota almacena en el parámetro *objectSource* de tipo objeto, con la nota de un estudiante almacenada en el parámetro *studentData* de tipo objeto y retorna un dato de tipo objeto con los datos (nombre, grado, curso y nota) del estudiantes con notas más altas; donde:

- __*objectSource*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con los datos del estudiante con la nota más alta.

- __*studentData*__: __PARAMETRO OBLIGATORIO__ objeto tipo json con la información del estudiante que se desea comparar con estudiante con la nota más alta almacenado en *objectSource*.

__*Nota:*__ como la función *getStudentHigherAvgScore* pasa los parámetros a esta función, se espera que los parámetros tengan estructura y valores válidos.

__Ejemplos:__

__compareAvgScore(*higherScores*, *studentInformation*)__: compara la nota máxima registrada hasta el momento en el objeto *higherScores* con la nota obtenida por el estudiante del objeto *studentInformation* y retorna los datos del estudiante con nota más alta.
