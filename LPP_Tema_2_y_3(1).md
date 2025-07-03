
# 📘 Lenguajes y Paradigmas de la Programación  
**Grado en Ingeniería Informática – 3.º curso**  
**Universidad de La Laguna**  
**Temas 2 y 3 - Resolución de cuestiones**

--- 

## 🧩 Tema 2: Fundamentos y Ruby

### 1. ¿Qué se entiende por abstracción?
Proceso de ocultar los detalles de implementación mostrando solo los aspectos esenciales, permitiendo trabajar con modelos simplificados del sistema.

### 2. ¿Qué estructura dan los traductores de lenguajes de alto nivel a la memoria de ejecución?
Dividen la memoria en segmentos: código, datos, pila (stack), heap y registros. Esta organización permite la ejecución ordenada de instrucciones, control de llamadas y gestión de memoria.

### 3. ¿Qué es un procedimiento (subprograma)?
Bloque de código reutilizable con nombre propio, que puede recibir argumentos y devolver resultados. En Ruby se conoce como método (`def nombre`).

### 4. ¿Qué es un Registro de Activación (Stack Frame)?
Estructura que almacena la información necesaria para ejecutar un subprograma: variables locales, parámetros, dirección de retorno y enlaces de contexto.

### 5. ¿Cuál es la estructura estándar de un registro de activación?
- Dirección de retorno  
- Parámetros  
- Variables locales  
- Enlace dinámico  
- Enlace estático

### 6. Flujo de ejecución de un programa con subprograma de suma:
```
main
 └── llama a suma(a, b)
      └── calcula resultado = a + b
           └── retorna a main
```

### 7. ¿Qué se entiende por programación procedural?
Estilo de programación donde el código se organiza como procedimientos o funciones que manipulan datos. Ejemplo: C, Pascal.

### 8. ¿Qué instrucción usaban los primeros lenguajes para modificar la secuencia?
`GOTO`, para saltos incondicionales.

### 9. ¿Por qué se considera perjudicial el uso de `goto`?
Según Dijkstra, rompe la lógica secuencial, dificulta el mantenimiento y comprensión del código.

### 10. ¿Qué establece el Teorema Fundamental de la Estructura?
Cualquier algoritmo puede implementarse usando solo tres estructuras: **secuencia, selección e iteración**.

### 11. ¿Qué es programación estructurada o modular?
Organización del programa en bloques independientes (módulos) que encapsulan funcionalidad específica.

### 12. Características de la programación estructurada:
- Modularidad  
- Claridad del flujo de control  
- Uso limitado o nulo de `goto`  
- Uso de subprogramas

### 13. ¿Qué se entiende por encapsulación?
Ocultar los detalles internos de implementación de un módulo o clase y exponer solo lo necesario.

### 14. Características de la POO:
- Encapsulación  
- Abstracción  
- Herencia  
- Polimorfismo  
- Todo es objeto (en Ruby)

### 15. ¿Qué es Ruby?
Lenguaje de programación dinámico, interpretado, totalmente orientado a objetos.

### 16. Principal característica de Ruby:
**Todo es un objeto**, incluso los números y clases.

### 17. Definición de subprograma:
```ruby
def saludar(nombre)
  puts "Hola, #{nombre}"
end
```

### 18. Separador de sentencias:
Ruby permite múltiples sentencias por línea separadas con `;`, aunque generalmente se evita.

### 19. Comentarios:
```ruby
# Comentario de una línea

=begin
Comentario de
varias líneas
=end
```

### 20. Cadenas literales:
```ruby
'Texto sin interpolación'
"Texto con interpolación: #{valor}"
```

... (truncado por longitud para continuar abajo)

### 21. Interpolación:
Inserción de variables o expresiones dentro de una cadena con `#{}`.

### 22. Prefijos de variables:
- `$`: global  
- `@`: instancia  
- `@@`: clase

### 23. Identificadores en Ruby:
Empiezan con letra o `_`, pueden contener letras, números y `_`.

### 24. Array:
```ruby
a = [1, 2, 3]
```

### 25. Hash:
```ruby
h = {nombre: "Laura", edad: 20}
```

### 26. Symbol:
```ruby
:nombre
```

### 27. ¿Qué números son?
- `010` → 8 (octal)  
- `0x1F` → 31 (hex)  
- `0b1111` → 15 (binario)

### 28. ¿Son válidos subguiones en números?
Sí: `1_000_000` es válido.

### 29. Condicionales:
```ruby
if cond
elsif otra_cond
else
end
```

### 30. Iterativas:
```ruby
while, until, for, each, times
```

### 31. Expresiones regulares:
```ruby
/ruby/i
```

### 32. Operador de matching:
```ruby
texto =~ /patrón/
```

### 33. ¿Qué es `rvm`?
Ruby Version Manager, herramienta para instalar y gestionar versiones de Ruby.

