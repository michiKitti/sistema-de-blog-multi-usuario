#  Sistema de Blog Multi-usuario 

##  Descripción
Este proyecto consiste en un **sistema de consola en Python** que permite a diferentes autores **escribir, editar y gestionar sus propias publicaciones de blog**.  
Cada autor puede iniciar sesión (de forma simulada), crear publicaciones con etiquetas (tags), y mantener control total sobre sus propios posts.

---

##  Entidades y Relaciones

### 1️ **Autores (`autores.csv`)**
Contiene la información básica de cada autor.

| Campo | Descripción |
|--------|--------------|
| `id_autor` | Identificador único y numérico del autor |
| `nombre_autor` | Nombre completo del autor |
| `email` | Correo electrónico único |

---

### 2️ **Publicaciones (`posts.json`)**
Cada publicación es un objeto con su información completa y asociada a un autor.

| Campo | Descripción |
|--------|--------------|
| `id_post` | Identificador único y numérico del post |
| `id_autor` | ID del autor que creó la publicación |
| `titulo` | Título del post |
| `contenido` | Texto o cuerpo de la publicación |
| `fecha_publicacion` | Fecha en que fue creada la publicación |
| `tags` | Lista de etiquetas o temas del post (por ejemplo: `["python", "desarrollo"]`) |

---

##  Funcionalidades Clave

-  **CRUD completo para Autores**  
  Crear, leer, actualizar y eliminar autores, con validación de datos.

-  **Crear nueva Publicación**  
  Asignar automáticamente la publicación al autor que tiene sesión iniciada (simulado).

-  **Ver publicaciones de un autor específico**  
  Permite filtrar y listar los posts de un autor en particular.

-  **Buscar publicaciones por tag**  
  Filtra publicaciones que contengan un tag específico (búsqueda no sensible a mayúsculas/minúsculas).

-  **Modificar y eliminar publicaciones propias**  
  Solo el autor que creó un post puede modificarlo o eliminarlo.

---

##  Reto Adicional

Implementar el manejo de **comentarios anidados** en las publicaciones.  
Cada publicación podrá contener una **lista de comentarios** dentro del objeto JSON, permitiendo responder comentarios dentro de otros comentarios.

**Ejemplo:**
```json
{
  "id_post": 1,
  "titulo": "Aprendiendo Python",
  "comentarios": [
    {
      "autor": "Allison",
      "contenido": "Excelente post!",
      "respuestas": [
        {
          "autor": "David",
          "contenido": "Totalmente de acuerdo 👍"
        }
      ]
    }
  ]
}
