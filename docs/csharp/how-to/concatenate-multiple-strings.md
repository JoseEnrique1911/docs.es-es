---
title: "Concatenación de varias cadenas (Guía de C#)"
description: "Hay varias maneras de concatenar cadenas en C#. Obtenga información sobre las opciones y las razones para las diferentes opciones."
ms.date: 01/11/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4bc5e04edba48065746b96841b628ec5843c5e9
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="774d5-104">Concatenación de varias cadenas (Guía de C#)</span><span class="sxs-lookup"><span data-stu-id="774d5-104">How to: Concatenate Multiple Strings (C# Guide)</span></span>

<span data-ttu-id="774d5-105">*Concatenación* es el proceso de anexar una cadena al final de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="774d5-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="774d5-106">Las cadenas se concatenan con el operador +.</span><span class="sxs-lookup"><span data-stu-id="774d5-106">You concatenate strings by using the + operator.</span></span> <span data-ttu-id="774d5-107">En el caso de los literales y las constantes de cadena, la concatenación se produce en tiempo de compilación, y no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="774d5-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="774d5-108">En cambio, para las variables de cadena, la concatenación solo se produce en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="774d5-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="774d5-109">En el ejemplo siguiente se usa la concatenación para dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad del código fuente.</span><span class="sxs-lookup"><span data-stu-id="774d5-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="774d5-110">Estas partes se concatenarán en una sola cadena en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="774d5-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="774d5-111">No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas de que se trate.</span><span class="sxs-lookup"><span data-stu-id="774d5-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  
  

<span data-ttu-id="774d5-112">Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, la [interpolación de cadena](../tutorials/string-interpolation.md) o los métodos <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="774d5-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../tutorials/string-interpolation.md) or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="774d5-113">El operador `+` es sencillo de usar y genera un código intuitivo.</span><span class="sxs-lookup"><span data-stu-id="774d5-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="774d5-114">Incluso si usa varios operadores + en una instrucción, el contenido de la cadena se copia solo una vez.</span><span class="sxs-lookup"><span data-stu-id="774d5-114">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="774d5-115">En el código siguiente se muestran dos ejemplos del uso del operador `+` para concatenar cadenas:</span><span class="sxs-lookup"><span data-stu-id="774d5-115">The following code shows two examples of using the `+` operator to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="774d5-116">En algunas expresiones, es más fácil concatenar cadenas mediante la interpolación de cadena, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="774d5-116">In some expressions, it is easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
>  <span data-ttu-id="774d5-117">En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="774d5-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="774d5-118">Otros métodos para concatenar cadenas son <xref:System.String.Concat%2A?displayProperty=nameWithType> y <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="774d5-118">Other methods to concatenate strings are <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="774d5-119">Estos métodos funcionan bien para compilar una cadena a partir de un número reducido de cadenas de componente.</span><span class="sxs-lookup"><span data-stu-id="774d5-119">These methods work well when you are building a string from a small number of component strings.</span></span> <span data-ttu-id="774d5-120">Estos métodos también son una excelente opción si conoce el número de cadenas que componen la cadena concatenada.</span><span class="sxs-lookup"><span data-stu-id="774d5-120">These methdos are also a great choice when you know the number of strings that make up your concatenated string.</span></span>

<span data-ttu-id="774d5-121">En otros casos, puede combinar cadenas en un bucle, donde no sabe cuántas cadenas de origen se combinan, y el número real de cadenas de origen puede ser bastante elevado.</span><span class="sxs-lookup"><span data-stu-id="774d5-121">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="774d5-122">La clase <xref:System.Text.StringBuilder> se diseñó para estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="774d5-122">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="774d5-123">El código siguiente usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="774d5-123">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="774d5-124">Puede obtener más información sobre las [razones para elegir la concatenación de cadenas o sobre la clase `StringBuilder`](xref:System.Text.StringBuilder#StringAndSB).</span><span class="sxs-lookup"><span data-stu-id="774d5-124">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB)</span></span>

<span data-ttu-id="774d5-125">Otra opción para combinar cadenas de una colección consiste en usar [LINQ](../programming-guide/concepts/linq/index.md) y el método <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="774d5-125">Another option to join strings from a collection is to use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="774d5-126">Este método combina las cadenas de origen mediante una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="774d5-126">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="774d5-127">La expresión lambda realiza el trabajo de agregar cada cadena a la acumulación existente.</span><span class="sxs-lookup"><span data-stu-id="774d5-127">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="774d5-128">En el ejemplo siguiente se combina una matriz de palabras mediante la adición de un espacio entre cada palabra de la matriz:</span><span class="sxs-lookup"><span data-stu-id="774d5-128">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]  


## <a name="see-also"></a><span data-ttu-id="774d5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="774d5-129">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="774d5-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="774d5-130">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="774d5-131">Cadenas</span><span class="sxs-lookup"><span data-stu-id="774d5-131">Strings</span></span>](../programming-guide/strings/index.md)