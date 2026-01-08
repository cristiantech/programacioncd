# Instalación y configuración de Django en Windows

Guía paso a paso para instalar Python, crear un entorno virtual, solucionar errores comunes en Windows y configurar un proyecto Django.

---

## 1. Instalar Python

Descarga Python desde el sitio oficial:

https://www.python.org/downloads/windows/

Durante la instalación:
- Marca la opción **Add Python to PATH**
- Selecciona **Install Now**

Verifica la instalación:

```bash
python --version
```

---

## 2. Crear el entorno virtual

Desde la carpeta de tu proyecto, ejecuta:

```bash
python -m venv .jsc
# .jsc es el nombre del entorno virtual (puedes usar otro si deseas).
```

---

## 3. Problema común en Windows al activar el entorno virtual

Al intentar activar el entorno virtual con:

```bash
.jsc\Scripts\activate
```

Puede aparecer un error como:

```text
running scripts is disabled on this system
```

o

```text
no se puede cargar el archivo Activate.ps1
```

Esto ocurre por la **política de ejecución (Execution Policy)** de PowerShell en Windows.

---

## 4. Solución: actualizar la Execution Policy de PowerShell

Abre **PowerShell como Administrador** y ejecuta:

```powershell
Set-ExecutionPolicy RemoteSigned
# Permite ejecutar scripts locales de forma segura
```

Cuando el sistema pregunte, escribe:

```text
Y
```

Cierra PowerShell y vuelve a abrir la terminal.

⚠️ Este paso solo se realiza una vez en el sistema.

---

## 5. Activar el entorno virtual

Desde la carpeta del proyecto:

### Usando PowerShell

```powershell
.jsc\Scripts\Activate.ps1
```

### Usando CMD

```cmd
.jsc\Scripts\activate.bat
```

Si el entorno se activó correctamente, verás:

```text
(.jsc)
```

al inicio de la terminal.

---

## 6. Actualizar pip (recomendado)

Con el entorno virtual activado:

```bash
python -m pip install --upgrade pip
```

---

## 7. Instalar Django

Ejecuta:

```bash
pip install django
```

Verifica la instalación:

```bash
django-admin --version
```

---

## 8. Crear un proyecto Django

```bash
django-admin startproject mi_proyecto
cd mi_proyecto
```

---

## 9. Ejecutar el servidor de desarrollo

```bash
python manage.py runserver
```

Abre el navegador en:

```text
http://127.0.0.1:8000/
```

---

## 10. Comandos útiles

Desactivar el entorno virtual:

```bash
deactivate
```

Guardar dependencias del proyecto:

```bash
pip freeze > requirements.txt
```

Instalar dependencias desde un archivo:

```bash
pip install -r requirements.txt
```

---

## 11. Notas importantes para Windows

- Usar **PowerShell o CMD** para activar el entorno virtual
- Ejecutar PowerShell como administrador solo para cambiar la Execution Policy
- No es necesario cambiar la policy nuevamente
- Evitar usar **Git Bash** para activar entornos virtuales en Windows

---

✅ Django configurado correctamente en Windows.
    