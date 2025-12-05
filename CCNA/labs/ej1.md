### 💡 Ejercicio 00X: [NOMBRE DEL EJERCICIO]

> Objetivo: [Objetivo breve del ejercicio, por ejemplo: Asegurar un puerto de switch para prevenir accesos no autorizados.]

---

### Paso 1: [Título del Paso]

* **Descripción:** [Describe la acción que se realiza, por ejemplo: Entrar a la interfaz del puerto que vamos a asegurar y ponerlo en modo acceso.]
* **Comandos:**
```cisco
enable
configure terminal
interface GigabitEthernet 0/1
switchport mode access[Imagen de Evidencia: images/ej_XXX_paso1_modo_access.png]

Paso 2: [Título del Paso]
Descripción: [Describe la acción de seguridad principal, por ejemplo: Habilitar la seguridad de puerto y establecer el límite de direcciones MAC a 1.]

Comandos:

Cisco CLI

switchport port-security
switchport port-security maximum 1
[Imagen de Evidencia: images/ej_XXX_paso2_port_security.png]

Paso 3: [Título del Paso (Ej. Guardar y Verificar)]
Descripción: [Describe la acción final, por ejemplo: Guardar la configuración y verificar que la seguridad de puerto esté activa.]

Comandos:

Cisco CLI

end
copy running-config startup-config
show port-security interface GigabitEthernet 0/1
[Imagen de Evidencia: images/ej_XXX_paso3_verificacion.png]


---

## 2. 💻 Código Completo de la Página (`index.html`)

Este código incluye la librería para Markdown, la lógica de `fetch()` para leer tus archivos `.md`, y las instrucciones claras de dónde pegar las rutas.

```html
