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

As good practice, each function from the UnitTest class should use the next format for its name:
> NameOfTheTestedFunction\_Scenario\_ExpectedBehaviour

Inside the function, a good practice is to separate its instructions in three main sections:
```
// Arrange
    In this section contains all initializations
// Act
    Here are written all action to perform the test
// Assert
    Finally, the Assert object used for the test result is put here
```
