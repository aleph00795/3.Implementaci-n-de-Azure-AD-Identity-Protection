# Implementación de Azure AD Identity Protection
## Tarea 4: Configurar el acceso condicional (requerir MFA)

Nota: Esta tarea requiere una cuenta de usuario, AZ500User1. Si desea mostrar la verificación de MFA, la cuenta de usuario debe tener un número de teléfono.

En esta tarea revisaremos la configuración de la directiva de acceso condicional y crearemos una directiva que requiera MFA al iniciar sesión en el portal.

CONFIGURACION DE LA DIRECTIVA 

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


PRUEBA DE LA DIRECTIVA 

1. Inicie sesión en el Portal como AZ500User1.

2. Para poder iniciar sesión se requiere una segunda autenticación.

![image](https://user-images.githubusercontent.com/110675810/189019333-ec2ba038-7c8d-45e9-98b8-43a367c11655.png)

3. Si tiene un número de teléfono asociado al usuario, proporcione y compruebe el código de texto. Debería poder iniciar sesión correctamente en el portal.

![image](https://user-images.githubusercontent.com/110675810/189019581-375a3b80-9c85-4f32-8b7e-216d091c0dd3.png)

![image](https://user-images.githubusercontent.com/110675810/189019977-6d19a84b-deac-46d1-82d1-7cded7a528a0.png)

4. Si no tiene un número de teléfono asociado al usuario, esto demuestra que MFA está en vigor.

5. Es posible que quiera volver a AZ500Policy1 y desactivar la directiva.

![image](https://user-images.githubusercontent.com/110675810/189020476-bee44e91-e2fc-4f5f-b476-ec4ba468355b.png)
