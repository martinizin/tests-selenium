# Proyecto VV Selenium — Suite de Regresión Básica

**Curso:** Validación y Verificación de Software  
**Universidad:** Universidad de las Américas (UDLA)  
**Sitio bajo prueba:** [SauceDemo](https://www.saucedemo.com/)

---

## Pre-requisitos

- Navegador Firefox o Chrome actualizado.
- Extensión **Selenium IDE ≥ 4.0**:
  - Firefox: https://addons.mozilla.org/firefox/addon/selenium-ide/
  - Chrome: https://chromewebstore.google.com/detail/selenium-ide/mooikfkahbdckldjjndioackbalphokd

---

## Credenciales SauceDemo

| Usuario           | Password       | Comportamiento esperado                                                              |
|-------------------|----------------|--------------------------------------------------------------------------------------|
| `standard_user`   | `secret_sauce` | Login exitoso → redirige a `/inventory.html`                                         |
| `locked_out_user` | `secret_sauce` | Error: usuario bloqueado                                                             |
| `wrong_user`      | `wrong_pass`   | Error: "Epic sadface: Username and password do not match any user in this service"   |

---

## Importar y ejecutar la suite

1. Abrir Selenium IDE desde el ícono de la extensión en el navegador.
2. Seleccionar **"Open an existing project"**.
3. Cargar el archivo `selenium/Suite_Regresion_Basica.side`.
4. En el panel izquierdo, seleccionar la suite **`Suite_Regresion_Basica`**.
5. Click en **"Run all tests in suite"** (▶▶).
6. Esperar a que los tres tests finalicen — todos deben aparecer en verde.

---

## Personalización (antes de ejecutar)

Abrir `selenium/Suite_Regresion_Basica.side` en un editor de texto y reemplazar:

```json
"name": "Proyecto_VV_Apellido_Nombre"
```

con tu apellido y nombre reales, por ejemplo:

```json
"name": "Proyecto_VV_Pillacela_Martin"
```

---

## Casos de prueba incluidos

| ID   | Nombre                  | Tipo              | Aserciones clave                                      |
|------|-------------------------|-------------------|-------------------------------------------------------|
| CP01 | Login Happy Path        | Flujo positivo    | `assertText` título "Products", `assertLocation` URL  |
| CP02 | Login Negativo          | Prueba negativa   | `verifyText` mensaje de error exacto                  |
| CP03 | Carrito Dinámico        | Elementos dinámicos | `assertText` badge=2, `verifyElementNotPresent`     |

---

## Estructura del repositorio

```
selenium-tests/
├── README.md
├── Selenium.md                        # PRD del proyecto
├── .gitignore
├── selenium/
│   └── Suite_Regresion_Basica.side    # Proyecto Selenium IDE
└── informe/
    ├── informe_practica.md            # Plantilla del informe (completar tras ejecución)
    └── evidencias/                    # Screenshots de ejecución
```

---

## Checklist de tareas manuales pendientes

- [ ] Reemplazar `Proyecto_VV_Apellido_Nombre` en el `.side` con tu nombre real.
- [ ] Ejecutar la suite completa en Selenium IDE.
- [ ] Capturar `informe/evidencias/01_log_passed.png` (log verde).
- [ ] Capturar `informe/evidencias/02_assert_editor.png` (comando assertText CP01).
- [ ] *(Opcional)* Capturar `informe/evidencias/03_error_cp02.png`.
- [ ] Completar todos los `<!-- TODO MANUAL -->` en `informe/informe_practica.md`.
- [ ] Commit final: `docs: completar informe con evidencias de ejecución`

Ver detalles completos en `Selenium.md` § 5.
