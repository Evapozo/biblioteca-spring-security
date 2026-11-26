cambiar a build donde se crean instancias de libro y de autor
donde añadas la etiqueta de builder añade allargsconstructor
- repasar tabla builder de solid y patrones .md
- AutorMapper LibroMapper AutorRepositoryJdbc LibroRepositoryJdbc

- ocultar botones a quien no es admin sec:authorize="hasRole('ADMIN')"	
- en lugar de vista 403, capturar la excepcion de acceso denegado y redirigir a la página de login con mensaje de error
- login get es la vista, post es la accion de login 
- usuariorepositoryjdbc inversion de dependencias. @primary en memoria


## Reto: rol bibliotecario
1. UsuarioRepositoryMemoria: añadir un usuario con rol BIBLIOTECARIO
2. SecurityConfig: añadir un requestMatcher para que el rol BIBLIOTECARIO pueda acceder a /libros y /autores
bibliotecario puede dar de alta y editar libros y autores, pero no puede borrar. Solo el admin puede borrar.
3. libros/lista.html: añadir en el boton de borrar que solo sea visible para ADMIN.
en cada vista que uses sec:authorize="hasRole('ADMIN')" debes importar el namespace xmlns:sec="http://www.thymeleaf.org/extras/spring-security" en la etiqueta html
4. autores/lista.html: añadir en el boton de borrar que solo sea visible para ADMIN.
y en el boton de editar hasAnyRole('ADMIN', 'BIBLIOTECARIO') para que el bibliotecario pueda editar autores.
añade sec:authorize="hasAnyRole('ADMIN', 'BIBLIOTECARIO')" en el td para que no pinte la columna