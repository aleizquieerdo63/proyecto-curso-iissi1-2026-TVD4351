# Clínica Veterinaria

## Miembros del grupo L6-DF-3

1. Torres Muñoz, Jose Antonio
2. Martínez Cintas, Pilar
3. Palma Pastrana, Virginia
4. Izquierdo Burguillos, Alejandro

---

## Índice

1. Introducción al problema
2. Glosario de términos
3. Visión general del sistema
   
   3.1. Requisitos generales (Objetivos)
   
   3.2. Usuarios del sistema (Roles)
4. Catálogo de requisitos
   
   4.1. Requisitos de información
   
   4.2. Reglas de negocio
   
   4.3. Requisitos funcionales (sólo listados y consultas)
 
   4.4. Pruebas de aceptación de reglas de negocio
5. Modelo conceptual

   5.1. Diagramas de clases UML con restricciones

   5.2. Escenarios de prueba con descripción textual y diagrama de objetos UML
6. Matrices de trazabilidad: Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos de información y reglas de negocio.
---

## 1. Introducción al problema

Nuestra propuesta se centra en la "Clínica Veterinaria Joviralpi". Durante el último año, la clínica ha experimentado un crecimiento, aumentando sus clientes en un 150% y ampliando su plantilla de dos a cinco veterinarios, además de incorporar personal de recepción.

Actualmente, el sistema de información de la clínica opera de manera tradicional, dependiendo casi en su totalidad del papel. La gestión se realiza mediante un sistema de archivos físicos y fichas impresas para cada paciente. Las citas se anotan en una agenda de sobremesa.

Este crecimiento repentino ha desbordado la capacidad operativa del sistema actual, generando una serie de problemas que afectan tanto a la eficiencia interna como a la calidad del servicio ofrecido a los clientes.

La gestión en papel y los procesos manuales están causando problemas serios en el día a día de la clínica. Perder tiempo buscando fichas guardadas o no entender la letra de otros compañeros retrasa las consultas, y siempre existe el riesgo de que los papeles se estropeen o se pierdan para siempre. Además, como solo una persona puede tener la carpeta en la mano, en recepción y en las salas se forman atascos constantes. A esto se le suma tener que llamar manualmente a las personas para recordarles su cita porque no podemos mandar avisos automáticos.


El objetivo principal del proyecto es diseñar un sistema digital centralizado que reemplace el papel en la clínica Joviralpi mediante una base de datos única y accesible para todo el personal. Con esta solución se busca proteger la información clínica evitando pérdidas o errores, agilizar la operativa diaria al eliminar la búsqueda manual de fichas, y mejorar la experiencia del cliente reduciendo los tiempos de espera y facilitando los recordatorios de citas.

En conclusión, queremos digitalizar nuestra clínica para que haya una evolución y mejora del funcionamiento y servicio que ofrecemos a los clientes.

---

## 2. Glosario de términos

- Cartilla sanitaria: Es el documento básico de salud preventiva del animal. Un librito físico donde se anotan y sellan las vacunas y desparasitaciones administradas.
- Desparasitación: Tratamiento preventivo o curativo consistente en la administración de fármacos antiparasitarios a un paciente.
- Diagnóstico: Juicio emitido formalmente por el veterinario tras el examen del paciente durante una consulta.
- Especie: Clasificación biológica a la que pertenece el paciente (canina, felina, etc.).
- Raza: División dentro de cada especie.
- Microchip: pequeño dispositivo electrónico que se implanta bajo la piel de las mascotas para su identificación permanente y legal.

---

## 3. Visión general del sistema

### 3.1. Requisitos generales (Objetivos)

Nuestros propósitos principales para el sistema de la clínica, codificados y expresados formalmente como historias épicas, son los siguientes:

RG-01: Gestión de clientes  

*Como* recepcionista
*Quiero* saber los dueños de las mascotas,
*Para* realizar los trámites como la disponibilidad de consultas y la confirmación de estas

RG-02: Gestión de mascotas:

