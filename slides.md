---
title: Ciberseguridad + Red Team + Inteligencia Artificial
author: Javier
theme: default
class: lead
notes: Presentación minimalista estilo Feynman
---

<style>
:root {
  --slide-background: #0e1223;
  --text-primary: #e2e8f0;
  --text-secondary: #a0aec0;
  --accent: #67e8f9;
}
section {
  font-family: 'JetBrains Mono', 'Fira Code', Menlo, monospace;
  color: var(--text-primary);
  font-size: 0.85rem; /* Reducido */
}
.slide-content p, li, h1,h2,h3 {
  color: var(--text-primary);
  font-size: 0.85rem; /* Reducido */
}
.slide-content blockquote, .slide-content table {
  color: var(--text-secondary);
  font-size: 0.8rem; /* Reducido */
}
.right-note {
  font-size: 0.7rem; /* Más pequeño */
  line-height: 1.2;
  color: #9ca3af;
  border-left: 2px solid #475569;
  padding-left: 0.8rem;
}
.animated {
  animation: fadeInUp 1.0s ease;
}
@keyframes fadeInUp {
  0% { opacity: 0; transform: translateY(18px); }
  100% { opacity: 1; transform: translateY(0); }
}
.mermaid {
  font-size: 0.7rem;
  max-width: 100%;
  height: auto;
}
</style>

# Ciberseguridad + Red Team + IA

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  **Explicar como si tuviera 12 años: ataques + defensa + IA.**
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Pie: esta diapositiva es la vista general y ancla mental.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

---

## Índice

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  1. Contexto global<br>
  2. Ciberseguridad (Feynman)<br>
  3. Red Team<br>
  4. Herramientas y matriz<br>
  5. IA en ciberseguridad<br>
  6. Ejercicio integrado<br>
  7. Recursos visuales<br>
  8. Recomendaciones<br>
  9. Conclusión<br>
  10. Q&A<br>
  11. Referencias
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Navega con flechas o click.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

---

## 1. Contexto global

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - Incidentes crecientes: ransomware, phishing, supply chain.
  - Mayor superficie: IoT, nube, trabajo remoto.
  - Ojo con MITRE ATT&CK: T1078, T1566, T1486.
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Nota: Empieza con una historia breve (empresa X afectada por phishing). Añade fecha / gráfica en vivo si es posible.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

---

## 2. Ciberseguridad (Feynman)

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  <strong>Explicación simple</strong><br>
  Ciberseguridad protege los datos y sistemas para que solo usuarios legítimos accedan.<br><br>
  <strong>Analogía</strong><br>
  Casa con puertas, cerraduras, cámaras (disponibilidad, integridad, confidencialidad).<br><br>
  <strong>Puntos claves</strong><br>
  - CIA: Confidencialidad, Integridad, Disponibilidad.
  - Defensa en profundidad: capas (perímetro, red, endpoint, app, datos).
  - Zero Trust: "nunca confíes, siempre verifica".

  ```mermaid
  graph TD
    A[Confidencialidad] --> B[Integridad]
    B --> C[Disponibilidad]
    C --> D[Defensa en Profundidad]
    D --> E[Perímetro]
    D --> F[Red]
    D --> G[Endpoint]
    D --> H[Aplicación]
    D --> I[Datos]
  ```
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Recordatorio: Invita a pensar en el correo electrónico y la llave de casa como credenciales. Siempre verifica identidad.
  </div>
</div>

---

## 3. Red Team (para un niño curioso)

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - ¿Qué es? Simular al ladrón para fortalecer la casa.
  - Objetivo: descubre fallos antes del atacante real.
  - Ciclo: Reconocimiento, Entrada, Movimiento lateral, Exfiltración.

  ```mermaid
  flowchart TD
    A[Reconocimiento<br/>OSINT, Nmap] --> B[Entrada<br/>Phishing, Exploits]
    B --> C[Movimiento lateral<br/>Pivoting, Escalada]
    C --> D[Exfiltración<br/>Datos robados]
    D --> E[Lecciones aprendidas<br/>Reportes y mejoras]
    style A fill:#e1f5fe
    style B fill:#fff3e0
    style C fill:#fce4ec
    style D fill:#f3e5f5
    style E fill:#e8f5e8
  ```
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Pie: Red Team no es delito; es controlado, autorizado y ético. Incluir fase de "lecciones aprendidas".
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

---

## 4. Herramientas y matriz simple

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  | Fase | Herramienta | Resultado esperado |
  | --- | --- | --- |
  | Recon | Nmap, OSINT | Inventario y vectores |
  | Explotación | Metasploit | Acceso inicial |
  | Post-exploit | BloodHound, Impacket | Dominio comprometido |

  - Complemento: scripts Python + IA para generación de payloads de prueba.
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Nota: El adversario también usa IA; mapea capacidades de IA de atacante y defensores.
  </div>
