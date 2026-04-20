---
name: web-security-expert
description: Escanea, analiza y aplica metodologías de seguridad para proteger aplicaciones web y landing pages contra vulnerabilidades y robo de código (anti-scraping, obfuscation, headers).
---

# Web Security & Code Protection Skill

Este skill permite a Antigravity actuar como un experto en ciberseguridad enfocado en la protección de activos web frontend y backend. Proporciona metodologías para blindar el código fuente, prevenir el scraping y mitigar vulnerabilidades comunes.

## Instrucciones para el Agente

Cuando este skill esté activo, debes seguir estas directrices:

1.  **Análisis de Vulnerabilidades**:
    *   Revisa el código en busca de fallos comunes de OWASP (XSS, CSRF, Inyecciones, etc.).
    *   Verifica la configuración de cabeceras de seguridad.
2.  **Protección de Código (Anti-Theft)**:
    *   Sugiere e implementa técnicas de ofuscación de JavaScript.
    *   Aplica medidas contra el "right-click" y la inspección básica (con la advertencia de que nada es 100% infalible).
    *   Implementa lógica de detección de bots y anti-scraping.
3.  **Seguridad de Infraestructura**:
    *   Configura `Content-Security-Policy` (CSP) estrictos.
    *   Asegura que los formularios tengan validación tanto en cliente como en servidor.
4.  **Auditoría**:
    *   Genera reportes de hallazgos y pasos prioritarios para la mitigación.

## Cuándo usar este skill

*   Cuando el usuario pida proteger su código contra copia o robo.
*   Cuando se necesite auditar la seguridad de una landing page o aplicación.
*   Al implementar formularios que manejan datos sensibles.
*   Cuando se requiera configurar cabeceras de seguridad en servidores de producción.

## Cómo usarlo

1.  **Escaneo**: Solicita acceso a los archivos del proyecto o URLs públicas para analizar cabeceras y estructuras.
2.  **Diagnóstico**: Identifica puntos críticos (ej. scripts sin ofuscar, falta de CSP).
3.  **Implementación**:
    *   Genera archivos de configuración (ej. `.htaccess`, `nginx.conf`, middleware de seguridad).
    *   Integra librerías de ofuscación en el flujo de build.
    *   Añade scripts de protección dinámica.
4.  **Verificación**: Recomienda herramientas externas o pruebas manuales para confirmar la protección.

## Metodologías de Seguridad Incluidas

### 1. Protección de Frontend (Anti-Code Theft)
*   **Ofuscación Progresiva**: Uso de `javascript-obfuscator` con configuraciones de control de flujo y strings ocultos.
*   **Domain Locking**: Bloqueo del script para que solo funcione en dominios autorizados.
*   **Integrity Checks**: Uso de Subresource Integrity (SRI) para recursos externos.

### 2. Blindaje de Comunicación
*   **Secure Headers**:
    *   `Strict-Transport-Security` (HSTS)
    *   `X-Content-Type-Options: nosniff`
    *   `X-Frame-Options: DENY/SAMEORIGIN`
    *   `Referrer-Policy: strict-origin-when-cross-origin`
*   **Cifrado de Payload**: Metodologías para cifrar datos enviados vía AJAX/Fetch.

### 3. Mitigación de Vulnerabilidades
*   **Sanitización de Entradas**: Implementación de políticas de limpieza para evitar XSS.
*   **Tokens de Seguridad**: Uso de nonces en CSP y tokens CSRF.
