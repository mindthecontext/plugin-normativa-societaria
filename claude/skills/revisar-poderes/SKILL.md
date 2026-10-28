---
description: Hace el informe de poderes (o de personería) de una sociedad a partir de su expediente — «revisa los poderes de esta empresa», «haz el informe de personería», «¿quiénes pueden representar a la sociedad y para qué?», «tengo que onboardear a este cliente empresa, aquí van sus escrituras», «arma la ficha de apoderados». Entrega la sociedad y su régimen, quién la administra, cada apoderado con sus facultades, modalidad y límites, la vigencia, las observaciones y lo que falta, citando pasaje y artículo. Para SpA, anónimas, limitadas y EIRL.
---

# Revisar los poderes de una sociedad

Esta skill hace el trabajo completo que una fiscalía o una notaría hace antes de operar con una empresa: leer el
expediente y decir **quién la representa, para qué, cómo y hasta cuánto, y si está vigente**. No responde por un acto
en particular (para eso, `quien-puede-firmar`), pero cada facultad que informa lleva su estado.

Lee primero `references/criterio-de-respuesta.md`.

## 1 · Identifica la sociedad

Nombre, RUT, tipo social, régimen (tradicional, RES o migrada), domicilio, fecha de constitución y de las
modificaciones. Llama a `cadena_del_tipo` y a `lista_de_revision` (sin acto) con el tipo y el régimen.

## 2 · Inventario y vacíos

Lista cada documento con fecha, tipo y otorgante, ordenados por fecha. Contra la lista de revisión, marca lo que
está, lo que está mencionado pero no aportado, y lo que falta. Revisa integridad (páginas, cláusulas).

## 3 · La administración

Quién administra según el estatuto vigente (con el pasaje), y si el estatuto calla, según la cadena del tipo (con las
tres comprobaciones). Quién puede otorgar poderes y con qué formalidad. Integración del órgano a la fecha de cada
otorgamiento, como condición salvo señal concreta.

## 4 · Cada apoderado

Para cada persona que el expediente faculta, una ficha:

```
<Nombre> · <cargo o calidad> · <documento que la faculta, fecha, localizador>
Facultades: <lista de actos, con el pasaje literal de cada una o de la cláusula>
Modalidad: individual | conjunta con <quién> | por clases (<cuáles>)
Límites: <monto, unidad, por operación o acumulado, plazo, exclusiones>
Vigencia: <constancia y fecha> | condicionada a <qué>
Estado por acto: <acto> — RESPALDA CON CONDICIONES | NO RESPALDA | NO SE PUEDE DETERMINAR (motivo en una frase)
```

Usa `requisitos_del_acto` para decidir si una facultad comprende cada acto que informas (créditos, títulos, banca,
garantías, enajenación…). Una facultad no comprende otra que la ley separa. Si el poder está en otra unidad que la
operación habitual, no conviertas: informa el límite como está.

## 5 · Observaciones

Lo que una fiscalía tiene que saber antes de operar: contradicciones entre documentos (sin elegir), reformas que
cambiaron la administración, poderes anteriores a una migración, reglas del tipo que reservan actos a la junta o al
directorio, reglas provisionales de las que depende el informe (`preguntas_abiertas`).

## 6 · Formato

```
Informe de poderes · <sociedad> · <fecha de la revisión>
Respuesta corta: <quiénes pueden obligar a la sociedad, para qué, y la condición principal>

1. Sociedad y régimen
2. Administración (con pasaje y normas)
3. Apoderados (una ficha por persona)
4. Vigencia
5. Observaciones
6. Lo que falta pedir (documento concreto y qué cambia)
Normas aplicadas (corpus societario-corpus-2026-10-28): <ID · norma, art. · versión · para qué>
Límites
```

Cada hecho, con su pasaje literal; cada norma, leída con `ver_articulo`. Ninguna falla de la lista del criterio.
