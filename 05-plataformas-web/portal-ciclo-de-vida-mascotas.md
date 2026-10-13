# Portal web del ciclo de vida de mascotas

**Categoría:** [Plataformas web](README.md) · **Tecnologías:** MySQL, MCP, full-stack

Portal para gestionar la vida de un perro (vacunas, salud, crecimiento, seguros, memorial). Incluye la idea original y 3 prompts encadenados.

> **Antes de usarlo, reemplaza:** `[TU_CONTRASEÑA_MYSQL]`, `[TU_USUARIO_MYSQL]`

## Prompt

```text
Prompt original
PORTAL WEB DEL CICLO DE VIDA DE MASCOTAS
Quiero realizar un portal web de mascotas de perros donde tenga todo el proceso desde donde nacen, bautizo con nombre de la mascota, llevar el itinerario de vacunas, alimentación, peso, ejercicios, a través de los años, gustos, comida favorita, ropa favorita y también debe tener la información de los dueños, además los perros deben tener un seguro de vida y al final donde serán sepultados.

Prompt # 1
Actúa como arquitecto de software y desarrollador full-stack senior. Necesito diseñar y construir un portal web para la gestión integral del ciclo de vida de perros (mascotas), desde su nacimiento hasta su etapa final.

0) Creación de la base de datos
Ya se tiene instalada en MYSQL local una base de datos llamada “mascotas” en la que puedes acceder por el conector por el MCP llamado “msyql” para que construyas todas las tablas y relaciones necesarias para que funcione el portal web de mascotas.
Los datos de conexión local por si los necesitas son:
        "MYSQL_HOST": "localhost",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "[TU_USUARIO_MYSQL]",
        "MYSQL_PASSWORD": "[TU_CONTRASEÑA_MYSQL]",
        "MYSQL_DATABASE": "mascotas"

1) Objetivo del sistema
Crear una plataforma donde cada dueño pueda registrar y administrar uno o varios perros, llevando un historial completo y ordenado por años, con trazabilidad y reportes.

2) Módulos y funcionalidades
A. Gestión de dueños
- Registro e inicio de sesión (autenticación).
- Perfil del dueño: datos personales, contacto, dirección, y documentos (opcional).
- Relación dueño ↔ perros (un dueño puede tener varios perros).
B. Registro del perro (ciclo de vida)
- Datos básicos: nombre, raza, sexo, fecha de nacimiento, lugar, fotos.
- Origen/nacimiento: criadero o lugar de procedencia, información de padres (si aplica).
- “Bautizo” / ceremonia de nombre: fecha, nombre asignado, notas y fotos.
C. Salud y veterinaria
- Itinerario / calendario de vacunas: tipo de vacuna, fecha programada, fecha aplicada, veterinario, lote, observaciones.
- Recordatorios y alertas (vacunas próximas o vencidas).
- Historial médico: consultas, diagnósticos, medicamentos, alergias.
D. Alimentación y nutrición
- Plan de alimentación por etapas (cachorro, adulto, senior).
- Registro de comidas: tipo, marca, porciones, horarios.
- Comida favorita y restricciones.
E. Crecimiento y actividad
- Registro de peso (línea de tiempo / gráfica).
- Registro de ejercicios: tipo, duración, intensidad, frecuencia.
- Metas y seguimiento (por semana/mes).
F. Gustos y preferencias
- Gustos, juguetes favoritos, actividades favoritas.
- Comida favorita y premios preferidos.
G. Ropa y accesorios
- Inventario de ropa favorita: tipo, talla, color, fotos.
- Accesorios (collar, placa, correa, etc.).
H. Momentos inolvidables
- Se debe poder subir fotografías y un breve comentario donde este el perro con los dueños o amigos en diferentes momentos.
I. Seguro de vida
- Datos de póliza: aseguradora, número, vigencia, valor, beneficiarios, condiciones.
- Pagos/cuotas (si aplica) y estado del seguro.
- Registro de reclamos o eventos relacionados.
J. Etapa final y memorial
- Registro de fallecimiento (fecha, causa opcional, notas).
- Lugar de sepultura: cementerio/ubicación, referencia (mapa o coordenadas), datos de contacto.
- Sección “memorial” con fotos y línea de tiempo del perro.

3) Roles de usuario (mínimo)
- Dueño (gestiona sus perros).
- Administrador (gestiona catálogos, usuarios, seguridad).
- Veterinario (registra vacunas/consultas con permisos).

4) Requisitos no funcionales
- Seguridad: contraseñas cifradas, control de acceso por roles.
- Privacidad: datos personales protegidos.
- Auditoría básica: historial de cambios críticos.
- Diseño responsive (móvil y escritorio).
- Copias de seguridad y exportación (PDF/Excel del historial por perro).

5) Entregables que debes generar
1. Arquitectura (frontend, backend, base de datos).
2. Modelo de datos (tablas y relaciones).
3. Lista de pantallas (UI) y flujo de navegación.
4. Endpoints API principales (CRUD).
5. Alcance MVP (primera versión) + roadmap de mejoras.
6. Ejemplo de datos de prueba (dueño + 2 perros con registros + veterinario).

Prompt # 2
Analizar la base de datos el backend y el frontend de mascotas y realizar las siguientes acciones
1. Revisar y realizar los cambios de la aplicación que tiene tres roles y veo que cuando ingreso a alguno de los tres roles de Dueño, Admin, Veterinario tienen las mismas opciones.
2. Completar unas opciones de los botones  de agregar de agendar, salud, crecimiento, momentos, además que deben también funcionar los botones de eliminar.
3. Además, analizando la base de datos de 48 tablas, veo que entorno grafico faltan varias opciones.
4. Realizar también el modulo de reportes y exportar
5. Al final revisar todos los cambios, verificar y reportar.

Prompt # 3
Quiero que revises todo lo creado y hagas una landing page de venta de comida, ropa, accesorios, seguros de vida para las mascotas (perros), seguros funerarios etc. como página principal y en alguna parte que se pueda acceder al portal web
```
