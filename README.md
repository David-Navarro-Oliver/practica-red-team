# 🛡️ Laboratorio Red Team en Windows, Debian y Active Directory
![Idioma](https://img.shields.io/badge/idioma-espa%C3%B1ol-blue) ![Tipo](https://img.shields.io/badge/tipo-laboratorio%20acad%C3%A9mico-informational) ![Estado](https://img.shields.io/badge/estado-documentado-2ea44f)

English version: [README_EN.md](README_EN.md)

## 🔒 Aviso de confidencialidad
![Alcance](https://img.shields.io/badge/alcance-entorno%20aislado-critical) ![Uso](https://img.shields.io/badge/uso-formativo-lightgrey)

Este repositorio documenta una práctica académica de Red Team realizada exclusivamente en un entorno virtualizado, aislado y controlado. El contenido no representa actividad ofensiva sobre sistemas reales de terceros, sino una simulación técnica orientada al aprendizaje, la evaluación y la documentación de procedimientos de laboratorio.

## 🎯 Objetivo del proyecto
![Objetivo](https://img.shields.io/badge/objetivo-red%20team%20lab-red) ![C2](https://img.shields.io/badge/C2-Havoc-purple) ![AD](https://img.shields.io/badge/Active%20Directory-familia.local-blue)

El objetivo principal es construir y documentar un laboratorio Red Team con visibilidad entre sistemas Linux y Windows, despliegue de un entorno Command and Control, compromiso controlado de una estación Windows 10, pivoting hacia Windows Server y análisis posterior de relaciones de Active Directory.

El trabajo combina dos bloques: una fase inicial de planificación y reconocimiento OSINT sobre una organización real, y una fase práctica centrada en la creación de una infraestructura local con Debian, Windows 10, Windows Server 2019, Active Directory, Havoc, BloodHound CE y herramientas auxiliares de análisis.

## 🧭 Alcance
![Sistemas](https://img.shields.io/badge/sistemas-Debian%20%7C%20Windows%2010%20%7C%20Server%202019-success) ![Red](https://img.shields.io/badge/red-laboratorio%20NAT-orange)

El alcance cubre la preparación de máquinas Debian, la validación de túneles SSH, la configuración de una estación Windows 10, el despliegue de Windows Server 2019, la promoción a controlador de dominio, la creación de usuarios y grupos, la instalación de Havoc, la generación de sesiones controladas, el uso de BloodHound CE y la validación de rutas de privilegio dentro del dominio.

Quedan fuera de alcance las pruebas sobre infraestructuras externas, técnicas destructivas, acciones no autorizadas y cualquier ejecución fuera del entorno académico definido.

## 🧱 Arquitectura del laboratorio
![Virtualizacion](https://img.shields.io/badge/virtualizaci%C3%B3n-VMware%20Workstation-informational) ![Dominio](https://img.shields.io/badge/dominio-familia.local-blueviolet)

La topología documentada se apoya en varias máquinas virtuales con funciones diferenciadas:

| Componente | Rol en el laboratorio |
| --- | --- |
| Debian 1 | Plataforma de apoyo, operación, túneles y tooling |
| Debian 2 | Nodo auxiliar para validaciones de servicios internos |
| Windows 10 | Endpoint principal del ejercicio |
| Windows Server 2019 | Controlador de dominio, DNS y núcleo de Active Directory |
| Havoc | Framework de Command and Control |
| BloodHound CE | Análisis de relaciones y trayectorias de privilegio |

## 🕵️ Ejercicio 1: OSINT y planificación
![OSINT](https://img.shields.io/badge/fase-OSINT-yellow) ![Organizacion](https://img.shields.io/badge/organizaci%C3%B3n-Carrefour%20Espa%C3%B1a-blue)

La primera parte del informe desarrolla una planificación de reconocimiento sobre Carrefour España. Se identifican la entidad principal, sociedades relacionadas, dominios corporativos, subdominios relevantes, sistemas autónomos, rangos de red y activos prioritarios.

El análisis se mantiene en un plano pasivo y no intrusivo, con especial atención a la delimitación del alcance, la justificación de activos y la priorización inicial de servicios visibles desde fuentes públicas.

## 🖥️ Ejercicio 2: laboratorio técnico
![Laboratorio](https://img.shields.io/badge/fase-laboratorio%20t%C3%A9cnico-red) ![Pivoting](https://img.shields.io/badge/t%C3%A9cnica-pivoting%20SSH-orange) ![Windows](https://img.shields.io/badge/endpoint-Windows%2010-blue)

La segunda parte concentra el desarrollo práctico. Primero se prepara la base Linux, se publican servicios locales y se validan túneles SSH para comprender el tránsito encapsulado. Después se incorpora Windows 10 como endpoint principal y se comprueba el acceso a servicios Windows a través de canales reversos.

Con la conectividad validada, se despliega Windows Server 2019, se configura Active Directory y se crea el dominio `familia.local`. Sobre esta infraestructura se definen identidades, grupos y relaciones que sirven como base para las fases posteriores de enumeración, análisis y progresión controlada.

## ⚙️ Cadena operativa documentada
![Flujo](https://img.shields.io/badge/flujo-acceso%20%7C%20pivot%20%7C%20AD%20%7C%20credenciales-darkgreen) ![Validacion](https://img.shields.io/badge/validaci%C3%B3n-evidencias%20t%C3%A9cnicas-success)

La práctica documenta una cadena técnica completa:

| Fase | Resultado |
| --- | --- |
| Preparación Linux | Servicios locales, conectividad y túneles SSH validados |
| Preparación Windows | Endpoint Windows 10 integrado en la topología |
| Active Directory | Dominio `familia.local`, usuarios, grupos y servidor DNS |
| Command and Control | Teamserver y cliente Havoc operativos |
| Acceso inicial | Sesión controlada sobre Windows 10 |
| Pivoting | Tránsito hacia Windows Server mediante canales internos |
| BloodHound CE | Ingesta y análisis de relaciones del dominio |
| Privilegios | Validación de rutas, escalada de privilegios y modificación controlada de pertenencias |
| Credenciales | Extracción de material de autenticación dentro del laboratorio |
| Payload alternativo | Validación de ejecución mediante cliente Discord modificado |

## 🧪 Herramientas utilizadas
![Tooling](https://img.shields.io/badge/tooling-Havoc%20%7C%20BloodHound%20%7C%20Impacket-lightgrey) ![SSH](https://img.shields.io/badge/t%C3%BAneles-SSH-success)

El laboratorio utiliza herramientas propias de un entorno de práctica Red Team y Active Directory:

| Herramienta | Uso principal |
| --- | --- |
| VMware Workstation | Virtualización del entorno |
| OpenSSH | Túneles directos y reversos |
| proxychains | Enrutado de tráfico a través de canales encapsulados |
| Havoc | Command and Control y gestión de sesiones |
| BloodHound CE | Visualización de relaciones de Active Directory |
| bloodhound.py | Recolección remota de información del dominio |
| Impacket | Validación de acceso remoto y credenciales |
| bloodyAD | Modificación controlada de objetos y pertenencias |
| asar | Modificación y reempaquetado de cliente Discord |

## 📌 Auditoría del contenido
![Revision](https://img.shields.io/badge/revisi%C3%B3n-documental-blue) ![Madurez](https://img.shields.io/badge/madurez-alta-2ea44f)

El documento original presenta una estructura sólida, con alcance definido, metodología progresiva, evidencias por fase y una conclusión técnica coherente. La secuencia operativa está bien conectada: infraestructura, tránsito, dominio, C2, acceso inicial, pivoting, enumeración, modificación de privilegios, extracción de credenciales y validación de ejecución alternativa.

Como mejora documental, sería recomendable añadir un diagrama visual de red, una tabla final de direccionamiento, una matriz de riesgos defensivos y una sección de lecciones aprendidas separada de la conclusión.

## ✅ Resultado final
![Resultado](https://img.shields.io/badge/resultado-laboratorio%20funcional-success) ![Entrega](https://img.shields.io/badge/entrega-README%20biling%C3%BCe-blue)

El ejercicio cumple el objetivo principal y lo amplía con fases avanzadas sobre Active Directory y ejecución alternativa de payload. El resultado es un laboratorio Red Team verificable, documentado y reproducible a nivel conceptual, construido íntegramente sobre máquinas propias y sin interacción con sistemas reales de terceros.

