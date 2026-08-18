# OmniBlock — Ficha de la tienda (Español)

Copia traducida para las fichas en español de la Chrome Web Store y de
AMO. Ambas tiendas aceptan fichas por idioma -- ver `submission-runbook.md`
para el proceso de dónde introducir cada texto. La estructura, los
límites de caracteres, la categoría, las capturas de pantalla, las
imágenes promocionales y la declaración de recopilación de datos están
en `listing.md` (en inglés, fuente de verdad para el proceso) -- este
archivo solo contiene el texto orientado al usuario que realmente se
introduce por idioma.

## Nombre

```
OmniBlock
```

## Descripción breve (Chrome Web Store, ≤132 caracteres)

125 caracteres:

```
Bloqueador de anuncios, rastreadores y amenazas: 6 niveles de protección, Security Shield, listas propias, control por sitio.
```

## Resumen (AMO, ≤250 caracteres)

220 caracteres:

```
Bloquea anuncios, rastreadores y sitios maliciosos conocidos en 6 niveles de protección más un Security Shield independiente. Listas propias, confianza por sitio, selector de elementos. Cero telemetría, totalmente local.
```

## Descripción completa (ambas tiendas)

```
OmniBlock es un bloqueador de contenido multi-navegador: anuncios,
rastreadores, avisos de cookies y sitios maliciosos conocidos, con un
regulador de protección de 0 a 5, un Security Shield independiente y
siempre activo, controles por sitio, suscripciones a listas de filtros
propias y un selector de elementos con solo apuntar y hacer clic.

SINCEROS SOBRE LAS DIFERENCIAS DE PLATAFORMA

En Chrome, Edge, Brave y otros navegadores basados en Chromium, OmniBlock
funciona sobre la API nativa declarativeNetRequest de Manifest V3.
Ninguna extensión de Manifest V3 -- OmniBlock incluido -- puede igualar lo
que lograba uBlock Origin en la era de MV2, porque Chrome eliminó la API
de filtrado dinámico que lo hacía posible. La verdadera competencia de
OmniBlock en Chromium son uBO Lite y ABP-MV3, y nuestro objetivo es
superarlos en profundidad de listas de filtros, comodidad de los niveles
de protección y control por sitio, funcionando a la velocidad nativa de
DNR: cero JavaScript en la ruta de las solicitudes, lo que es
estrictamente más rápido que cualquier coincidencia evaluada por JS de un
bloqueador de la era MV2.

En Firefox, OmniBlock usa webRequest de bloqueo completo con su propio
motor de filtrado, lo que lo sitúa genuinamente en la misma categoría que
uBlock Origin: soporte completo de la sintaxis de listas de filtros,
reglas ilimitadas, y un motor de coincidencia que, según los propios
benchmarks publicados por Ghostery, es más rápido que el de uBO.

Preferimos contárselo desde el principio antes de que lo descubra por las
malas.

CARACTERÍSTICAS

- 6 niveles de protección (de Apagado a Fortaleza), cada uno acumulativo
  y precompilado -- cambiar de nivel es instantáneo, sin reiniciar
- Security Shield independiente: listas de amenazas (malware, phishing,
  fraude, tiendas falsas) que permanecen activas incluso con el nivel de
  protección en Apagado, porque la seguridad no es una preferencia de
  bloqueo de anuncios
- Suscripciones a listas de filtros propias -- suscríbete a cualquier
  URL de lista en sintaxis adblock o hosts
- Mis filtros -- escribe tus propias reglas de filtrado a mano,
  validadas línea por línea
- Selector de elementos -- apunta y haz clic para ocultar cualquier cosa
  que una lista de filtros haya pasado por alto
- Controles por sitio -- confía plenamente en un sitio con un clic para
  excluirlo del bloqueo
- Panel de estadísticas local -- historial de solicitudes bloqueadas y
  dominios más bloqueados (Firefox; ver la nota de la página de
  Estadísticas sobre por qué Chromium no puede exponer estos datos a
  ninguna extensión)
- Importa o exporta tus ajustes como un único archivo
- Interfaz Rift, solo modo oscuro (sistema de diseño OmniVex, el azul
  característico de OmniBlock), pensada para un popup rápido y sin
  fricciones

PRIVACIDAD

Cero recopilación de datos. Sin telemetría, sin analítica, sin cuentas,
sin servidor. Las listas de filtros se descargan como texto en sintaxis
adblock desde sus mantenedores públicos (EasyList, las listas de filtros
de uBlock Origin, las listas de bloqueo DNS de HaGeZi). La biblioteca de
scriptlets a la que esas reglas pueden hacer referencia viene empaquetada
dentro de la propia extensión, fijada a una versión concreta y verificada
-- y a cualquier lista que suscribas tú mismo se le eliminan las líneas
que invocan scriptlets antes de que los motores de bloqueo de OmniBlock
lleguen siquiera a verlas. Política completa: consulta la pestaña de
Privacidad de esta ficha.
```
