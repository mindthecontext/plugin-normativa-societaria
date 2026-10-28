---
name: quien-puede-firmar
description: Determina si una persona puede celebrar un acto concreto por una sociedad (SpA, anónima, limitada o EIRL), sola o con quién, con los documentos del caso — «¿puede la apoderada firmar sola el crédito?», «¿le alcanza el poder para hipotecar?», «¿el gerente puede vender el inmueble?», «¿basta su firma para abrir la cuenta?», «revisa la personería para esta compraventa», «¿quién tiene que firmar por la sociedad?». Separa lo que acredita el expediente de lo que dice la ley, cita pasaje y artículo con su versión, y se abstiene cuando falta un documento decisivo o dos versiones se contradicen. Úsala siempre que la respuesta dependa de un estatuto o un poder concreto.
---

# Quién puede firmar

Esta skill responde si una firma basta para que una sociedad celebre **un acto determinado**. El insumo son los
documentos de la sociedad y el acto; la salida es uno de tres estados, con los pasajes y artículos que lo sostienen y
lo que falta.

Lee primero `references/criterio-de-respuesta.md`: es la regla de esta skill. Las normas se leen con las herramientas
del servicio Societario (`ver_articulo`, `buscar_normas`), y la estructura del dominio con `cadena_del_tipo`,
`requisitos_del_acto`, `lista_de_revision` y `calcular_umbral`.

## 1 · Fija la pregunta

Antes de leer los documentos, anota:

- **Quién firmaría**, con el nombre que aparece en los documentos.
- **Por qué sociedad, de qué tipo y en qué régimen** (tradicional, RES o migrada). Si el tipo no está cubierto
  (`listar_cobertura`), dilo y para.
- **Qué acto**, en los términos del mapa (crédito, títulos, banca, garantías, enajenación, arrendamiento, laboral,
  judicial, administrativo, transigir, delegar, relacionadas, gratuitos), con su monto, unidad, fecha prevista y las
  garantías que traiga. Cada garantía es un acto aparte.
- **Cómo firmaría**: sola o con quién.

Lo que quien pregunta no dio no se supone: es un faltante.

## 2 · Trae la estructura del caso

Llama, en paralelo:

- `cadena_del_tipo` con el tipo y el régimen: de dónde salen las reglas y dónde constan los poderes.
- `requisitos_del_acto` con el acto y el tipo: qué tiene que decir el poder y qué reglas del tipo reservan el acto a
  otro órgano.
- `lista_de_revision` con tipo, régimen, acto y momento: la cadena de documentos que vas a recorrer.

## 3 · Haz el inventario del expediente

Lista cada documento con su fecha, tipo y quién lo otorga, ordenados por fecha. Marca cuál fija la administración,
cuál otorga la facultad, cuáles modifican o revocan, y cuál acredita vigencia y a qué fecha. Un documento que
menciona otro no es ese otro. Revisa que cada documento esté entero (páginas, artículos, letras, cláusulas) y aplica
las reglas de página ausente e integración del órgano del criterio.

## 4 · Lee la cláusula entera

Copia el pasaje literal de la facultad y lee en él: **qué actos**, **quiénes**, **de qué modo** y **hasta cuánto**,
en qué unidad y si es por operación o acumulado. Las restricciones suelen estar en otra frase, un párrafo final o una
cláusula posterior: busca «sin perjuicio», «no obstante», «en todo caso», «se exceptúa», «conjuntamente», «previo
acuerdo». En el estatuto, lee también los títulos que no son de administración: una limitación al endeudamiento o a
las garantías puede estar en el de juntas o en el de capital.

## 5 · Lee las normas que vas a usar

Con `ver_articulo`, lee cada artículo antes de citarlo. Si vas a aplicar una supletoria, haz y escribe las tres
comprobaciones de «La cadena del tipo social». Si las unidades del monto y del límite difieren, usa `calcular_umbral`.
Si la respuesta depende de una regla provisional, búscala en `preguntas_abiertas` y nómbrala en Límites.

## 6 · Decide con el criterio, en su orden

Recorre los ocho pasos de «Cómo se decide». Si varios fallan, di todos. Elige el estado y escribe la respuesta en el
formato del criterio. Si la pregunta también es por los efectos de una firma ya hecha, agrega la sección de efectos o
deriva a `firma-irregular`.

## 7 · Revisa antes de entregar

- Cada hecho lleva su pasaje literal; cada norma, su id, artículo y versión, leída en esta conversación.
- Ninguna falla de la lista final del criterio.
- La respuesta corta responde lo preguntado, en el registro de quien preguntó, y el siguiente paso es una actuación
  concreta (quién más firma, qué documento pedir, qué ajustar).
