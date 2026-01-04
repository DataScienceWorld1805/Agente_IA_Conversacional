# 🤖 Agente de IA Conversacional con LangChain

Un agente de inteligencia artificial conversacional desarrollado con **LangChain** y **Groq**, que incluye una interfaz gráfica moderna tipo ChatGPT y capacidades de exportación de conversaciones en múltiples formatos.

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación](#-instalación)
- [Configuración](#-configuración)
- [Uso](#-uso)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Funcionalidades Detalladas](#-funcionalidades-detalladas)
- [Personalización](#-personalización)
- [Solución de Problemas](#-solución-de-problemas)
- [Arquitectura del Sistema](#-arquitectura-del-sistema)
- [Contribuciones](#-contribuciones)
- [Licencia](#-licencia)

## ✨ Características

- **🤖 Agente Conversacional Inteligente**: Utiliza modelos de lenguaje avanzados (Llama 3.1) a través de Groq API
- **💬 Interfaz Gráfica Moderna**: Interfaz tipo ChatGPT desarrollada con Gradio 6.2+
- **🧠 Memoria de Conversación**: Mantiene el contexto de la conversación durante toda la sesión usando `ConversationBufferMemory`
- **📥 Exportación Multi-formato**: Descarga conversaciones en TXT, Markdown, PDF y DOCX con formato profesional
- **⚙️ Configuración Flexible**: Ajuste de temperatura y selección de modelos según necesidades
- **🔌 Detección Automática de Puertos**: Encuentra automáticamente puertos disponibles (7860-7869)
- **🎨 Interfaz Personalizada**: CSS personalizado para una experiencia visual mejorada
- **🔒 Seguridad**: Gestión segura de API keys mediante variables de entorno (.env)
- **🔄 Compatibilidad**: Soporte para múltiples versiones de LangChain con fallbacks automáticos

## 🛠 Tecnologías Utilizadas

| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| **LangChain** | 1.2.0+ | Framework para construir aplicaciones con modelos de lenguaje |
| **LangChain Classic** | 1.0.1+ | Módulos legacy (ConversationChain, ConversationBufferMemory) |
| **Groq API** | 1.1.1+ | API para acceder a modelos de IA de alto rendimiento (Llama 3.1) |
| **Gradio** | 6.2.0+ | Framework para crear interfaces web interactivas |
| **ReportLab** | 4.4.7+ | Generación de documentos PDF |
| **python-docx** | 1.2.0+ | Creación de documentos Word (DOCX) |
| **python-dotenv** | 1.2.1+ | Gestión segura de variables de entorno |
| **Python** | 3.11+ | Lenguaje de programación base |

## 📦 Requisitos Previos

- **Python 3.11 o superior**
- **Jupyter Notebook** o **JupyterLab**
- **API Key de Groq** (obtén una gratis en [console.groq.com](https://console.groq.com))
- **Conexión a Internet** (para acceder a la API de Groq)

## 🚀 Instalación

### Paso 1: Clonar o Descargar el Proyecto

```bash
git clone <tu-repositorio>
cd Agente_IA
```

O descarga los archivos del proyecto manualmente.

### Paso 2: Abrir el Notebook

```bash
jupyter notebook agente_ia_langchain.ipynb
```

O desde JupyterLab:

```bash
jupyter lab agente_ia_langchain.ipynb
```

### Paso 3: Instalar Dependencias

Ejecuta la **primera celda** del notebook (Cell 1), que instalará automáticamente todas las dependencias necesarias:

- `langchain` y módulos relacionados
- `langchain-classic` (para ConversationChain y ConversationBufferMemory)
- `langchain-groq` (integración con Groq)
- `gradio` (interfaz web)
- `reportlab` (generación de PDFs)
- `python-docx` (generación de documentos Word)
- `python-dotenv` (gestión de variables de entorno)

**Nota:** Si alguna dependencia ya está instalada, el sistema la actualizará automáticamente.

## ⚙️ Configuración

### Configuración de la API Key

El proyecto utiliza variables de entorno para gestionar de forma segura la API key de Groq.

#### Opción 1: Archivo .env (Recomendado)

1. **Crea un archivo llamado `.env`** en la raíz del proyecto (mismo directorio que el notebook)

2. **Agrega tu API Key** en el archivo con el siguiente formato:

```env
GROQ_API_KEY=tu_api_key_de_groq_aqui
```

**Ejemplo:**
```env
GROQ_API_KEY=gsk_1234567890abcdefghijklmnopqrstuvwxyz
```

3. **Verifica la configuración**: Ejecuta la celda que carga la API Key (Cell 3). Deberías ver:
   ```
   ✓ API Key cargada correctamente desde .env
   ```

#### Opción 2: Variables de Entorno del Sistema

También puedes configurar la variable de entorno directamente en tu sistema:

**Windows (PowerShell):**
```powershell
$env:GROQ_API_KEY="tu_api_key_aqui"
```

**Linux/Mac:**
```bash
export GROQ_API_KEY="tu_api_key_aqui"
```

⚠️ **IMPORTANTE - Seguridad:**
- El archivo `.env` contiene información sensible
- **Nunca subas el archivo `.env` al repositorio** (ya está en `.gitignore`)
- No compartas tu API key públicamente
- Si necesitas compartir el proyecto, crea un archivo `.env.example` como plantilla

## 📖 Uso

### Opción 1: Interfaz Gráfica (Recomendado)

1. **Ejecuta todas las celdas** del notebook en orden (Cells 1-7)
2. **La interfaz se abrirá automáticamente** en tu navegador en `http://127.0.0.1:7860` (o el puerto disponible)
3. **Comienza a chatear** escribiendo en el campo de texto y presionando "Enviar" o Enter
4. **Descarga conversaciones** seleccionando el formato (TXT, Markdown, PDF, DOCX) y haciendo clic en "📥 Descargar Conversación"
5. **Limpia la conversación** usando el botón "Limpiar" para reiniciar el contexto

### Opción 2: Modo Consola

Si prefieres interactuar directamente desde el notebook sin interfaz gráfica:

1. Descomenta la celda del modo conversación directo (Cell 9)
2. Ejecuta la celda
3. Escribe tus mensajes directamente en la terminal del notebook
4. Escribe `salir`, `exit`, `quit` o `adios` para terminar

## 📁 Estructura del Proyecto

```
Agente_IA/
│
├── agente_ia_langchain.ipynb    # Notebook principal con todo el código
├── .env                          # Archivo con variables de entorno (NO incluir en git)
├── .env.example                  # Plantilla de ejemplo para .env (opcional)
├── .gitignore                    # Archivos a ignorar en git
├── README.md                     # Este archivo
└── INFORME_TECNICO.md            # Documentación técnica detallada
```

## 🎯 Funcionalidades Detalladas

### 1. Chat Interactivo

- **Conversación en tiempo real** con el agente de IA
- **Mantiene el contexto** de toda la conversación usando `ConversationBufferMemory`
- **Respuestas rápidas** gracias a Groq API (modelo Llama 3.1 optimizado)
- **Manejo robusto de errores** con mensajes informativos al usuario
- **Formato compatible** con Gradio 6.2+ (mensajes estructurados con `role` y `content`)

### 2. Exportación de Conversaciones

Exporta tus conversaciones en **4 formatos profesionales**:

#### 📄 TXT (Texto Plano)
- Formato simple con separadores visuales
- Encabezado con fecha y hora
- Emojis para identificar usuario/agente
- Ideal para lectura rápida

#### 📝 Markdown (.md)
- Formato con encabezados jerárquicos
- Compatible con GitHub/GitLab
- Separadores horizontales
- Fecha destacada
- Ideal para documentación

#### 📑 PDF
- Documento profesional formateado
- Tamaño de página: Letter
- Estilos personalizados:
  - Título: 16pt, negrita
  - Usuario: Azul oscuro (#00008B)
  - Agente: Verde oscuro (#006400)
- Espaciado optimizado
- Ideal para presentaciones y archivos

#### 📘 DOCX (Microsoft Word)
- Documento editable
- Encabezados con niveles
- Colores personalizados:
  - Usuario: RGB(0, 0, 139)
  - Agente: RGB(0, 100, 0)
- Tamaños de fuente: 10pt (fecha), 11pt (contenido)
- Formato profesional listo para edición
- Ideal para documentos corporativos

**Características de Exportación:**
- Generación automática de archivos temporales
- Inclusión de metadatos (fecha/hora)
- Formato consistente entre exportaciones
- Manejo de errores durante la exportación
- Descarga automática al hacer clic en el archivo generado

### 3. Gestión de Memoria

- **Memoria persistente** durante toda la sesión activa
- **Contexto completo** de la conversación disponible para el agente
- **Referencias a mensajes anteriores** permitidas
- **Reinicio manual** mediante botón "Limpiar"
- **Persistencia durante la sesión** activa de Jupyter

**Nota:** La memoria se reinicia al reiniciar el kernel de Jupyter.

### 4. Detección Automática de Puertos

- **Búsqueda automática** de puertos libres (7860-7869)
- **Evita conflictos** con otras instancias de Gradio
- **Fallback automático** si no encuentra puerto en el rango
- **Feedback visual** del puerto utilizado

### 5. Compatibilidad y Robustez

- **Manejo de importaciones** con fallbacks automáticos
- **Compatibilidad** con múltiples versiones de LangChain
- **Instalación automática** de dependencias faltantes
- **Validación de entrada** (mensajes vacíos)
- **Manejo de errores** en todas las funciones críticas

## 🎨 Personalización

### Cambiar el Modelo de IA

En la función `initialize_agent()` (Cell 4), puedes cambiar el modelo:

```python
llm = ChatGroq(
    groq_api_key=os.environ.get("GROQ_API_KEY"),
    model_name="llama-3.1-8b-instant",  # Cambia aquí
    temperature=0.7,
    max_tokens=2048
)
```

**Modelos disponibles en Groq:**

| Modelo | Parámetros | Características | Estado |
|--------|-----------|-----------------|--------|
| `llama-3.1-8b-instant` | 8B | Rápido y eficiente | ✅ Recomendado |
| `llama-3.3-70b-versatile` | 70B | Más potente | ⚠️ Verificar disponibilidad |
| `mixtral-8x7b-32768` | 56B | Contexto largo (32K tokens) | ✅ Disponible |
| `llama-3.1-70b-versatile` | 70B | - | ❌ DESCONTINUADO |

**Nota:** Consulta [console.groq.com/docs/models](https://console.groq.com/docs/models) para ver los modelos disponibles actualmente.

### Ajustar la Temperatura

Controla la creatividad de las respuestas:

- **`temperature=0.0`**: Respuestas deterministas y precisas (ideal para tareas técnicas)
- **`temperature=0.7`**: Balance entre creatividad y precisión (recomendado para conversación general)
- **`temperature=1.0`**: Respuestas más creativas y variadas (ideal para escritura creativa)

**Ejemplo:**
```python
llm = ChatGroq(
    groq_api_key=os.environ.get("GROQ_API_KEY"),
    model_name="llama-3.1-8b-instant",
    temperature=0.5,  # Más conservador
    max_tokens=2048
)
```

### Personalizar el Prompt del Sistema

Modifica el comportamiento del agente editando el `SystemMessagePromptTemplate` en `initialize_agent()`:

```python
SystemMessagePromptTemplate.from_template(
    "Eres un asistente de IA útil, amigable y conversacional. "
    "Responde de manera clara y natural, manteniendo el contexto de la conversación. "
    "Si no sabes algo, admítelo honestamente."
)
```

**Ejemplos de personalización:**

**Asistente Técnico:**
```python
SystemMessagePromptTemplate.from_template(
    "Eres un asistente técnico especializado en programación y tecnología. "
    "Proporciona respuestas precisas, con ejemplos de código cuando sea relevante. "
    "Sé conciso pero completo."
)
```

**Asistente Creativo:**
```python
SystemMessagePromptTemplate.from_template(
    "Eres un asistente creativo y entusiasta. "
    "Ayuda con ideas, brainstorming y proyectos creativos. "
    "Sé inspirador y original en tus respuestas."
)
```

### Ajustar el Límite de Tokens

Controla la longitud máxima de las respuestas:

```python
llm = ChatGroq(
    groq_api_key=os.environ.get("GROQ_API_KEY"),
    model_name="llama-3.1-8b-instant",
    temperature=0.7,
    max_tokens=4096  # Respuestas más largas (máximo según el modelo)
)
```

## 🔧 Solución de Problemas

### Error: "No module named 'langchain.chains'"

**Causa:** Dependencias no instaladas o versión incorrecta de LangChain.

**Solución:**
1. Ejecuta la celda de instalación (Cell 1) nuevamente
2. Reinicia el kernel de Jupyter (Kernel → Restart Kernel)
3. Vuelve a ejecutar todas las celdas en orden

### Error: "Cannot find empty port"

**Causa:** Todos los puertos en el rango 7860-7869 están ocupados.

**Solución:**
1. Cierra otras instancias de Gradio que estén ejecutándose
2. El código buscará automáticamente un puerto libre
3. Si persiste, modifica el rango en `find_free_port()` o deja que Gradio seleccione automáticamente

### Error: "model_decommissioned" o "Model not found"

**Causa:** El modelo especificado está descontinuado o no está disponible.

**Solución:**
1. Cambia a `llama-3.1-8b-instant` (modelo recomendado y estable)
2. Verifica modelos disponibles en [console.groq.com/docs/models](https://console.groq.com/docs/models)
3. Actualiza el `model_name` en `initialize_agent()`

### Error: "No se encontró GROQ_API_KEY en el archivo .env"

**Causa:** El archivo `.env` no existe o no contiene la variable correcta.

**Solución:**
1. Crea un archivo `.env` en la raíz del proyecto
2. Agrega la línea: `GROQ_API_KEY=tu_api_key_aqui`
3. Asegúrate de que el archivo esté en el mismo directorio que el notebook
4. Reinicia el kernel y vuelve a ejecutar la celda de carga (Cell 3)

### La interfaz no se abre en el navegador

**Causa:** Problemas con el puerto, firewall o configuración del navegador.

**Solución:**
1. Verifica que el puerto no esté bloqueado por el firewall
2. Intenta acceder manualmente a `http://127.0.0.1:7860` (o el puerto mostrado en la salida)
3. Verifica que no haya otros servicios usando el puerto
4. Reinicia el kernel y ejecuta todas las celdas nuevamente
5. Si usas `inbrowser=True`, verifica la configuración de tu navegador predeterminado

### Error al exportar PDF/DOCX

**Causa:** Librerías `reportlab` o `python-docx` no instaladas correctamente.

**Solución:**
1. Ejecuta la celda de instalación (Cell 1) nuevamente
2. Verifica que las importaciones funcionen correctamente
3. Si persiste, instala manualmente:
   ```bash
   pip install reportlab python-docx
   ```

### Error: "API rate limit exceeded"

**Causa:** Has excedido el límite de solicitudes de la API de Groq.

**Solución:**
1. Espera unos minutos antes de hacer más solicitudes
2. Verifica tu plan de Groq en [console.groq.com](https://console.groq.com)
3. Considera reducir la frecuencia de solicitudes

### La memoria de conversación se pierde

**Causa:** La memoria solo persiste durante la sesión activa del kernel.

**Solución:**
- Esto es comportamiento esperado. La memoria se reinicia al reiniciar el kernel
- Para persistencia entre sesiones, considera implementar guardado en archivo o base de datos
- Usa la función de exportación para guardar conversaciones importantes

## 🏗 Arquitectura del Sistema

### Diagrama de Arquitectura

```
┌─────────────────────────────────────────────────────────┐
│                    INTERFAZ DE USUARIO                   │
│                    (Gradio Web UI)                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │   Chatbot    │  │  Text Input  │  │   Export     │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              CAPA DE PROCESAMIENTO                      │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │  Chat Handler│  │  Memory Mgmt │  │  Export      │ │
│  │              │  │  (Buffer)    │  │  Functions   │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              CAPA DE ORQUESTACIÓN                        │
│              (LangChain Framework)                      │
│  ┌──────────────────────────────────────────────────┐   │
│  │  ConversationChain + ConversationBufferMemory   │   │
│  │  ChatPromptTemplate + SystemMessagePrompt       │   │
│  └──────────────────────────────────────────────────┘   │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              CAPA DE MODELO DE IA                      │
│              (Groq API - Llama 3.1)                     │
│  ┌──────────────────────────────────────────────────┐   │
│  │  ChatGroq LLM                                   │   │
│  │  - Modelo: llama-3.1-8b-instant                │   │
│  │  - Temperature: 0.7                             │   │
│  │  - Max Tokens: 2048                             │   │
│  └──────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
```

### Flujo de Datos

1. **Usuario escribe mensaje** → Interfaz Gradio
2. **Validación** → Verificación de mensaje no vacío
3. **Procesamiento** → `chat_with_agent()` recibe el mensaje
4. **Orquestación** → `ConversationChain.predict()` agrega contexto histórico
5. **LLM** → `ChatGroq` envía solicitud a Groq API
6. **Respuesta** → Modelo genera respuesta contextual
7. **Actualización** → Memoria y historial se actualizan
8. **Visualización** → Respuesta mostrada en la interfaz

### Componentes Principales

1. **Módulo de Inicialización** (`initialize_agent()`)
   - Configuración del agente
   - Carga de credenciales
   - Creación de memoria y prompt

2. **Módulo de Conversación** (`chat_with_agent()`)
   - Procesamiento de mensajes
   - Gestión de contexto
   - Manejo de errores

3. **Módulo de Interfaz** (`create_chat_interface()`)
   - UI web con Gradio
   - Componentes interactivos
   - Eventos y callbacks

4. **Módulo de Exportación** (`export_to_*()`)
   - Generación de archivos
   - Múltiples formatos
   - Manejo de archivos temporales

5. **Módulo de Utilidades**
   - Gestión de puertos
   - Carga de variables de entorno
   - Funciones auxiliares

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. **Fork** el proyecto
2. **Crea una rama** para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. **Abre un Pull Request**

### Guía de Contribución

- Mantén el código limpio y bien documentado
- Sigue las convenciones de estilo de Python (PEP 8)
- Agrega comentarios para funciones complejas
- Prueba tus cambios antes de hacer commit
- Actualiza la documentación si es necesario

## 📝 Notas Importantes

### Seguridad

- **Nunca subas tu archivo `.env`** al repositorio (ya está en `.gitignore`)
- El archivo `.env` contiene información sensible y debe mantenerse privado
- Usa `.env.example` como referencia para la estructura del archivo
- No compartas tu API key públicamente

### Modelos

- Algunos modelos pueden estar descontinuados. Consulta la documentación oficial de Groq
- El modelo `llama-3.1-70b-versatile` está **DESCONTINUADO** - no usar
- Verifica modelos disponibles en [console.groq.com/docs/models](https://console.groq.com/docs/models)

### Versiones

- Este proyecto usa **LangChain 1.2+** con soporte para `langchain-classic`
- Si tienes problemas, verifica las versiones de las dependencias
- Las versiones se actualizan automáticamente en la celda de instalación

### Variables de Entorno

- El proyecto usa `python-dotenv` para cargar variables de entorno desde `.env`
- Esto sigue las mejores prácticas de seguridad
- También puedes usar variables de entorno del sistema

### Limitaciones

- **Memoria de sesión**: La memoria se pierde al reiniciar el kernel
- **Límites de API**: Sujeto a límites de rate de Groq
- **Conexión**: Requiere conexión a internet para funcionar
- **Exportación**: Archivos temporales (se eliminan automáticamente por el sistema)

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la [MIT License](LICENSE) (o la licencia que prefieras).

## 👤 Autor

**Alonso Martin**
- GitHub: [@DataScienceWorld1805](https://github.com/DataScienceWorld1805)
- Email: datascienceworld1805@gmail.com

## 🙏 Agradecimientos

- [LangChain](https://www.langchain.com/) por el framework de orquestación de LLMs
- [Groq](https://groq.com/) por la API de modelos de IA de alto rendimiento
- [Gradio](https://gradio.app/) por la interfaz gráfica interactiva
- [ReportLab](https://www.reportlab.com/) por la generación de PDFs
- La comunidad de código abierto

## 📚 Recursos Adicionales

- [Documentación de LangChain](https://python.langchain.com/)
- [Documentación de Groq](https://console.groq.com/docs)
- [Documentación de Gradio](https://www.gradio.app/docs/)
- [Modelos disponibles en Groq](https://console.groq.com/docs/models)

---

⭐ Si este proyecto te resultó útil, ¡considera darle una estrella!
