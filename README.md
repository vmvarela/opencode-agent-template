# OpenCode Agent Template 🤖

Repositorio plantilla para desplegar rápidamente **agentes de IA modulares, portables y basados en la arquitectura de OpenCode v2**.

Este marco de trabajo utiliza un enfoque de **navegación selectiva bajo demanda** y administración de archivos en Markdown para dotar a la IA de un "cerebro" estructurado (contexto, habilidades, memoria y espacio de trabajo) sin saturar la ventana de contexto.

---

## 📁 Estructura del Repositorio

```text
.
├── AGENTS.md                  # Manual orquestador principal (reglas, rol y flujos)
├── README.md                  # Guía de uso de la plantilla
├── .gitignore                 # Aislamiento para proyectos anidados (projects/*)
├── .opencode/
│   └── opencode.json          # Configuración oficial de OpenCode v2 (MCPs, permisos, agentes)
├── .agents/
│   └── skills/                # Habilidades y recetas paso a paso del agente
├── context/                   # Normas, estándares y políticas estáticas
├── memory/                    # Registro dinámico de aprendizajes y lecciones
└── projects/                  # Repositorios o proyectos anidados aislados
```

---

## 🚀 Cómo usar esta plantilla

### 1. Crear un nuevo repositorio desde el Template
1. En GitHub, haz clic en el botón **"Use this template"** > **"Create a new repository"**.
2. Nombra tu nuevo repositorio (ej. `prisamedia`, `opensource`, `health`).
3. Clona el nuevo repositorio en tu máquina local:
   ```bash
   git clone https://github.com/tu-usuario/nombre-del-agente.git
   cd nombre-del-agente
   ```

### 2. Configurar la identidad del Agente
Abre el archivo **`AGENTS.md`** y edita la **Sección 1 (Rol e Identidad)** asignando el propósito específico de tu agente:
* **Rol**: Ej. *Copiloto DevOps en Hiberus para PrisaMedia*.
* **Misión**: Ej. *Gestionar la gobernanza de GitHub, pipelines de CI/CD y plantillas en Backstage*.

### 3. Poblar las subcarpetas
* **`context/`**: Añade normativas estáticas, políticas de seguridad, guías de estilo o requerimientos del cliente.
* **`.agents/skills/`**: Añade recetas paso a paso para procedimientos habituales que deba ejecutar la IA.
* **`memory/`**: Permite que el agente autoregistre correcciones o excepciones aprendidas durante el uso.
* **`projects/`**: Haz `git clone` de los repositorios de código sobre los que trabajará el agente (esta carpeta está ignorada en `.gitignore` para no crear anidamientos de Git).

---

## ⚙️ Configuración con OpenCode v2

El archivo **`.opencode/opencode.json`** incluye la configuración predeterminada para **OpenCode v2**:
* **Reglas de seguridad y permisos**: Permisos de lectura (`allow`), confirmación humana (`ask`) para ediciones/commits y prohibición (`deny`) de acciones destructivas.
* **Modelos y subagentes**: Asignación de modelos para razonamiento (`plan`), ejecución (`build`) o títulos (`title`).
* **Servidores MCP**: Plantilla lista para habilitar conectores MCP (ej. GitHub, Playwright, etc.).

---

## 🔄 Flujo de Trabajo y Automejora

1. **Abre OpenCode** en la raíz del repositorio.
2. **Interactúa con el agente**: La IA leerá automáticamente el `AGENTS.md` e irá únicamente a los archivos de `context/`, `.agents/skills/` o `memory/` que necesite para responder.
3. **Aplica correcciones**: Si corriges a la IA en una respuesta, el agente registrará la lección en `memory/` para no repetir el error en el futuro.
