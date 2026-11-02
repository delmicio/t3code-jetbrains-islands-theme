# JetBrains Islands theme for T3 Code

A [T3 Code](https://github.com/pingdotgg/t3code) theme that reproduces **Islands Dark** and **Islands Light**, the default UI themes of JetBrains IDEs since 2025.x.

One theme file holds both versions. T3 Code switches between light and dark with your appearance mode, the same way it does for its built-in themes.

*Versión en español [abajo](#español).*

## Install

### Option 1: CLI (one line)

```sh
curl -fsSL https://raw.githubusercontent.com/delmicio/t3code-jetbrains-islands-theme/main/jetbrains-islands.json -o /tmp/jetbrains-islands.json && ~/.t3/bin/t3 theme set /tmp/jetbrains-islands.json
```

`t3 theme set <path>` publishes the file into `~/.t3/userdata/themes/` and selects it, and connected clients switch to it. To go back, run `t3 theme clear`.

### Option 2: Settings UI

1. Download [`jetbrains-islands.json`](jetbrains-islands.json).
2. In T3 Code, open **Settings → Appearance → Add a theme**.
3. Choose the file, or paste its contents into the Theme JSON box.

## Palette

The colors are taken from the official JetBrains sources in [JetBrains/intellij-community](https://github.com/JetBrains/intellij-community/tree/master/platform/platform-resources/src/themes/islands): `ManyIslandsDark.theme.json`, `ManyIslandsLight.theme.json` and the `IslandSchemeDark.xml` editor scheme.

| Role | Dark | Light |
| --- | --- | --- |
| Window frame / toolbar | `#26282C` | `#E9EAEE` |
| Islands (chat, sidebar, terminal) | `#191A1C` | `#FFFFFF` |
| Inline panels | `#212326` | `#F7F8F9` |
| Popups / raised panels | `#26282C` | `#FFFFFF` |
| Text | `#D1D3D9` | `#000000` |
| Muted text | `#9FA2A8` | `#5F6269` |
| Accent / focus | `#3871E1` | `#3871E1` |
| Selected row | `#2A4371` | `#D0DFFE` |
| Code blocks | `#2B2D30` | `#F7F8F9` |

JetBrains defines hover states as translucent overlays. T3 Code needs solid colors, so those were flattened onto their backgrounds. For example, `#FFFFFF17` over `#26282C` becomes `#3A3B3F`.

## Limitations

- **Syntax highlighting is not included.** The current T3 Code build always highlights code with its built-in `pierre-dark` / `pierre-light` themes, and themes can only change UI colors. When importing a VS Code theme, T3 Code also drops its `tokenColors`. If T3 Code adds custom code themes later, the Islands Dark token colors are in `IslandSchemeDark.xml`: keywords `#CF8E6D`, strings `#6AAB73`, numbers `#2AACB8`, functions `#56A8F5`, fields `#C77DBB`, comments `#7A7E85`.
- **Some colors are approximations.** The Islands folder has no light editor scheme, so two light colors don't come from an official file. The light terminal selection (`#A6D2FF`) is the classic IntelliJ Light value, and the active search match (`#F4CD9A`) was picked to fit the palette.
- **No rounded island shapes.** T3 Code themes set colors only. You get the frame/island contrast, but not the rounded corners.

## License

Apache-2.0, the same license as the intellij-community sources the colors come from. See [LICENSE](LICENSE) and [NOTICE](NOTICE).

This project is not affiliated with or endorsed by JetBrains. "JetBrains", "IntelliJ" and "Islands" are trademarks of their respective owners.

---

## Español

Theme para [T3 Code](https://github.com/pingdotgg/t3code) que reproduce **Islands Dark** e **Islands Light**, los themes por defecto de los IDEs de JetBrains desde la versión 2025.x. Un solo archivo trae las dos versiones, y T3 Code cambia entre light y dark según tu modo de apariencia, igual que con sus themes integrados.

### Instalación

**Por CLI:**

```sh
curl -fsSL https://raw.githubusercontent.com/delmicio/t3code-jetbrains-islands-theme/main/jetbrains-islands.json -o /tmp/jetbrains-islands.json && ~/.t3/bin/t3 theme set /tmp/jetbrains-islands.json
```

Para volver al theme anterior: `t3 theme clear`.

**Desde la app:** descarga [`jetbrains-islands.json`](jetbrains-islands.json), ve a **Settings → Appearance → Add a theme** y elige el archivo o pega su contenido.

### Limitaciones

- **No incluye syntax highlighting.** T3 Code usa sus propios themes de código (`pierre-dark` / `pierre-light`), y los themes solo cambian los colores de la interfaz.
- **Dos colores de la versión light son aproximados:** la selección de la terminal y el match activo de búsqueda.
- **Sin bordes redondeados.** Los themes de T3 Code solo cambian colores, así que no hay esquinas redondeadas en las islas.
