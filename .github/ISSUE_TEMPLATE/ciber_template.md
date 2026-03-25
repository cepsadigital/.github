name: 🔐 Cybersecurity Support
about: Reporta cualquier problema o bloqueo relacionado con seguridad (secret scanning, code scanning, dependencias, permisos, etc.)
title: "[CIBER] "
labels: ["ciber"]

body:
  - type: dropdown
    id: category
    attributes:
      label: Tipo de problema
      options:
        - Secret Scanning / Push Protection
        - Code Scanning / SAST
        - Dependency Scanning / Dependabot
        - Permisos y accesos
        - Otro
    validations:
      required: true

  - type: dropdown
    id: urgency
    attributes:
      label: Urgencia
      options:
        - 🔴 Bloqueante (no puedo mergear/desplegar)
        - 🟠 Alta (afecta al desarrollo activo)
        - 🟡 Media (puedo continuar con workaround)
        - 🟢 Baja (consulta o mejora)
    validations:
      required: true

  - type: textarea
    id: what
    attributes:
      label: ¿Qué ha pasado?
      description: Describe el problema o bloqueo con el mayor detalle posible.
      placeholder: "Al hacer push a main, secret scanning bloqueó el commit porque..."
    validations:
      required: true

  - type: textarea
    id: bypass
    attributes:
      label: ¿Se ha hecho algún bypass o workaround?
      description: Si se saltó alguna protección, es importante que ciber lo sepa.
      placeholder: "No / Sí, porque..."
    validations:
      required: false

  - type: textarea
    id: extra
    attributes:
      label: Contexto adicional
      description: PR relacionado, rama, error exacto, capturas...
    validations:
      required: false