</div>

---

## 5. IA en ciberseguridad

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - Detección: ML sobre logs y tráfico (anomalías, comportamientos extraños).
  - Respuesta: SOAR, playbooks automáticos.
  - Riesgos: adversarial ML, deepfakes, phishing altamente personalizado.

  ```mermaid
  graph LR
    A[Logs/ Tráfico<br/>Entrantes] --> B[Modelo ML<br/>Entrenado]
    B --> C[Detección de Anomalía<br/>Score de Riesgo]
    C --> D[Alerta SOC<br/>Priorización]
    D --> E[Respuesta Automática<br/>Bloqueo/Quarantine]
    E --> F[Retroalimentación<br/>Mejora Modelo]
    F --> B
    style A fill:#e3f2fd
    style B fill:#f3e5f5
    style C fill:#fff3e0
    style D fill:#fce4ec
    style E fill:#e8f5e8
    style F fill:#e1f5fe
  ```
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Pie: Una buena política de datos (calidad y etiquetado) mejora IA; define métricas de éxito.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

---

## 6. Ejercicio integrado (Feynman en 60s)

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  1. Capturamos logs desde endpoints + firewall.
  2. Modelo ML identifica patrón de lateralidad raro.
  3. Alerta se deriva a SOC + bloquea la sesión.
  4. Red Team valida el conjunto mediante un ataque de prueba.

  - Resultado: detección temprana + remediación automatizada.

  ```mermaid
  sequenceDiagram
    participant E as Endpoint
    participant F as Firewall
    participant M as Modelo ML
    participant S as SOC
    participant R as Red Team

    E->>M: Envía logs
    F->>M: Envía tráfico
    M->>S: Anomalía detectada
    S->>S: Bloquea sesión
    R->>R: Valida con ataque simulado
  ```
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Nota: Subrayar que la defensa es un ciclo continuo y necesita retroalimentación diaria.
  </div>
</div>

---

## 7. Recursos visuales (imagen + link)

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  ![Vector ciberseguridad](https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=1200&q=80)

  - MITRE ATT&CK: https://attack.mitre.org
  - NIST CSF: https://www.nist.gov/cyberframework
  - OWASP Top 10
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Pie: Usa estos recursos para armar un plan trimestral y compartir con stakeholders.
  </div>
</div>

---

## 8. Recomendaciones prácticas

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - Auditorías periódicas + ejercicios Red/Blue/Purple
  - Implantar MFA + gestión de parches automatizada
  - Telemetría completa + observabilidad con IA
  - Definir gobernanza de modelos ML y privacidad

  ```mermaid
  graph TD
    A[Auditorías] --> B[MFA + Parches]
    B --> C[Telemetría + IA]
    C --> D[Gobernanza ML]
    D --> E[Zero Trust]
    E --> F[Monitoreo Continuo]
    style A fill:#e8f5e8
    style B fill:#e1f5fe
    style C fill:#fff3e0
    style D fill:#fce4ec
    style E fill:#f3e5f5
    style F fill:#e3f2fd
  ```
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Nota: pide un reporte trimestral con 5 métricas simples (incidentes, tiempo MTTR, cobertura MFA, hallazgos Red Team, efectividad IA).
  </div>
</div>

---

## 9. Conclusión Feynman

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - Ciberseguridad = protección activa + mentalidad de ataque.
  - Red Team = aprendizaje continuo.
  - IA = multiplicador si es confiable y supervisado.
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Pie: nunca dejes de preguntar “¿qué pasa si…?”.
  </div>
</div>

---

## 10. Q&A

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - Preguntas abiertas.
  - Ejercicio sugerido: mapea un flujo de datos de tu organización y encuentra 3 controles faltantes.
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Nota: usa estos puntos para fomentar la discusión.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>

<div style="display:grid;grid-template-columns:1.5fr 0.8fr;gap:1.5rem;align-items:start;">
  <div>
  - MITRE ATT&CK: https://attack.mitre.org<br>
  - NIST Cybersecurity Framework: https://www.nist.gov/cyberframework<br>
  - OWASP Top 10: https://owasp.org/www-project-top-ten/<br>
  - CSA (Cloud Security Alliance): https://cloudsecurityalliance.org/<br>
  - Libros: "The Art of Deception" de Kevin Mitnick<br>
  - Artículos: "AI in Cybersecurity" IEEE<br>
  </div>
  <div style="font-size:0.8rem;line-height:1.3;color:#999;">
  Fuentes para profundizar.
  </div>
</div>

<footer>Presentación Ciberseguridad + Red Team + IA | Javier | 2026</footer>
