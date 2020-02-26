Microsoft Defending Democracy Program: ElectionGuard](images/electionguard-banner.svg)

# 🗳 ElectionGuard

[![licencia](https://img.shields.io/github/license/microsoft/electionguard)](Licencia)

ElectionGuard es un kit de desarrollo de software de código abierto (SDK) que hace que la votación sea más segura, transparente y accesible. El SDK de ElectionGuard aprovecha [la encriptación homomórfica](https://es.wikipedia.org/wiki/Cifrado_homomórfico) para asegurar que los votos registrados por sistemas electrónicos de cualquier tipo permanezcan encriptados, seguros y secretos. Mientras tanto, ElectionGuard también permite el recuento verificable y preciso de los votos por cualquier organización de terceros sin comprometer el secreto o la seguridad. 

Anunciado el 6 de mayo en la conferencia de desarrolladores del edificio, ElectionGuard permitirá la verificación de extremo a extremo de las elecciones, así como apoyar la publicación de los resultados de las auditorías de comparación de las boletas.  Los resultados pueden ser publicados en línea o puestos a disposición de organizaciones de terceros para su validación segura, y permiten a los votantes individuales confirmar que sus votos fueron contados correctamente. 
 
Más información en [la entrada del blog del anuncio](https://blogs.microsoft.com/on-the-issues/?p=63211). 

## Código Abierto
Esta biblioteca y todos los proyectos vinculados a ElectionGuard, están licenciados bajo la licencia del MIT. No hay ningún cargo por el uso de ElectionGuard.

## Core Component
Este es el núcleo del SDK que realiza funciones electorales como la encriptación de los votos, la desencriptación, la generación de claves y el recuento. Este código está pensado para ser ejecutado en el hardware del sistema de votación y para ser integrado en el software del sistema de votación existente (o nuevo). El SDK de ElectionGuard está destinado a añadir verificación y cifrado de extremo a extremo en sistemas de votación integrales de terceros. Se proporcionan aplicaciones simplificadas de prueba de concepto para comprender cómo debe llamarse cada implementación de la API. Actualmente, hay dos implementaciones disponibles.

### C

[📁 Fuente](https://github.com/microsoft/electionguard-c) - https://github.com/microsoft/electionguard-c

### C#
[📁 Fuente](https://github.com/microsoft/electionguard-dotnet) - https://github.com/microsoft/electionguard-dotnet

[📦 Paquete - ElectionGuard.SDK](https://www.nuget.org/packages/ElectionGuard.SDK)


## Especificaciones y documentación
Esta biblioteca contiene las especificaciones fundamentales, la documentación, la arquitectura y las pruebas matemáticas y criptográficas que sustentan a ElectionGuard. Si está buscando entender mejor el sistema, o quiere saber cómo integrar los diversos componentes, hay mucha información valiosa contenida aquí.

[📄 Documentación y especificaciones](https://github.com/jaouahbi/electionguard.wiki.es)

## Reference Implementation
El resto del SDK de ElectionGuard consiste en una implementación de referencia dividida en varios repositorios separados. Estos repositorios, aunque están pensados para ser utilizados conjuntamente como componentes de una solución más amplia, también pueden ser independientes si los desarrolladores sólo desean investigar o implementar un componente.

### Dispositivo de administración
Se trata de una aplicación que se utiliza para administrar los procesos electorales de ElectionGuard, incluida la generación de claves, el aprovisionamiento de fideicomisarios y el recuento posterior a las elecciones, los desciframientos parciales y las pruebas de conocimiento cero.

[📁 Fuente](https://github.com/microsoft/electionguard-admin-device) - https://github.com/microsoft/electionguard-admin-device

### Ballot Box
Esta biblioteca se utiliza para escanear las boletas para generar listas de boletas emitidas y estropeadas en una elección; se utiliza en el recuento para finalizar las operaciones de las boletas (emitidas o estropeadas, etc.) para la publicación de los resultados.

[📁 Fuente](https://github.com/microsoft/electionguard-ballot-box) - https://github.com/microsoft/electionguard-ballot-box


### Ballot Marking Device
Esto contiene una instancia de trabajo del dispositivo de marcado de boletas (BMD). Construido por VotingWorks en consulta con el [Centro de Diseño Cívico] (https://civicdesign.org), este front-end proporciona una interfaz para que un votante complete e imprima una boleta que, en un caso de uso verificable de extremo a extremo, iría acompañada de una identificación de rastreo impresa. Este front-end de BMD se proporciona como una, implementación potencial.

[📁 Fuente](https://github.com/microsoft/electionguard-ballot-marking-device) - https://github.com/microsoft/electionguard-ballot-marking-device


### Tracking Site
Aplicación que demuestra la publicación de artefactos electorales de ElectionGuard en un sitio web público para permitir la búsqueda de ID de verificación, archivos zip descargables de los resultados de las elecciones (para verificadores de terceros) y resúmenes de los resultados de las elecciones.

[📁 Fuente](https://github.com/microsoft/electionguard-tracking-site) - https://github.com/microsoft/electionguard-tracking-site

### Verificador
La aplicación de verificación se utiliza para realizar una verificación externa e independiente de un recuento de elecciones. Este repositorio contiene una implementación de referencia de un verificador construido contra las especificaciones de ElectionGuard. No se trata de la aplicación de verificador *sólo*, sino más bien de un ejemplo. Esta biblioteca debe ser usada en conjunto con las especificaciones técnicas y las guías de uso contenidas en las [especificaciones](specs/readme).

[📁 Fuente](https://github.com/microsoft/electionguard-verifier) - https://github.com/microsoft/electionguard-verifier

### Web API
Se trata de una API que interactúa con los dispositivos de encriptación de la administración para llevar a cabo la encriptación de las boletas, el casting, el deterioro y el recuento. Esto hace uso del paquete C# Nuget.

[📁 Fuente](https://github.com/microsoft/electionguard-web-api) - https://github.com/microsoft/electionguard-web-api


## Problemas de seguridad reportando
Alentamos a la comunidad de desarrolladores y de seguridad a realizar investigaciones, informar sobre cuestiones y sugerir mejoras en este código base. Sin embargo, a diferencia de los errores de rendimiento o de características, por favor **no** informe de las vulnerabilidades de seguridad en los comentarios públicos de Github. Cada repositorio tiene un archivo de SEGURIDAD con instrucciones sobre cómo informar responsablemente de las vulnerabilidades de seguridad en el proceso de CVD de Microsoft.

 ## Contribuyendo
Ayude a defender la democracia y **[contribuya al proyecto][]**.

[Código de Conducta]: CODE_OF_CONDUCT.md
[Contribuir al proyecto]: CONTRIBUIR.md

## ¡Gracias! 🎉
Un enorme agradecimiento a los que han ayudado a contribuir a este proyecto hasta ahora, incluyendo:
* Josh Benaloh (cuya [tesis doctoral](https://www.microsoft.com/en-us/research/publication/verifiable-secret-ballot-elections/) fue el génesis de gran parte de este trabajo)
* [Galois](https://galois.com/) / [Free & Fair](https://freeandfair.us/)
* [VotingWorks](https://voting.works/)
* [Centro de Diseño Cívico](https://civicdesign.org/)
* [Diseño de óxido](https://oxidedesign.com/)
* [Tecnología InfernoRed](https://infernored.com/)
* Muchos equipos dentro de Microsoft
