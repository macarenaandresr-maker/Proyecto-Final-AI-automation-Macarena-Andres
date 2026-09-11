# Proyecto Final — Ecosistema de Automatización con IA

**UrbanStep · Clasificación y Respuesta Automatizada de Leads Comerciales**
Por: Macarena Andrés

---

## Descripción

Sistema autónomo que recibe consultas comerciales por correo, las interpreta
con inteligencia artificial, clasifica el lead, recomienda un producto real
del catálogo y redacta una respuesta personalizada. Ninguna respuesta se envía
sin validación humana previa.

**Stack:** n8n · OpenAI GPT-4o-mini · Airtable · Gmail · Telegram

---

## Enlaces de la entrega

| Recurso | Enlace |
|---|---|
| 📊 Dashboard de Control Ejecutivo | https://airtable.com/appOLmEstMzIwN4lS/shrhbQJBeQXrcQ1BM |
| 🗄️ Base de datos (modo lectura) | https://airtable.com/appOLmEstMzIwN4lS/shrl4XiLHc2YrMzzO |
| 🎥 Video demostrativo (3 min) | *(pegar enlace)* |

---

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `UrbanStep_Entrega_Final.pdf` | Documento principal: arquitectura, manual de datos, matriz de costos, seguridad y resiliencia |
| `Diagrama_Arquitectura_UrbanStep.pdf` | Mapa de arquitectura del sistema |
| `workflow.json` | Flujo de n8n exportado (sin credenciales) |
| `screenshots_UrbanStep_AI/` | Evidencias del test de estrés |

---

## Arquitectura

Gmail (trigger filtrado) → Airtable (registro) → Router de validación →
Catálogo → GPT-4o-mini → Telegram (validación humana) → Router de decisión →
Gmail Reply en hilo / Registro de rechazo

**17 nodos · 19 conexiones · 3 sub-flujos · 4 rutas de contingencia**

---

## Criterios cubiertos

- **Mapa de arquitectura** — diagrama con triggers, routers, APIs, nodos de IA y destino de datos
- **Estructuras de datos** — 3 tablas vinculadas + 9 esquemas JSON de transferencia
- **Optimización de costos** — cuadro comparativo, matriz de decisión, Message Batches y Prompt Caching
- **Seguridad y resiliencia** — minimización de datos, Error Handlers y Human-in-the-loop
- **Dashboard de control** — vista pública con KPIs y tasa de error

---

## Nota de seguridad

El archivo `workflow.json` se exporta sin credenciales: contiene únicamente
referencias a las credenciales almacenadas en el gestor de n8n. Las claves
de API residen cifradas en la plataforma y no se incluyen en este repositorio.
