# Notas: Pruebas Unitarias en C# y Visual Studio
Este repositorio es un conjunto de notas como _referencia rápida_ para realizar pruebas unitarias. Si has llegado a este repositorio y ves información útil aquí, considera adquirir el curso _"Unit Testing for C# Developers"_ de _Mosh Hamedani_. Puedes encontrar su curso en Udemy.

# Procedimiento para realizar pruebas unitarias

## Prueba unitaria con MSTest

MSTest está incluido dentro de Visual Studio. No necesita instalación adicional.

Una vez preparada el proyecto que se va a probar, se agrega dentro de la solución otro proyecto de tipo **Unit Test Project**. Su nombre debe tener el formato:

> NombreProyecto.TestUnit


Se crea un archivo .cs con el siguiente formato:

```
using Microsoft. VisualStudio.TestsTools.UnitTesting
namespace NombreProyectoAProbar.UnitTest
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod]
        public void TestMethod1()
        {
        }
    }
}
```

Como buena práctica, la clase de pruebas debe llamarse como la clase que vas a probar más la palabra _Tests_. Por ejemplo:

> ClassNameTests

Además, cada función de la clase de pruebas debe usar el siguiente formato para su nombre:

> NombreFuncionAProbar\_Escenario\_ResultadoEsperado

Dentro de cada función, una buena práctica es separar las instrucciones en tres secciones:

```
// Arrange
    Aquí se encuentran las inicializaciones
// Act
    Aquí se ponen todas las acciones realizadas para la prueba
// Assert
    Finalmente, se usa el objeto Assert para comprobar el resultado de la prueba.
```

## Prueba unitaria con NUnit

NUnit debe instalarse en cada proyecto para poder ser usado. Para instalar, hay que abrir el _Package Manager_, e introducir los siguientes comandos:

```shell
PM> install-package NUnit -Version 3.8.1
...
PM> install-package NUnit3TestAdapter -Version 3.8.0
```

Los atributos cambian de nombre:

```
[TestClass]     ->      [TestFixture]
[TestMethod]    ->      [Test]
```

El objeto **Assert** se sigue usando, pero ya no es una clase de la biblioteca **Microsoft.VisualStudio.TestTools.UnitTesting**, ahora la referencia es:

> using NUnit.Framework;

Si se dejan las dos referencias juntas, habrá error debido a que el compilador no sabrá a cual objeto Assert se está refiriendo el código.

La clase Assert tiene algunas ventajas en cuanto a lectura.

Para **MSTest**, Assert se puede usar así:
```
Assert.IsTrue(result);
```

Adicionalmente, **NUnit** agrega las siguientes dos formas:
```
Assert.That(result, Is.True);
Assert.That(result == true);
```
Lo anterior se lee como lenguaje natural: _"Afirma que el resultado es verdadero"_