*Como* veterinario,
*Quiero* gestionar los datos sobre las mascotas
*Para* consultar su historial clínico y llevar un seguimiento

RG-03: Gestión de citas

*Como* recepcionista
*Quiero* gestionar las citas de la clínica de forma centralizada,
*Para* organizar mejor el tiempo de los veterinarios, evitar que dos clientes vengan a la misma hora y reducir las esperas.

RG-04: Gestión de usuarios 

*Como* director de la clínica
*Quiero* gestionar los datos y accesos de los empleados en el sistema,
*Para* controlar la plantilla activa, garantizar la seguridad de la información clínica y permitir la asignación de turnos y citas a los veterinarios disponibles.

### 3.2. Usuarios del sistema (Roles)

De acuerdo con los objetivos definidos, tendremos tres roles con permisos diferenciados:

Veterinario:
Su trabajo se centra en el apartado médico (Gestión de pacientes e historiales). Puede buscar pacientes, añadir entradas al historial clínico tras una consulta (diagnósticos, observaciones), registrar las vacunas administradas y consultar la agenda del día para ver sus citas asignadas.

Recepcionista:
Es el encargado principal del apartado de citas (Gestión de agenda). Da de alta en el sistema a los nuevos clientes (humanos) y a sus pacientes (mascotas). Crea, modifica o cancela las citas en la agenda general, asignándolas a los diferentes veterinarios según disponibilidad.

Director (Administrador):
Es el gerente de la clínica y tiene permisos totales. Además de poder hacer todo lo que hacen los recepcionistas y veterinarios, es el encargado de dar de alta a los empleados en el programa.

---

## 4. Catálogo de requisitos

### 4.1. Requisitos de información CAMBIAR

RI-01: Información de Clientes.

*Como* administrador del sistema,
*Quiero* almacenar la siguiente información de Clientes: DNI/NIF, nombre y apellidos, teléfono, correo electrónico, dirección postal

Un cliente puede tratar en la clínica varias Mascotas, con un máximo de 5.

RI-02: Información de Mascotas.

*Como* administrador del sistema,
*Quiero* almacenar la siguiente información de Mascotas: número de microchip, nombre, especie, raza, sexo(hembra, macho), fecha de nacimiento.

Una mascota tiene un dueño

Cada mascota podrá visitar a numerosos veterinarios, y un veterinario podrá atender a múltiples mascotas.

RI-03: Información de Citas

*Como* administrador del sistema,
*Quiero* almacenar la siguiente información de las citas: fecha y hora programada, cliente, mascota, veterinario asignado, motivo o tipo de cita (consulta general, revisión o urgencia), estado actual de la cita (pendiente, confirmada, atendida o cancelada), observaciones o notas previas (opcional), coste.

HAY QUE RELACIONAR LAS CITAS CON ALGO :PENDIENTE

RI-04: Información de Usuarios:

*Como* administrador del sistema,
*Quiero* almacenar la siguiente información de los Usuarios: DNI/NIF, nombre, apellidos, teléfono, correo electrónico, rol (veterinario, recepcionista), estado de acceso (activo, inactivo), horarios de trabajo

El director supervisa a los recepcionistas y a los veterinarios

### 4.2. Reglas de negocio

Las reglas de negocio definen las políticas, restricciones y condiciones que rigen el funcionamiento de la clínica Joviralpi y que el sistema debe hacer cumplir obligatoriamente para garantizar la integridad y coherencia de los datos:

RN-01: Solapamiento de citas de un mismo veterinario

Como recepcionista, quiero que el sistema impida asignar a un mismo veterinario dos citas que coincidan en el mismo tramo de fecha y hora, para evitar duplicidades de agenda, retrasos en la atención y saturación de los gabinetes de consulta.

RN-02: Asignación de citas exclusivamente a veterinarios en activo y en horario de apertura

Como director de la clínica, quiero que solo se puedan reservar citas en tramos horarios comprendidos dentro del horario comercial de la clínica y asignadas a empleados registrados con el rol de veterinario que figuren en estado activo, para garantizar el cumplimiento de los turnos laborales y asegurar que todo paciente citado sea atendido por personal cualificado disponible.

