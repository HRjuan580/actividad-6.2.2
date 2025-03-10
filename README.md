# actividad-6.2.2

# Codigo plantUML
@startuml

' Diagrama de Secuencia Estereotipado: CU - Validación Usuario
actor Usuario
boundary UI <<boundary>>
control ControlAutenticacion <<control>>
entity BaseDatos <<entity>>

Usuario -> UI : ingresar credenciales
UI -> ControlAutenticacion : validar usuario y contraseña
ControlAutenticacion -> BaseDatos : consultar usuario y contraseña
BaseDatos --> ControlAutenticacion : devuelve resultado validación
ControlAutenticacion --> UI : respuesta validación
UI --> Usuario : mostrar resultado

@enduml
![image](https://github.com/user-attachments/assets/c7cb3c9f-1f65-45b8-9301-eb7dc3fa0584)

@startuml

' Diagrama de Secuencia Final: CU - Validación Usuario
actor Usuario
boundary InterfazUsuario
control GestorAutenticacion
entity RepositorioUsuarios

Usuario -> InterfazUsuario : ingresar credenciales
InterfazUsuario -> GestorAutenticacion : validar usuario y contraseña
GestorAutenticacion -> RepositorioUsuarios : consultar usuario y contraseña
RepositorioUsuarios --> GestorAutenticacion : devuelve resultado validación
GestorAutenticacion --> InterfazUsuario : respuesta validación
InterfazUsuario --> Usuario : mostrar resultado

@enduml
![image](https://github.com/user-attachments/assets/03ca77db-cf52-49bd-b5db-e3fb7f6f04be)

@startuml

' Diagrama de Secuencia Estereotipado: CU - Sacar Dinero
actor Usuario
boundary Cajero <<boundary>>
control ControlTransaccion <<control>>
entity CuentaBancaria <<entity>>

Usuario -> Cajero : ingresar tarjeta y PIN
Cajero -> ControlTransaccion : validar credenciales
ControlTransaccion -> CuentaBancaria : verificar saldo
CuentaBancaria --> ControlTransaccion : saldo disponible
ControlTransaccion -> CuentaBancaria : debitar saldo
CuentaBancaria --> ControlTransaccion : confirmación débito
ControlTransaccion -> Cajero : autorizar retiro
Cajero -> Usuario : entregar dinero

@enduml
![image](https://github.com/user-attachments/assets/ac844da7-9d64-4e52-ad30-cba2911421aa)

@startuml

' Diagrama de Secuencia Final: CU - Sacar Dinero
actor Usuario
boundary TerminalATM
control GestorTransacciones
entity CuentaCliente

Usuario -> TerminalATM : ingresar tarjeta y PIN
TerminalATM -> GestorTransacciones : validar credenciales
GestorTransacciones -> CuentaCliente : verificar saldo
CuentaCliente --> GestorTransacciones : saldo disponible
GestorTransacciones -> CuentaCliente : debitar saldo
CuentaCliente --> GestorTransacciones : confirmación débito
GestorTransacciones -> TerminalATM : autorizar retiro
TerminalATM -> Usuario : entregar dinero

@enduml

![image](https://github.com/user-attachments/assets/6263d842-e6a1-41dc-8c08-d4c4f07b8e1c)

c) Responde a la pregunta: ¿De que manera te ayuda un diagrama de secuencias durante el proceso de desarrollo del software? 
(Entrega:
Un diagrama de secuencias ayuda a visualizar la interacción entre actores y el sistema, facilitando la comunicación, el diseño y la implementación. Mejora la claridad del flujo del sistema, optimiza la mantenibilidad y ayuda en pruebas y depuración al identificar errores y validar la lógica del software.)
