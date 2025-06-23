# CONFIGURACIÓN DE OPENSSH EN WS 2019 O SUPERIORES

- **Instalar el OpenSSH en Powershell como Administrador:**
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0

- **Verificar que este correctamente instalado:**
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH.Server*'

- **Asegurarse de que el archivo de configuración "sshd_config" existe y contenga contenido:**
notepad C:\ProgramData\ssh\sshd_config

- **El archivo de contener lo siguiente, si no está agrégalo:**
Port 22
Protocol 2
AddressFamily any
ListenAddress 0.0.0.0
PasswordAuthentication yes
Subsystem sftp sftp-server.exe

- **Asignar el servicio para que arranque automáticamente e intentar iniciarlo:**
Set-Service -Name sshd -StartupType Automatic
Start-Service sshd

- **Asegurarse en AZURE lo siguiente o sino crearlo (Muy importante):**
Crea una nueva regla de entrada:
    • Nombre: Allow-SSH
    • Prioridad: 300 (o menor si tienes reglas más restrictivas)
    • Puerto origen: * o 1024-65535
    • Puerto destino: 22
    • Protocolo: TCP
    • Acción: Permitir
    • Dirección: Entrada
Origen/Destino: Cualquiera (o lo que requiera tu seguridad)