RN-03: Máximo registrados

Como recepcionista, quiero asegurarme de que un cliente no puede tener a más de 5 mascotas registradas en la clínica

RN-04: Tiempo de anulación de citas

Como recepcionista, necesito comunicarme con el cliente como míninmo 48 horas antes para saber si la cita esta confirmada o anulada. No se puede anular una cita con poca antelación

RN-05: Asignación de citas conservando pagos

Como recepcionista, quiero tener un control de los pagos, asegurando de que no se dé una cita nueva a un cliente que no haya pagado la anterior

RN-06: Tiempo máximo de pago

Como director, llevo una lista de los pagos diarios y voy confirmando que todos se pagen antes de las dos semanas siguientes a la cita

### 4.3. Requisitos funcionales: listados y consultas (RF) "(4 por cada requisito general, listado)"

RF-01.1: Listado de clientes

*Como* recepcionista,
*Quiero* ver un listado en el que pueda buscar los clientes registrados en la clínica
*Para* consultar sus datos y localizar rápidamente a los dueños de las mascotas al gestionar la disponibilidad y confirmación de sus consultas

RF-01.2: Creación de clientes

*Como* recepcionista,
*Quiero* registrar todos los datos necesarios de un nuevo dueño de mascota en el sistema
*Para* darlos de alta en la base de datos de la clínica y después permitir asignarles citas

RF-01.3: Edición de clientes

*Como* recepcionista,
*Quiero* modificar los datos de un cliente ya registrado
*Para* mantener actualizada su información de contacto (teléfono, correo o dirección) ante posibles avisos o confirmaciones de consulta

RF-01.4: Borrado de clientes

*Como* recepcionista,
*Quiero* dar de baja a un cliente en el sistema
*Para* deshabilitar su ficha e impedir que se le sigan asignando trámites o consultas si ya no acude a la clínica

RF-02.1: Listado de mascotas

*Como* administrador del sistema,
*Quiero* consultar un listado de todas las mascotas registradas junto con su dueño responsable
*Para* localizar su historial clínico rápidamente según su número de microchip o nombre 

RF-02.2: Creación de mascotas

*Como* administrador del sistema,
*Quiero* registrar los datos de una mascota vinculandola a su dueño
*Para* incorporar la información al sistema y permitir sus futuras citas

RF-02.3: Edición de mascotas

*Como* administrador del sistema,
*Quiero* actualizar la información registrada de una mascota
*Para* mantener la ficha correctamente actualizada en la base de datos

RF-02.4: Borrado de mascotas

*Como* administrador del sistema,
*Quiero* dar de baja la ficha de una mascota
*Para* inactivar su registro en caso de fallecimiento o cambio de centro veterinario, evitando que se le asignen nuevas citas

RF-03.1: Listado de citas

*Como* recepcionista,
*Quiero* visualizar un calendario de todas las citas programadas en la clínica
*Para* consultar la disponibilidad y los horarios de los veterinarios y organizar mejor las consultas diarias

RF-03.2: Creación de citas

*Como* recepcionista,
*Quiero* registrar una nueva cita asociando una fecha y hora, un cliente, una mascota y un veterinario
*Para* asignar el turno correspondiente y evitar que dos clientes coincidan a la misma hora

RF-03.3: Edición de citas

*Como* recepcionista,
*Quiero* modificar los datos de una cita existente (fecha, hora, movito o veterinario asignado)
*Para* actualizar los detalles de la visita según las necesidades del cliente

RF-03.4: Borrado de citas

*Como* recepcionista,
*Quiero* cancelar o eliminar una cita programada en el sistema
*Para* liberar el hueco en el horario del veterinario, evitar confusiones y poder reasignar ese horario a otra mascota

RF-04.1: Listado de usuarios

*Como* director,
*Quiero* visualizar un listado de todos los empleados registrados en el sistema
*Para* consultar la plantilla activa, revisar sus roles y comprobar su disponibilidad