### 34–37. Comandos:
```bash
rvm list known       # disponibles
rvm list             # instaladas
rvm use 3.1.0        # usar versión
ruby -v              # versión activa
```

### 38–39. pry:
REPL avanzada para Ruby  
```bash
gem install pry
```

### 40–41. GitHub Codespaces:
Entorno de desarrollo en la nube  
Se accede desde GitHub > botón "Code" > "Codespaces"

### 42–44. GitHub Copilot:
Asistente con IA para programar. Se instala como extensión en VS Code.

### 45. Pair Programming:
Dos personas programan en conjunto: uno codifica, otro revisa.

### 46. Gestión de dependencias:
Control de librerías externas necesarias para un proyecto.

### 47. ¿Qué es rake?
Herramienta Ruby para automatizar tareas, similar a `make`.

### 48. rake vs make:
`rake` usa Ruby como DSL en vez de sintaxis especial.

### 49–55. Tareas en Rake:
```ruby
# Rakefile
require 'rake'

desc "Tarea ejemplo"
task :ejemplo do
  puts "Hola desde Rake"
end

task :default => [:ejemplo]
```

### 56–57. Unit Testing:
Verifica funciones/métodos individualmente. Los tests se almacenan en `/test`.

### 58–59. Requisitos para test:
```ruby
require 'test/unit'

class MiTest < Test::Unit::TestCase
```

### 60–74. Assertions y ejecución:
```ruby
assert(condición)
assert_equal(esperado, real)
assert_not_equal(esperado, real)
assert_raise(Exception) { bloque }
assert_instance_of(Clase, objeto)
assert_respond_to(objeto, :método)
assert_in_delta(esperado, actual, delta)
```

```ruby
# Ejecutar test específico
ruby test_ejemplo.rb -n nombre_test

# Patrón
ruby test_ejemplo.rb -n /patron/

# Rakefile
require 'rake/testtask'

Rake::TestTask.new do |t|
  t.libs << "test"
  t.test_files = FileList['test/test_*.rb']
end
```

---

## 🧵 Tema 3: Concurrencia y Pruebas

### 1–6. Concurrencia, paralelismo y diferencias:
| Tipo | Lugar | Comunicación |
|------|-------|--------------|
| Concurrente | Un solo núcleo | Memoria compartida |
| Paralela | Múltiples núcleos | Memoria compartida |
| Distribuida | Múltiples máquinas | Red |

### 7–9. Procesos y threads:
- Proceso: Programa en ejecución con su espacio de memoria  
- Thread: Subunidad de ejecución dentro de un proceso  

### 10–12. Condiciones de Bernstein:
Permiten saber si dos instrucciones pueden ejecutarse en paralelo sin interferencia.

### 13–14. Orden y no determinismo:
El orden de ejecución puede variar, provocando salidas distintas en diferentes ejecuciones.

### 15–21. Problemas clásicos:
- Race condition  
- Mutual exclusion  
- Critical section  
- Deadlock  
- Starvation

### 22. Crear threads en Ruby:
```ruby
t = Thread.new { puts "hola" }
```

### 23. Métodos de Thread:
- `Thread.current`  
- `Thread.list`  
- `Thread.kill`  
- `Thread.join`

### 24. Análisis de código:
Imprime info de threads activos, crea y mata hilos, y finaliza con `Thread.exit`.

### 25–26. Variables y acceso:
Cada hilo tiene acceso a variables globales, pero también puede tener locales usando `Thread.current["clave"]`.

### 27. Ejecución con `Thread.current["mycount"]`:
Salida puede variar por condiciones de carrera, `count` final puede ser diferente a esperada.

### 28. Incremento sin sincronización:
El valor final de `sum` será menor que el esperado por condiciones de carrera.

### 29–30. Mutex:
Evita condiciones de carrera. Código protegido:
```ruby
mutex.synchronize { sum = inc(sum) }
```

### 31. Mecanismos anti-deadlock:
- Ordenar adquisición de recursos  
- Uso de `ConditionVariable`

### 32. Código con `ConditionVariable`:
Un hilo espera, el otro despierta al primero. Sincronización clara.

### 33. TDD (Test Driven Development):
Desarrollo basado en pruebas:  
1. Escribir test  
2. Escribir código  
3. Refactorizar

### 34. Paradigma de RSpec:
**BDD** (Behavior Driven Development)

### 35. Pasos con RSpec:
1. Crear especificación  
2. Ejecutar test (fallará)  
3. Implementar código  
4. Repetir

### 36–44. RSpec:
- Directorio: `/spec`
- `describe`: Agrupa tests  
- `it`: Caso individual  
- `before`: Setup  
- `expect(x).to eq(y)`: Comprobación  
- Ejecutar con descripción: `rspec -f d`

```ruby
# Rakefile para RSpec
require 'rspec/core/rake_task'

RSpec::Core::RakeTask.new(:spec)

task :default => :spec
```
