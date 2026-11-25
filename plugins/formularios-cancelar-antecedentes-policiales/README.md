# Penal: antecedentes policiales y escritos ante la Sección de Instrucción

> Plugin de Claude Code `formularios-cancelar-antecedentes-policiales` · **2 formularios** · Penal · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Dos formularios penales: solicitud a la Sección de Instrucción del Tribunal de Instancia para que acuerde o certifique el archivo de unas diligencias (para pedir después la cancelación de los antecedentes policiales) y escrito del perjudicado que renuncia a las acciones contra la aseguradora.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 2 está al final):

- **Comunicaciones, requerimientos y cartas** (1). Por ejemplo: Solicitud al juzgado de instrucción de archivo de diligencias para cancelar antecedentes policiales.
- **Escritos de trámite y otros** (1). Por ejemplo: Escrito ante la Sección de Instrucción del perjudicado que renuncia a acciones contra la aseguradora.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Solicitud de archivo de diligencias para cancelar antecedentes policiales»
   - «Escrito del perjudicado que renuncia a las acciones contra la aseguradora»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-cancelar-antecedentes-policiales:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-cancelar-antecedentes-policiales:solicitud-juzgado-instruccion-archivo-diligencias-pen-0001`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 214 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-cancelar-antecedentes-policiales@formularios-juridicos-penal-espana`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-juridicos-penal-espana
/plugin install formularios-cancelar-antecedentes-policiales@formularios-juridicos-penal-espana
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-juridicos-penal-espana`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-juridicos-penal-espana/releases/latest/download/formularios-cancelar-antecedentes-policiales.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (2)

| Código | Formulario | Skill |
|---|---|---|
| PEN-0001 | Solicitud al juzgado de instrucción de archivo de diligencias para cancelar antecedentes policiales | `solicitud-juzgado-instruccion-archivo-diligencias-pen-0001` |
| PEN-0002 | Escrito ante la Sección de Instrucción del perjudicado que renuncia a acciones contra la aseguradora | `escrito-ante-seccion-instruccion-perjudicado-renuncia-pen-0002` |

## Privacidad

Ver `PRIVACY.md`.
