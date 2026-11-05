# bootdump — canal de actualizaciones

Este repositorio es **solo el canal de distribución** de la app **bootdump**
(extrae `boot.img`, `init_boot.img` y `vendor_boot.img` de POCO / HyperOS 3).

Aquí no hay código fuente: el desarrollo es privado. Este espejo público existe
únicamente para que la app pueda consultar si hay una versión nueva e instalarla
sin credenciales.

## Contenido

| Archivo | Para qué sirve |
| --- | --- |
| `version.json` | Manifiesto que consulta la app al pulsar **Buscar actualizaciones** |
| `bootdump.apk` | Última versión publicada, firmada con la clave de la app |

`version.json` tiene este formato:

```json
{
  "versionCode": 13,
  "versionName": "1.13",
  "apkUrl": "https://raw.githubusercontent.com/guian17/bootdump-updates/main/bootdump.apk?v=13",
  "sha256": "<hash del apk>",
  "notes": "resumen del cambio"
}
```

La app descarga el APK, comprueba que su **SHA-256** coincide con el publicado y
solo entonces abre el instalador del sistema. Si la comprobación falla, no se
instala nada.

## Instalación manual

Si prefieres no esperar a la actualización automática, descarga
[`bootdump.apk`](https://raw.githubusercontent.com/guian17/bootdump-updates/main/bootdump.apk)
y ábrelo en el teléfono (hay que permitir «instalar apps desconocidas» para el
navegador o el gestor de archivos que uses).

## Actualizaciones

Este repositorio se reescribe automáticamente en cada compilación: no se aceptan
pull requests ni issues. Cada publicación sustituye el contenido anterior, así que
no se conserva historial de versiones antiguas.
