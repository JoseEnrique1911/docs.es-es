---
title: Procedimiento Interrumpir y combinar instrucciones en código (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: b19c36018a0938b9b6546e5baefbbc3de1e5dd30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619920"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Procedimiento Interrumpir y combinar instrucciones en código (Visual Basic)
Al escribir el código, a veces puede crear instrucciones largas que requieren un desplazamiento horizontal en el Editor de código. Aunque esto no afecta a la forma se ejecuta el código, resulta difícil para que usted u otra persona leer el código tal y como aparece en el monitor. En tales casos, considere la posibilidad de dividir la única instrucción larga en varias líneas.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Para dividir una única instrucción en varias líneas  
  
-   Usar el carácter de continuación de línea, que es un carácter de subrayado (`_`), en el punto en el que desea que el salto de línea. El carácter de subrayado debe tener inmediatamente antes un espacio e inmediatamente después un terminador de línea (retorno de carro).  
  
    > [!NOTE]
    >  En algunos casos, si se omite el carácter de continuación de línea, el compilador de Visual Basic implícitamente continuará, en la siguiente línea de código, la instrucción. Para obtener una lista de elementos de sintaxis para el que puede omitir el carácter de continuación de línea, vea "Continuación de línea implícita" en [instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     En el ejemplo siguiente, la instrucción se divide en cuatro líneas con caracteres de continuación de línea final de todas excepto la última línea.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Con esta secuencia hace que el código más fácil de leer, tanto en línea como al imprimirlo.  
  
     El carácter de continuación de línea debe ser el último carácter de una línea. No puede seguir con cualquier otra cosa en la misma línea.  
  
     Existen algunas limitaciones sobre dónde puede usar el carácter de continuación de línea; Por ejemplo, no puede usar en el medio de un nombre de argumento. Puede interrumpir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.  
  
     No puede continuar un comentario mediante el uso de un carácter de continuación de línea. El compilador no examina los caracteres de un comentario para un significado especial. Para un comentario de varias líneas, repita el símbolo de comentario (`'`) en cada línea.  
  
 Aunque el método recomendado consiste en colocar cada instrucción en una línea independiente, Visual Basic también permite colocar varias instrucciones en la misma línea.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Colocar varias instrucciones en la misma línea  
  
-   Separe las instrucciones con un signo de dos puntos (`:`), como en el ejemplo siguiente.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Vea también
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
