# SpawnRatePlugin_relase.zip
Plugin para terraria tshock en español 
# SpawnRatePlugin para TShock

Plugin que permite controlar la velocidad de aparición de enemigos en tu servidor de Terraria con TShock.

---

## Comandos disponibles

| Comando | Alias | Descripción |
|---|---|---|
| `/spawnrate <valor>` | `/sr <valor>` | Cambia la velocidad de aparición. **Menor valor = más rápido.** (defecto: 600) |
| `/maxspawns <valor>` | `/ms <valor>` | Cambia el máximo de enemigos en pantalla al mismo tiempo. (defecto: 5) |
| `/spawnreset` | — | Restablece ambos valores al defecto. |
| `/spawninfo` | — | Muestra los valores actuales. |

### Ejemplos de uso

```
/spawnrate 100     → Enemigos aparecen 6 veces más rápido que lo normal
/spawnrate 300     → Aparición moderadamente más rápida
/maxspawns 20      → Hasta 20 enemigos en pantalla a la vez
/spawnreset        → Vuelve a los valores originales
```

---

## Permisos

Los comandos requieren el permiso `spawnrate.set`.  
Asígnalo en TShock así:

```
/group addperm superadmin spawnrate.set
```

---

## Instalación

### Paso 1 — Obtener los archivos DLL de TShock

Copia los siguientes archivos desde la carpeta de instalación de tu TShock a la carpeta `lib/` de este proyecto:

- `TShockAPI.dll`
- `TerrariaServer.dll`
- `TerrariaApi.Server.dll`
- `Newtonsoft.Json.dll`

### Paso 2 — Compilar el plugin

Necesitas tener instalado el [.NET 6 SDK](https://dotnet.microsoft.com/download/dotnet/6.0).

```bash
dotnet build SpawnRatePlugin.csproj -c Release
```

El archivo compilado estará en:
```
bin/Release/net6.0/SpawnRatePlugin.dll
```

### Paso 3 — Instalar en el servidor

Copia `SpawnRatePlugin.dll` a la carpeta `ServerPlugins/` de tu TShock y reinicia el servidor.

---

## Configuración

Al iniciar el servidor por primera vez, se creará automáticamente el archivo:

```
tshock/SpawnRatePlugin.json
```

Puedes editarlo manualmente:

```json
{
  "SpawnRate": 600,
  "MaxSpawns": 5
}
```

Los cambios en el archivo se aplican en el siguiente reinicio del servidor (o usa los comandos en vivo).