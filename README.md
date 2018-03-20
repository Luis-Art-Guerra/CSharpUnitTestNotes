# CSharpUnitTestTutorial
Contiene archivos que estaré usando para un pequeño tutorial de  pruebas unitarias en C# y Visual Studio

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

Como buena práctica, cada función de la clase UnitTest debe usar el siguiente formato para su nombre:

> NombreFuncionAProbar\_Escenario\_ResultadoEsperado

Dentro de la función, una buena práctica es separar las instrucciones en tres secciones:

```
// Arrange
    Aquí se encuentran las inicializaciones
// Act
    Aquí se ponen todas las acciones realizadas para la prueba
// Assert
    Finalmente, se usa el objeto Assert para comprobar el resultado de la prueba.
```
