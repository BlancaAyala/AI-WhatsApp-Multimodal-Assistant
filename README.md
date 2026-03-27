🧠 AI WhatsApp Multimodal Assistant

n8n • WhatsApp API • Google Gemini • Multimodal AI


📖 Overview

Este proyecto implementa un asistente conversacional inteligente para WhatsApp capaz de procesar múltiples tipos de mensajes (texto, imágenes, documentos y audio) y responder automáticamente utilizando inteligencia artificial.
El sistema está diseñado como una solución escalable para automatizar la comunicación con clientes, permitiendo interpretar distintos formatos de entrada y generar respuestas contextualizadas.
El workflow está desarrollado en n8n, actuando como orquestador entre la API de WhatsApp y los servicios de IA.


🚀 Features

Procesamiento de mensajes de texto
Análisis de imágenes mediante IA
Procesamiento de documentos
Transcripción automática de audio (speech-to-text)
Memoria conversacional
Respuestas automáticas en texto
Respuestas en audio (text-to-speech)
Arquitectura modular y escalable


🏗️ System Architecture

User (WhatsApp)
      ↓
WhatsApp API
      ↓
n8n Workflow
      ↓
Message Type Router (Switch)
      ↓
Processing Layer:
  - Text Processing
  - Image Analysis
  - Document Processing
  - Audio Transcription
      ↓
Data Normalization
      ↓
AI Agent (Google Gemini)
      ↓
Response Generator
      ↓
Text / Audio Output
      ↓
WhatsApp Response


⚙️ Workflow Explanation

1. WhatsApp Trigger
El flujo comienza con la recepción de mensajes mediante un trigger de WhatsApp, que captura eventos entrantes de los usuarios.
2. Message Classification
Se utiliza un nodo Switch para identificar el tipo de mensaje:
texto
imagen
documento
audio
Cada tipo sigue un flujo de procesamiento específico.
3. Text Processing
Los mensajes de texto se procesan directamente extrayendo el contenido y los metadatos del usuario.
4. Image Processing
Descarga de la imagen desde la API de WhatsApp
Procesamiento mediante modelo de visión
Generación de descripción del contenido
5. Document Processing
Descarga del documento
Análisis del contenido
Extracción de información relevante
6. Audio Processing
Descarga del audio
Transcripción mediante speech-to-text
Conversión a texto procesable
7. Data Normalization
Todos los inputs se transforman en una estructura común:
{
  "user_id": "string",
  "message_type": "text | image | document | audio",
  "content": "string",
  "context": "optional"
}
8. AI Agent
El agente de IA (Google Gemini):
interpreta el mensaje
utiliza memoria conversacional
genera una respuesta contextual
9. Response Handling
Si es texto → respuesta en texto
Si es audio → conversión a voz (TTS)
🛠️ Technologies Used
n8n — automatización de workflows
WhatsApp Business API — mensajería
Google Gemini — procesamiento de lenguaje
Speech-to-Text API — transcripción de audio
Text-to-Speech — generación de audio
HTTP APIs — integración de servicios


▶️ Setup & Installation

Requisitos
Instancia de n8n (self-hosted o cloud)
Acceso a WhatsApp Business API
API Key de Google Gemini
Servicio de speech-to-text (opcional)
Servicio de text-to-speech (opcional)
Pasos
1. Importar el workflow en n8n
2. Configurar credenciales de WhatsApp API
3. Configurar credenciales de Google Gemini
4. Configurar endpoints HTTP necesarios
5. Activar el workflow

   
📌 Use Cases

Atención al cliente automatizada
Soporte técnico mediante WhatsApp
Asistentes conversacionales multimodales
Procesamiento de incidencias (imagen/audio)
Automatización de consultas frecuentes


📈 Future Improvements

Integración con base de datos (usuarios y conversaciones)
Implementación de RAG con base vectorial
Sistema de logging y monitorización
Clasificador de intención avanzado
Integración con CRM
Soporte multi-idioma


🧩 Key Highlights

Este proyecto demuestra:
Diseño de arquitecturas multimodales
Integración de IA en workflows reales
Procesamiento de múltiples tipos de input
Orquestación de servicios mediante n8n
Aplicación práctica en entornos empresariales


📄 License

Uso educativo y demostrativo. Adaptable a entornos empresariales.
