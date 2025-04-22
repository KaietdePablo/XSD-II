# XSD-II

Ejercicio: Validación de números y letras en atributos y elementos

He creado un esquema `fichas.xsd` para validar un documento XML que contiene varias fichas. Cada ficha tiene un atributo obligatorio `numero`, un atributo opcional `letra`, y los elementos `codigo` y `nombre`. La condición principal era que tanto `numero` como `codigo` debían tener un valor numérico de dos dígitos comprendido entre `"00"` y `"19"`, y que el atributo `letra` solo pudiera tomar los valores `"X"`, `"Y"` o `"Z"`. Para esto, he creado un tipo simple reutilizable `tipoDosDigitos` con una expresión regular que valida valores entre `00` y `19`, y un tipo simple exclusivo para el atributo `letra` (`tipoLetraXYZ`) que usa `xs:enumeration`. La estructura asegura que `numero` sea obligatorio y que `letra` sea opcional, cumpliendo con todas las condiciones del ejercicio.

Ejercicio: Validación de pares de letras mayúscula-minúscula

En este ejercicio he modificado una definición de elemento llamada `letras` que originalmente aceptaba cualquier cantidad de letras minúsculas. La nueva condición era que el valor tuviera uno o más pares de letras, donde cada par debe estar formado por una letra mayúscula seguida de una letra minúscula. Por ejemplo, valores como `"HoLa"` serían válidos, pero no `"Hola"`, `"HOLa"` o `"hola"`. Para ello, he usado una expresión regular con patrón `[A-Z][a-z]+` repetido una o más veces: `([A-Z][a-z])+`. Así, se obliga a que los caracteres se agrupen en pares válidos y que haya al menos uno.

Ejercicio: Restricción de valores admitidos con pattern y enumeration

En este ejercicio trabajé con un elemento llamado `respuesta` que debe aceptar únicamente las letras `"A"`, `"B"`, `"C"`, `"D"` o `"E"`. Originalmente se usaba una expresión regular con el patrón `[ABCDE]`. He explicado que esto se puede escribir también como `[A-E]` (usando un rango) o `[A|B|C|D|E]` (usando alternativas explícitas). Además, he demostrado cómo se puede hacer lo mismo sin usar `xs:pattern`, utilizando `xs:enumeration` para definir cada letra como un valor permitido. Esta alternativa es más clara y sencilla cuando el número de valores posibles es pequeño y fijo.

Ejercicio: Expresiones regulares con patrones variados

He resuelto ocho subejercicios en los que había que escribir expresiones regulares para validar distintos tipos de cadenas según unas reglas dadas. En cada caso he utilizado únicamente los símbolos permitidos según la tabla del enunciado (`*`, `+`, `{n}`, `\d`, `\D`, `[abc]`, etc.). Por ejemplo, para validar cadenas como `"Capítulo 0"` hasta `"Capítulo 9"` he usado `Capítulo \d`, y para validar cadenas como `"HoLa"` he utilizado `([A-Z][a-z])+`. También he trabajado con expresiones que validan cadenas complejas como `"RSSS7"` o `"COD645pera"`, combinando repeticiones, patrones numéricos y caracteres opcionales. Ha sido un ejercicio muy útil para practicar la construcción precisa de patrones con expresiones regulares dentro de esquemas XSD.

