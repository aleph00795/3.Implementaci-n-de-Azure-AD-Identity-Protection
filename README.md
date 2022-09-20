https://learn.microsoft.com/es-mx/training/modules/azure-ad-identity-protection/

## Tarea 1: Configurar el acceso condicional (requerir MFA)

Nota: Esta tarea requiere una cuenta de usuario, AZ500User1. Si desea mostrar la verificación de MFA, la cuenta de usuario debe tener un número de teléfono.

En esta tarea revisaremos la configuración de la directiva de acceso condicional y crearemos una directiva que requiera MFA al iniciar sesión en el portal.

### CONFIGURACION DE LA DIRECTIVA 

1. En el Portal busque Azure Active Directory y selecciónelo.

2. En Administrar seleccione Seguridad.

3. En Proteger seleccione Acceso condicional.

![image](https://user-images.githubusercontent.com/110675810/188899798-590cadb3-d194-4a32-a450-9b485d14bc5a.png)

4. Haga clic en Nueva directiva.

 - Nombre: AZ500Policy1

 - Usuarios y grupos > Seleccionar usuarios y grupos > Usuarios y grupos > Seleccione: AZ500User1

![image](https://user-images.githubusercontent.com/110675810/189017199-a63ac339-63fa-43bb-ac00-8bcb887325b1.png)

 - Aplicaciones en la nube o acciones > Seleccionar aplicaciones > Seleccione: Microsoft Azure Management

![image](https://user-images.githubusercontent.com/110675810/189017538-4767d2af-066f-4d1a-87ad-a7aef5951231.png)

 - Revise la advertencia de que esta directiva afecta al acceso al portal.

![image](https://user-images.githubusercontent.com/110675810/189017798-3f10aa31-217f-4918-b744-bec54bdf5e8e.png)

 - Condiciones > Riesgo de inicio de sesión > Revise los niveles de riesgo

![image](https://user-images.githubusercontent.com/110675810/189017948-42ec0388-e6ae-4762-885c-f61c291ad1a6.png)

 - Plataformas de dispositivos > Revise los dispositivos que pueden incluirse, como Android e iOS.

![image](https://user-images.githubusercontent.com/110675810/189018063-68ad383e-cec6-4727-b2c5-d69bdee3f771.png)

 - Ubicaciones > Revise las selecciones de ubicación física.

![image](https://user-images.githubusercontent.com/110675810/189018165-4b52f4f4-14c8-4bae-882f-3c08363ab5d0.png)

 - En Controles de acceso, haga clic en Conceder.

 - Revise las opciones de concesión, como MFA. Puede requerir uno o varios de los controles.

 - Seleccione Requerir autenticación multifactor.

![image](https://user-images.githubusercontent.com/110675810/189018324-d166be33-b3c5-493b-808c-28e66476c0b9.png)

5. En Habilitar directiva seleccione Activado.

![image](https://user-images.githubusercontent.com/110675810/189018513-ee7d5fb2-0c66-4dee-b77d-38a7ed5c7823.png)

Haga clic en Crear.

![image](https://user-images.githubusercontent.com/110675810/189018613-077949a8-1317-477a-be4d-1ac36c0539d9.png)

### PRUEBA DE LA DIRECTIVA 

1. Inicie sesión en el Portal como AZ500User1.

2. Para poder iniciar sesión se requiere una segunda autenticación.

![image](https://user-images.githubusercontent.com/110675810/189019333-ec2ba038-7c8d-45e9-98b8-43a367c11655.png)

3. Si tiene un número de teléfono asociado al usuario, proporcione y compruebe el código de texto. Debería poder iniciar sesión correctamente en el portal.

![image](https://user-images.githubusercontent.com/110675810/189019581-375a3b80-9c85-4f32-8b7e-216d091c0dd3.png)

![image](https://user-images.githubusercontent.com/110675810/189019977-6d19a84b-deac-46d1-82d1-7cded7a528a0.png)

4. Si no tiene un número de teléfono asociado al usuario, esto demuestra que MFA está en vigor.

5. Es posible que quiera volver a AZ500Policy1 y desactivar la directiva.

![image](https://user-images.githubusercontent.com/110675810/189020476-bee44e91-e2fc-4f5f-b476-ec4ba468355b.png)

## Tarea 2: Revision de acceso

En esta tarea, configuraremos una revisión de acceso.

### CONFIGURACION DE UNA REVISION DE ACCESO

1. En Portal, busque y seleccione Identity Governance.

2. En Revisiones de acceso seleccione Revisiones de acceso.

3. Haga clic en Nueva revisión de acceso.

![image](https://user-images.githubusercontent.com/110675810/189220977-5a3d8f47-bac6-47cf-898e-08678f528c67.png)

4. Crearemos una revisión de acceso para asegurarnos de que validamos la pertenencia al grupo AZ500Admin.

![image](https://user-images.githubusercontent.com/110675810/189221145-3e7ef15e-8171-4e19-b14f-a77680a1fe84.png)

5. Complete la información necesaria y analice cada parámetro. Los valores de configuración se agregan a medida que realiza las selecciones. Por ejemplo, si selecciona una revisión de acceso semanal, se le pedirá la duración.

- Nombre de revisión: AZ500Review
- Fecha de inicio: fecha actual
- Frecuencia: una sola vez
- Usuarios para revisar: miembros de un grupo
- Ámbito: Todos
- Seleccione un grupo: AZ500Admins
- Revisores: Usuario seleccionado
- Seleccionar revisores: agréguese como revisor
- Revise la Configuración de finalización, específicamente la acción si un revisor no responde.
- Revise Configuración avanzada.

![image](https://user-images.githubusercontent.com/110675810/189221653-cbec3320-dbb9-4b8a-b033-342302d89ef4.png)

![image](https://user-images.githubusercontent.com/110675810/189221929-f4ffb27e-9e66-40cf-b184-0b3806fc0662.png)

![image](https://user-images.githubusercontent.com/110675810/189221980-d4cca832-100c-458c-9923-be7c4850e929.png)

6. Inicie la revisión de acceso.

![image](https://user-images.githubusercontent.com/110675810/189222142-289f91ce-65db-4324-bb75-376595dbe45c.png)

7. En la página Revisión de acceso asegúrese de que aparece la nueva revisión de acceso.

8. El Estado cambiará de No iniciado a Inicializando.

![image](https://user-images.githubusercontent.com/110675810/189229816-1b3addda-6457-4e28-95ee-1f74ab0e74ea.png)

### REALIZACION DE UNA REVISION DE ACCESO 

En esta tarea, realizaremos una revisión de acceso.

1. Una vez completada la revisión de acceso, recibirá un correo electrónico. Este es el correo electrónico asociado a su cuenta de revisor.

2. Vea el correo electrónico y analice las instrucciones de revisión. Tenga en cuenta cuándo finalizará el período de revisión.

![image](https://user-images.githubusercontent.com/110675810/189230963-003145b9-b091-4623-aaaf-454633d66be4.png)

3. En el correo electrónico, haga clic en Iniciar revisión.

![image](https://user-images.githubusercontent.com/110675810/189231459-9cbab696-1719-4973-9513-e76f741badd9.png)

4. En la página Revisiones de acceso, haga clic en AZ500Review.

5. Observe que está revisando los miembros del grupo AZ500Admin. Hay dos miembros.

6. Use el vínculo Detalles para ver información sobre el usuario.

7. Seleccione Aprobar para un usuario y Denegar para el otro. Asegúrese de proporcionar un motivo.

![image](https://user-images.githubusercontent.com/110675810/189231753-41245bcf-eab8-4d46-94f0-3f369d78cbf0.png)

![image](https://user-images.githubusercontent.com/110675810/189232005-d9891cf5-d559-4b08-8e6a-ce223331276c.png)

Envíe las revisiones.

### REVISION DE LOS RESULTADOS DE LA REVISION DE ACCESO

En esta tarea, revisaremos los resultados de la revisión de acceso.

1. Vuelva al portal.

2. Haga clic en AZ500Review.

3. En la hoja Información general revise los resultados.

4. Debe haber un miembro aprobado y un miembro denegado.

![image](https://user-images.githubusercontent.com/110675810/189234164-e275b8de-de1a-4a73-a986-b03d5e45c965.png)

![image](https://user-images.githubusercontent.com/110675810/189234265-23d1604a-1237-42a3-ab1b-61d14dbd06dc.png)

5. Haga clic en Resultados para obtener información más detallada sobre el revisor y sus motivos.

![image](https://user-images.githubusercontent.com/110675810/189234719-4907c050-2a0f-4519-80d6-7adc449e28bb.png)

![image](https://user-images.githubusercontent.com/110675810/189234825-c86a6979-7171-47e3-850f-f19b5431ccc0.png)

6. En la hoja Información general, haga clic en Detener y confirme que desea detener la revisión.

![image](https://user-images.githubusercontent.com/110675810/189234922-307d81ab-577d-4068-b669-34ee50a12c38.png)

![image](https://user-images.githubusercontent.com/110675810/189235017-b204dc31-e5fc-4a50-808c-e4bf379333b9.png)

7. El Estado de revisión ahora debe ser Completar.

![image](https://user-images.githubusercontent.com/110675810/189235428-9e3aed7a-8d5e-418e-8e15-1d9d8e1b5c2e.png)

![image](https://user-images.githubusercontent.com/110675810/189235525-0952074d-c604-44cc-8c87-bac52f376c3b.png)


### APLICACION DE REVISION DE ACCESO

En esta tarea, se aplicarán los resultados de la revisión.

1. En el Portal, busque Azure Active Directory y selecciónelo.

2. En Administrar seleccione Grupos.

3. Busque el grupo AZ500Admins.

4. Revise los miembros del grupo.

5. Confirme que hay dos miembros.

![image](https://user-images.githubusercontent.com/110675810/189235981-3a7df395-53f9-40a4-a168-8e9d587caf2f.png)

![image](https://user-images.githubusercontent.com/110675810/189236204-854e1061-baa6-42a7-9dc8-0cb61ce2f4c2.png)

6. Haga clic en AZ500Review.

7. Haga clic en Aplicar.

![image](https://user-images.githubusercontent.com/110675810/189239798-99babcbd-d820-401d-94a8-12352cc75d28.png)

![image](https://user-images.githubusercontent.com/110675810/189239885-adfec970-e071-4f8d-9a4e-d2309412deeb.png)

8. Confirme que desea quitar el miembro denegado.

9. El Estado de revisión cambiará de Aplicando a Resultado aplicado.

10. Compruebe que el grupo AZ500Admins ahora solo tiene un miembro.

