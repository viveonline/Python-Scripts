# Python-Scripts
Scripts de todos los dias
Este script de Python utiliza el módulo psutil para recopilar información del sistema y enviar una alerta por correo electrónico si el uso de la CPU es mayor del 90%.
```
import psutil
import smtplib

# Obtener el uso de la CPU
cpu_usage = psutil.cpu_percent()

if cpu_usage > 90:
    # Enviar una alerta por correo electrónico
    server = smtplib.SMTP("smtp.example.com")
    message = "El uso de la CPU es del {}%".format(cpu_usage)
    server.sendmail("alert@example.com", "ops@example.com", message)
    server.quit()
```

Este script de Python utiliza el módulo GitPython para clonar un repositorio de Git y desplegar el código en un servidor.
```
import git
import shutil
import subprocess

# Clonar el repositorio
repo = git.Repo.clone_from("https://github.com/user/repo.git", "repo")

# Copiar los archivos a un directorio de producción
shutil.copytree("repo/src", "/var/www/myapp")

# Ejecutar comandos en el servidor
subprocess.run(["systemctl", "restart", "nginx"])
```


Comandos en un servidor a través del módulo subprocess.

```
import subprocess

# Ejecutar un comando en el servidor
output = subprocess.run(["ls", "-l", "/var/log"])

# Mostrar el resultado
print(output.stdout)

# Ejecutar varios comandos en el servidor
commands = [
    "apt update",
    "apt upgrade -y",
    "reboot"
]

for command in commands:
    subprocess.run(command, shell=True)
```
