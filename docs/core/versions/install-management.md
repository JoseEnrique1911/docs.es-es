---
title: Administrar las instalaciones de .NET Core
description: Administre varias versiones del SDK y Runtime de .NET Core en el equipo, y trabaje con las estrategias de instalación en paralelo.
author: leecow
ms.author: wiwagn
ms.date: 08/22/2018
ms.openlocfilehash: 06c3f43e7917efb8fd31898044d8f5d920c2cada
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485454"
---
# <a name="manage-net-core-installations"></a><span data-ttu-id="42f4d-103">Administrar las instalaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="42f4d-103">Manage .NET Core installations</span></span>

<span data-ttu-id="42f4d-104">.NET Core permite la coexistencia de varias versiones del SDK y Runtime en paralelo, lo que ofrece flexibilidad a la dependencia de versiones tanto para compilar como para ejecutar aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42f4d-104">.NET Core allows multiple versions of the SDK and Runtime to exist side-by-side, enabling version dependency flexibility for both building and running .NET Core applications.</span></span> <span data-ttu-id="42f4d-105">Este tipo de instalación y estos comportamientos de actualización automática de versiones tienen importantes ventajas, pero una destacada desventaja.</span><span class="sxs-lookup"><span data-stu-id="42f4d-105">These installation and automatic version roll-forward behaviors offer valuable benefits, but one pronounced drawback.</span></span> <span data-ttu-id="42f4d-106">A medida que se instalan las actualizaciones del SDK de .NET Core o .NET Core Runtime, las versiones anteriores permanecen en el disco.</span><span class="sxs-lookup"><span data-stu-id="42f4d-106">As updates of the .NET Core SDK or .NET Core Runtime are installed, previous versions remain on-disk.</span></span> <span data-ttu-id="42f4d-107">Con el tiempo, esta instalación de numerosas versiones incrementa el uso de disco.</span><span class="sxs-lookup"><span data-stu-id="42f4d-107">Multiple installed versions increase disk usage over time.</span></span> <span data-ttu-id="42f4d-108">Se han publicado más de 50 actualizaciones del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42f4d-108">More than 50 .NET Core SDK updates have been released.</span></span> <span data-ttu-id="42f4d-109">Es posible que haya muchas versiones del SDK y Runtime instaladas en el sistema que se podrían quitar.</span><span class="sxs-lookup"><span data-stu-id="42f4d-109">There may be many versions of the SDK and Runtime installed on your system that could be removed.</span></span>

## <a name="safe-to-remove"></a><span data-ttu-id="42f4d-110">¿Es seguro quitarlas?</span><span class="sxs-lookup"><span data-stu-id="42f4d-110">Safe to remove?</span></span>

<span data-ttu-id="42f4d-111">Los comportamientos de la [selección de la versión de .NET Core](selection.md) y la compatibilidad de runtime de .NET Core en diferentes actualizaciones permite quitar de forma segura las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="42f4d-111">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="42f4d-112">Las actualizaciones de .NET Core Runtime son compatibles con una "banda" de versión principal, como 1.x y 2.x.</span><span class="sxs-lookup"><span data-stu-id="42f4d-112">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="42f4d-113">Además, normalmente las versiones más recientes del SDK de .NET Core mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del tiempo de ejecución de una forma compatible.</span><span class="sxs-lookup"><span data-stu-id="42f4d-113">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="42f4d-114">En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42f4d-114">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="42f4d-115">Los casos en los que se conservan versiones anteriores del SDK o Runtime incluyen el mantenimiento de aplicaciones basadas en project.json.</span><span class="sxs-lookup"><span data-stu-id="42f4d-115">Instances where retaining older SDK or Runtime versions include maintaining project.json-based applications.</span></span>  <span data-ttu-id="42f4d-116">A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="42f4d-116">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

<span data-ttu-id="42f4d-117">Los métodos para quitar .NET Core varían en función de la plataforma y han cambiado un poco entre versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42f4d-117">The methods for removing .NET Core vary from platform to platform and have changed somewhat across .NET Core versions.</span></span> <span data-ttu-id="42f4d-118">Para obtener más información sobre cómo quitar versiones de .NET Core que ya no se necesitan, vea [How to remove the .NET Core Runtime and SDK](remove-runtime-sdk-versions.md) (Cómo quitar el SDK y Runtime de .NET Core) en la [documentación de .NET Core](../index.md).</span><span class="sxs-lookup"><span data-stu-id="42f4d-118">For details on removing versions of .NET Core that are no longer needed, see ['How to remove the .NET Core Runtime and SDK'](remove-runtime-sdk-versions.md) in the [.NET Core documentation](../index.md).</span></span>