RF-04.2: Creación de usuarios

*Como* director,
*Quiero* registrar un nuevo empleado asignandole sus datos personales y credenciales de acceso
*Para* darle de alta en el sistema y permitir operar según las responsabilidades de su puesto

RF-04.3: Edición de usuarios

*Como* director,
*Quiero* actualizar la información de un empleado
*Para* mantener al día los datos del personal y ajustar sus permisos en el sistema

RF-04.4: Borrado de usuarios

*Como* director,
*Quiero* dar de baja o inactivar la cuenta de un empleado
*Para* denegar inmediatamente sus accesos garantizando la seguridad de la información clínica cuando deje de formar parte de la plantilla

### 4.4. Pruebas de aceptación de reglas de negocio

Para cada regla de negocio se definen pruebas de aceptación que describen escenarios válidos (positivos) y escenarios donde se intenta incumplir la regla (negativos):

Pruebas para RN-01 (No al solapamiento de citas de un mismo veterinario):
- Caso positivo: Registrar una cita para un veterinario en una fecha y hora donde no tiene ninguna otra cita asignada. El resultado esperado es correcto y la cita queda guardada.
- Caso negativo: Intentar registrar una segunda cita para el mismo veterinario en la misma fecha y hora. El resultado esperado es un error controlado por solapamiento de citas en la agenda.

Pruebas para RN-02 (Asignación de citas exclusivamente a veterinarios en activo y en horario de apertura):
- Caso positivo: Asignar una cita dentro del horario comercial a un empleado con rol de veterinario que figure en estado activo. El resultado esperado es correcto.
- Caso negativo: Intentar asignar una cita a un veterinario que se encuentra en estado de baja. El resultado esperado es un error controlado indicando que el veterinario no está disponible.
- Caso negativo: Intentar asignar una cita a un empleado registrado con el rol de recepcionista. El resultado esperado es un error controlado indicando que no es personal veterinario.
- Caso negativo: Intentar registrar una cita fuera del horario comercial de apertura de la clínica. El resultado esperado es un error controlado por horario no disponible.

Pruebas para RN-03 (Unicidad de identificadores oficiales):
- Caso positivo: Dar de alta a un paciente con un número de microchip que no existe en el sistema. El resultado esperado es correcto y el paciente queda registrado.
- Caso negativo: Intentar registrar un paciente con un número de microchip que ya pertenece a otro paciente registrado. El resultado esperado es un error controlado por microchip duplicado.


Pruebas para RN-04 (Fecha y hora de cita posterior al momento del registro):
- Caso positivo: Agendar una cita para una fecha y hora posterior al momento actual del registro. El resultado esperado es correcto.
- Caso negativo: Intentar registrar una cita con una fecha u hora anterior al momento del registro en el sistema. El resultado esperado es un error controlado indicando que la cita debe ser futura.

Pruebas para RN-05 (Obligatoriedad de colegiación para la firma de consultas y recetas):
- Caso positivo: Registrar una consulta médica asignando como responsable a un usuario con rol de veterinario. El resultado esperado es correcto.
- Caso negativo: Intentar registrar una consulta médica indicando a un usuario sin rol de veterinario. El resultado esperado es un error controlado impidiendo la firma de la consulta.

## 5. Modelado Conceptual

### 5.1. Diagrama de clases UML con restricciones

![Diagrama de clases](img\diagramaclases.jpeg)

### 5.2. Escenarios de pruebas con diagrama de clases UML

#### 5.2.1 Prueba RN-01

![RN-01 Prueba](img\rn1_prueba.jpeg)

El veterinario Carlos Gómez (con DNI 87654321B) ya tiene asignada y confirmada una citaExistente de tipo CONSULTA_GENERAL para el día 2026-11-15 10:00:00. Posteriormente, la recepcionista intenta registrar una citaNuevaIntentada (de tipo REVISION) para el mismo veterinario y exactamente en el mismo tramo horario (2026-11-15 10:00:00), infringiendo la regla de negocio RN-01 (No solapamiento de citas de un mismo veterinario).El sistema detecta el conflicto de horario en la agenda del veterinario, muestra un error controlado y bloquea el almacenamiento de la nueva cita para evitar duplicidades y saturaciones en los gabinetes.

