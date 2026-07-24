# 🤖 Sistema de Screening Automático de Candidatos (Human-in-the-Loop)

Sistema de automatización desarrollado en **n8n** para procesar postulaciones laborales, evaluar candidatos utilizando **OpenAI**, gestionar la base de datos en **Airtable** y solicitar validación humana antes de notificar los resultados.

---

## 📹 Video Demostrativo

🎥 **[Hacé clic acá para ver la demostración en Google Drive](https://drive.google.com/file/d/1utp0wL5ULPiQgxFLJsbNOp3RcMIFL87u/view?usp=sharing)**

## 🗄️ Base de Datos (Airtable)
🔗 [Hacé clic acá para ver la base de datos](https://airtable.com/invite/l?inviteId=invu292R2l4DBEVgM&inviteToken=481242b4fb761bbc79f12f726eca8fc0fe5101f6c1609c2f090f70b6c58d54fa&utm_medium=email&utm_source=product_team&utm_content=transactional-alerts)

📄 **[Ver Diagrama de Arquitectura (PDF)](./Diagrama_Arquitectura_1.pdf)**

---

## 🚀 Arquitectura del Workflow

El sistema se divide en dos módulos principales:

1. **Ingesta de Candidatos:**
   * Recepción de correos vía **Gmail Trigger**.
   * Extracción automática del texto del CV en formato PDF.
   * Matcheo con vacantes activas y guardado del candidato en **Airtable**.

2. **Evaluación e Integración de IA (HITL):**
   * Procesamiento del perfil anonimizado mediante **OpenAI (GPT-4o)**.
   * Parseo estructurado de respuestas en JSON y asignación de puntaje.
   * Notificación al reclutador vía email con botones de aprobación/rechazo (**Human-in-the-Loop**).
   * Actualización del estado final y registro de cada paso en la tabla de **Auditoría**.

---

## 🛠️ Tecnologías Utilizadas

* **n8n** (Orquestación del flujo)
* **OpenAI API** (Evaluación de perfiles)
* **Airtable** (Base de datos relacional y logs)
* **Gmail / OAuth 2.0** (Disparador y envíos de correo)

---

## 📥 Cómo importar este flujo

1. Descargá el archivo JSON del flujo guardado en este repositorio.
2. En tu instancia de **n8n**, seleccioná **Import from File**.
3. Configurá las credenciales de OpenAI, Airtable y Gmail.
