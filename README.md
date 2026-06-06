# Soporte para Múltiples Enlaces por Categoría

Este proyecto permite asociar múltiples enlaces a una misma categoría. Si un enlace deja de estar disponible, el sistema intentará utilizar automáticamente el siguiente enlace configurado.

## Estructura

Cada categoría puede contener uno o más enlaces:

```json
{
  "WhatsApp": [
    "https://server1.com",
    "https://server2.com"
  ],
  "Telegram": [
    "https://server3.com",
    "https://server4.com"
  ]
}
```

## Funcionamiento

1. El usuario solicita una categoría.
2. El sistema busca los enlaces asociados a dicha categoría.
3. Se intenta utilizar el primer enlace disponible.
4. Si el enlace falla, se prueba el siguiente.
5. El proceso continúa hasta encontrar un enlace funcional.
6. Si todos los enlaces fallan, se devolverá un error.

## Añadir una Nueva Categoría

```json
{
  "NuevaCategoria": [
    "https://enlace1.com",
    "https://enlace2.com"
  ]
}
```

## Añadir Más Enlaces a una Categoría

### Antes

```json
{
  "WhatsApp": [
    "https://server1.com"
  ]
}
```

### Después

```json
{
  "WhatsApp": [
    "https://server1.com",
    "https://server2.com",
    "https://server3.com"
  ]
}
```

## Ejemplo Completo

```json
{
  "WhatsApp": [
    "https://principal.com",
    "https://backup1.com",
    "https://backup2.com"
  ],

  "Discord": [
    "https://discord1.com",
    "https://discord2.com"
  ],

  "Telegram": [
    "https://telegram1.com",
    "https://telegram2.com"
  ]
}
```

## Recomendaciones

- Utilizar nombres únicos para cada categoría.
- Mantener al menos dos enlaces por categoría.
- Colocar primero el enlace principal.
- Verificar periódicamente la disponibilidad de los enlaces.
- Utilizar HTTPS siempre que sea posible.
- Añadir enlaces de respaldo para mejorar la disponibilidad del servicio.

## Nota

Las categorías funcionan como identificadores. Cada categoría puede contener una cantidad ilimitada de enlaces, permitiendo implementar sistemas de redundancia y alta disponibilidad.
