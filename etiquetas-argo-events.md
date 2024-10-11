. Etiquetas más usadas en archivos YAML de Argo Events
Aquí tienes un listado de las etiquetas más comunes y sus funciones:

apiVersion: Define la versión de la API del recurso (p. ej., argoproj.io/v1alpha1).
kind: Especifica el tipo de recurso. Algunos ejemplos comunes son EventSource, Sensor, EventBus.
metadata: Proporciona metadatos sobre el recurso.
name: Nombre del recurso.
namespace: Namespace en el que reside el recurso.
labels: Etiquetas clave-valor para clasificar y seleccionar recursos.
annotations: Metadatos adicionales usados por otras herramientas.
spec: Define la especificación del recurso, es decir, su configuración principal.
serviceAccountName: Nombre de la cuenta de servicio que el recurso usará.
eventBusName: Nombre del EventBus asociado (en los sensores y EventSource).
eventSourceName: Nombre de la fuente de eventos (en los sensores).
triggers: Especifica qué acciones se deben ejecutar cuando se detecta un evento (en los sensores).
dependencies: Lista de dependencias o eventos que se esperan para activar un sensor.
nats: Configuración del backend de mensajería NATS (en EventBus).
auth: Define el tipo de autenticación usado (por ejemplo, none, token).
template: Configura los templates de recursos en Kubernetes.
containers: Configuración de los contenedores que se ejecutarán en los pods creados como respuesta a los eventos.
volumes: Configura volúmenes para los pods.
restartPolicy: Política de reinicio de los pods creados (p. ej., Never o OnFailure).
2. Tipos de Kind en Argo Events
En Argo Events, los tipos de Kind más importantes son:

EventSource: Es el recurso que define una fuente de eventos (cron, webhook, archivo, etc.).
Sensor: Escucha eventos de un EventSource y ejecuta una acción en respuesta (p. ej., crear un pod, ejecutar un comando).
EventBus: Es el backend de mensajería que transporta los eventos entre los EventSource y los Sensor.
EventListener: Permite escuchar y procesar eventos en tiempo real.
Además de estos tres fundamentales, hay recursos relacionados en la infraestructura de Argo Events, como controladores o componentes internos, pero los tres más utilizados en la práctica son EventSource, Sensor y EventBus.

3. Tipos de EventSource
En Argo Events, existen varios tipos de EventSource (fuentes de eventos), que permiten disparar acciones basadas en diferentes entradas de eventos. Aquí está una lista de los más usados:

Cron: Lanza eventos en intervalos de tiempo regulares según una expresión cron.
Webhook: Captura eventos a través de una solicitud HTTP entrante.
Kafka: Captura eventos desde un flujo Kafka.
NATS: Lanza eventos desde el sistema de mensajería NATS.
AMQP: Captura eventos desde un broker de mensajes compatible con AMQP.
MQTT: Captura eventos desde un broker de mensajes MQTT.
File: Monitorea cambios en archivos locales.
Resource: Detecta cambios en los recursos de Kubernetes.
Calendar: Dispara eventos basados en fechas y tiempos específicos.
SNS/SQS (Amazon Web Services): Captura eventos desde los servicios de mensajería de AWS.
GCP PubSub: Captura eventos desde el servicio Pub/Sub de Google Cloud Platform.
GitHub: Captura eventos desde GitHub (por ejemplo, push de un repositorio).
Slack: Captura eventos desde Slack.
HTTP: Lanza eventos basados en solicitudes HTTP.
Estos son solo algunos de los EventSource soportados. Existen muchas otras integraciones dependiendo del backend o la fuente de eventos que se necesite monitorizar.
