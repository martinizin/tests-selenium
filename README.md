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
├── .gitignore
├── selenium/
│   └── Suite_Regresion_Basica.side    # Proyecto Selenium IDE


---
.
