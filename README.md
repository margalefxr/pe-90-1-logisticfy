# Mac Guardian 2.1

Mantenimiento y seguridad **automáticos** para macOS (Intel y Apple Silicon).

## Instalación

```bash
cd carpeta/donde/lo/descargaste
chmod +x install.sh mac-guardian.sh
sudo ./install.sh
sudo mac-guardian --auto      # primera pasada completa a mano
```

A partir de ahí funciona solo, con dos tareas:

| Tarea | Cuándo | Qué hace |
|---|---|---|
| Revisión completa (`--auto`) | Cada día a las 10:30 (o al despertar) | Revisa todo, limpia, actualiza y corrige. Los domingos también verifica el disco, las firmas de las apps y pasa el antivirus |
| Vigilante (`--watch`) | Cada 15 minutos | CPU, RAM, calor, batería, ladrones de sesión, procesos maliciosos, accesos remotos y elementos de arranque nuevos |

Solo recibes una notificación cuando hay algo. Los informes están en `/Library/Logs/MacGuardian/`.

## Qué hace automáticamente

**Actualizaciones**
- Instala macOS, las actualizaciones de seguridad "ocultas" (Respuestas de seguridad, XProtect, Gatekeeper), el firmware y los drivers de Apple.
- Deja activadas las actualizaciones automáticas de seguridad.
- Actualiza todo lo instalado con Homebrew (incluidas las apps) y las apps de la App Store, para lo que instala `mas`.

**Seguridad**
- Activa el firewall, el modo sigiloso y Gatekeeper.
- Desactiva la cuenta de invitado y el inicio de sesión automático.
- Corrige los permisos de tu carpeta personal y de `~/.ssh`.
- Desactiva SSH, Compartir pantalla, Gestión remota y Eventos Apple remotos, cierra las sesiones remotas y los túneles ngrok/cloudflared.
- Elimina los proxies del sistema que no sean locales. Los de `127.0.0.1` (Burp o ZAP) se respetan.
- Manda a **cuarentena**:
  - elementos de arranque sospechosos o huérfanos;
  - binarios sin firma que corren desde `/tmp`;
  - políticas de adware que fuerzan extensiones;
  - lo que detecte ClamAV, que se instala solo los domingos si tienes Homebrew.

**Robo de sesión**
- Mata cualquier proceso **sin firma** que lea las cookies, las contraseñas o el llavero del navegador.
- Cierra las ventanas falsas de `osascript` que piden tu contraseña, el truco típico de los stealers de Mac (Atomic/AMOS).

**Rendimiento y batería**
- Si una app en segundo plano pasa 45 minutos por encima del 80 % de CPU, o la memoria está casi agotada, **te pregunta con una ventana** si quieres cerrarla. Si no respondes en 60 segundos, no la cierra. Si eliges *Dejarla*, no vuelve a preguntarte por esa app (se apunta en `/var/db/macguardian/ignoradas.txt`).
- Activa el modo de bajo consumo con la batería al 20 % o menos, y lo quita al cargar.
- Libera instantáneas de Time Machine si el disco se llena y vacía la caché DNS.

**Limpieza**
- Borra cachés de más de 7 días, logs e informes de fallos viejos, la Papelera de más de 30 días, descargas incompletas, enlaces rotos y versiones antiguas de Homebrew.

## Lo que hace con cuidado (y por qué)

- **Nunca cierra nada sin preguntarte.** Tampoco pregunta por las apps de la lista `PROTECTED_APPS`: juegos (World of Warcraft, Battle.net, Steam…), Discord, OrbStack, Terminal, VS Code, Burp, máquinas virtuales… Si quieres que no pregunte nunca, pon `ASK_BEFORE_QUIT=0`.
- **La cuarentena no borra nada.** Mueve los archivos a `/var/db/macguardian/cuarentena/` y anota el origen en `registro.txt`. Para recuperar uno: `sudo mv <destino> <origen>`. Se vacía a los 60 días.
- En la **primera ejecución** solo pone en cuarentena lo claramente malicioso. A partir de la segunda, también lo nuevo y sin firma: así no se carga programas que ya tenías y funcionaban.
- **Nunca toca** tus documentos ni Descargas, ni nada de `/System`.

## Lo que no se puede automatizar (te avisa)

- Activar **FileVault**, la contraseña al bloquear la pantalla o reactivar SIP: exigen tu contraseña o el modo recuperación.
- **Quitar extensiones del navegador**: te marca las peligrosas para que decidas tú.
- **Drivers de terceros**: se actualizan desde la app de su fabricante. El script los lista.
- **Reinicios**: con `AUTO_RESTART=0` solo te avisa, porque un reinicio forzado pierde lo que no hayas guardado. Si lo pones a `1`, reinicia a las 04:00 cuando haga falta.

## Personalizar

Todo se configura en el bloque del principio de `mac-guardian.sh`, con cada acción a `1` o `0`. Después, vuelve a ejecutar `sudo ./install.sh`.

Ajustes a tener en cuenta:
- Usas SSH o Compartir pantalla → `FIX_REMOTE=0`.
- Quieres que restaure `/etc/hosts` → `FIX_HOSTS=1`. Está a `0` porque en los labs y CTF se añaden entradas a mano.

## Acceso total al disco (opcional)

Sin él, el script se salta los permisos TCC, la Papelera, los elementos de inicio y Safari. Para la tarea automática habría que dárselo a `/bin/bash`, lo que lo concede a **cualquier** script bash. Es un compromiso de seguridad que tienes que decidir tú.

## Complementos recomendados (gratis, de Objective-See)

- **LuLu**: firewall de salida.
- **BlockBlock**: avisa en el momento en que algo se instala para arrancar solo.
- **KnockKnock**: revisión manual de persistencia.

Desinstalar: `sudo ./install.sh --uninstall`
