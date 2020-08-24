1. Debido a que Talend hace modificaciones al archivo talend.project.xml cuando se cierra el proyecto, solo un desarrollador puede trabajar en el proyecto al mismo tiempo. Sino se generarán conflictos al realizar el merge que se tendrán que solucionar manualmente. Cada commit se debe hacer luego de haber cerrado el proyecto.

2. Se debe agregar y hacer commit del proyecto completo cada vez. Incluyendo la metadata oculta y los directorios de compilación (.metadata, .JETEmitters and .Java).

3. Por las razones 1 y 2 se debe crear un job diferente para cada proyecto en lugar de tener un único proyecto para todos los jobs.

4. El git diff es dificil de leer debido a todo lo que hace talend por debajo.

5. En el caso de que llegue un nuevo desarrollador al proyecto. Las acciones a realizar son sencillas:
  - Clonar el proyecto: git clone https://github.com/sw-hcm-dl/tldReporteador.git
  - Iniciar Talend Open Studio. Al inicio, cambie el espacio de trabajo (en el sentido de Talend, cambie la conexión) y apunte al directorio creado por el comando anterior.
  - Reiniciar Talend según lo solicitado.
  - Entonces notará que Talend no reconoce el proyecto proveniente de Git. El truco consiste en crear el proyecto, siguiendo estrictamente el nombre del proyecto Git. Esto no sobrescribirá el proyecto Git, solo lo guardará como existente.
