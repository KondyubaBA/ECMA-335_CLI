## Assembly 0x20
Таблица Assembly (с кодом 0x20) содержит одну запись на каждую сборку в модуле. Она хранит информацию, которая описывает саму сборку, такую как версия, культура, публичный ключ и так далее.

|              |           |                                                                                |
|--------------|-----------|--------------------------------------------------------------------------------|
|HashAlgId     |4 байта    |Идентификатор алгоритма хеширования, используемого для хеширования файлов сборки|
|MajorVersion  |2 байта    |Основная версия сборки                                                          |
|MinorVersion  |2 байта    |Минорная версия сборки                                                          |
|BuildNumber   |2 байта    |Номер сборки                                                                    |
|RevisionNumber|2 байта    |Номер ревизии                                                                   |
|Flags         |4 байта    |Флаги, определяющие атрибуты сборки                                             |
|PublicKey     |Blob       |Публичный ключ сборки                                                           |
|Name          |String     |Имя сборки                                                                      |
|Culture       |String     |Культура сборки                                                                 |

## HashAlgId
|Algorithm     | Value |
|--------------|-------|
|None          | 0x0000|
|Reserved (MD5)| 0x8003|
|SHA1          | 0x8004|

## Flags
| Flag                     | Value | Description |
|--------------------------|-------|-------------|
|PublicKey                 |0x0001 |Ссылка на сборку содержит полный (не хешированный) публичный ключ.             |
|Retargetable              |0x0100 |Реализация этой сборки, используемая во время выполнения, не обязательно должна совпадать с версией, виденной во время компиляции. (См. текст после этой таблицы.)             |
|DisableJITcompileOptimizer|0x4000 |Зарезервировано (соответствующая реализация CLI может игнорировать эту настройку при чтении; некоторые реализации могут использовать этот бит для указания, что компилятор CIL в машинный код не должен генерировать оптимизированный код).             |
|EnableJITcompileTracking  |0x8000 |Зарезервировано (соответствующая реализация CLI может игнорировать эту настройку при чтении; некоторые реализации могут использовать этот бит для указания, что компилятор CIL в машинный код должен генерировать карту CIL в машинный код).             |

Пример
``` csharp
using System.Reflection;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;

[assembly: AssemblyTitle("MyAssembly")]
[assembly: AssemblyDescription("")]
[assembly: AssemblyConfiguration("")]
[assembly: AssemblyCompany("")]
[assembly: AssemblyProduct("MyProduct")]
[assembly: AssemblyCopyright("Copyright © 2024")]
[assembly: AssemblyTrademark("")]
[assembly: AssemblyCulture("")]

[assembly: AssemblyVersion("1.0.0.0")]
[assembly: AssemblyFileVersion("1.0.0.0")]
```