#### 5.2.2 Prueba RN-02

![RN-02 Prueba](img\rn2_prueba.jpeg)

El cliente Juan Pérez (con DNI 12345678A) posee una mascota llamada "Luna" (especie canina, microchip 985142000123456). La recepcionista Ana López crea y gestiona una cita de tipo CONSULTA_GENERAL para el día 2026-11-15 10:00:00 con estado PENDIENTE. Dicha cita es asignada para ser atendida por el Dr. Carlos Gómez, quien se encuentra registrado con el rol de Veterinario y con estado_acceso en Activo, cumpliendo con la regla RN-02. El sistema valida correctamente los datos, comprueba que el veterinario está activo y guarda la cita en la agenda sin incidencias.

#### 5.2.3 Prueba RN-03

![RN-03 Prueba](img\rn3_prueba.jpeg)

La clienta María Ruiz (con DNI 55443322C) posee actualmente un total de 5 mascotas registradas en el sistema (m1, m2, m3, m4 y m5), alcanzando el límite máximo permitido estipulado por la regla de negocio RN-03 (un cliente no puede tener a más de 5 mascotas registradas en la clínica). Si el recepcionista intentara registrar una sexta mascota asociada a este mismo cliente, el sistema bloqueará la operación. El sistema valida correctamente la cardinalidad máxima, advierte que se ha alcanzado el tope de 5 animales y deniega el alta de una nueva mascota para salvaguardar la restricción de negocio

#### 5.2.4 Prueba RN-04

![RN-04 Prueba](img\rn4_prueba.jpeg)

La regla de negocio RN-04 establece que la clínica debe comunicarse con el cliente con un mínimo de 48 horas de antelación para confirmar o anular las citas, prohibiendo expresamente las anulaciones fuera de plazo. En este escenario, la recepcionista Ana López intenta gestionar la anulación de la citaProgramada (programada para el 2026-11-15 09:00:00), pero el margen de tiempo disponible es inferior al mínimo requerido de 48 horas.El sistema detecta el incumplimiento del margen temporal establecido, bloquea el cambio de estado y deniega la anulación de la cita para proteger la planificación de la clínica.

#### 5.2.5 Prueba RN-05

![RN-05 Prueba](img\rn5_prueba.jpeg)

La regla de negocio RN-05 especifica que el sistema debe mantener un control de los pagos, asegurando que no se pueda asignar una cita nueva a un cliente que tenga pendiente el abono de una cita anterior. En este escenario, el cliente Pedro Picapiedra (clienteDeudor) intenta programar una citaNuevaBloqueada, pero el sistema comprueba que mantiene registrada una citaAnteriorPendiente (atendida pero no abonada).El sistema detecta la deuda pendiente asociada al cliente, emite un aviso de incumplimiento de la regla RN-05 y bloquea la asignación y guardado de la nueva cita en la agenda

#### 5.2.6 Prueba RN-06

![RN-06 Prueba](img\rn6_prueba.jpeg)

La regla de negocio RN-06 establece que el director debe supervisar los pagos diarios, asegurando que todas las citas atendidas sean abonadas en un plazo máximo de dos semanas desde su fecha de realización. En este escenario de supervisión, el director Roberto Sánchez (director1) revisa el historial del cliente Pedro Picapiedra (clienteDeudor) y detecta una citaAntiguaSinPagar (con estado ATENDIDA) cuyo tiempo transcurrido supera ampliamente el límite permitido de dos semanas sin haberse liquidado.El sistema, bajo la supervisión del director, identifica el retraso excesivo, genera una alerta por incumplimiento de la regla RN-06 y registra la incidencia para proceder a la reclamación del importe pendiente.

